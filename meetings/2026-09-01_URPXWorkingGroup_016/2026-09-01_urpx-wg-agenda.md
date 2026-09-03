# Utility Rate Plan Exchange (URPX) Working Group Meeting \#016

#### Date: 2026-09-01 11.30AM US ET (8.30AM US PT)

_The v0.4.0 vocabulary is finished and three documentation and mapping items stand before the tag. This session covers the two changes since the last meeting that affect anyone building against the model, and where the Green Button work now sits._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker for today's minutes | Klaartje, All | 4 min |
| 2 | URPX Status Update | The v0.4.0 vocabulary is finished and three items stand before the tag. What has landed since 18 August, what the remaining three are, and what goes public at which tag. The Green Button Alliance now officially supports URPX | Klaartje, All | 13 min |
| 3 | Ontology | A calculation now attaches at the measurement it applies to rather than only at price level, with a worked before and after. Two properties retire. Greenhouse gas emissions and green tariffs as a design thread | Klaartje, All | 10 min |
| 4 | SHACL Rules | Three closed shapes gain a calculation path, which is why the change could not wait until after the tag. The retired property and its nested node shape. What a conforming document is validated as | Klaartje, All | 6 min |
| 5 | API | The consuming API is still in requirements gathering. General input welcome on what you would need from an API over published rate plans | Klaartje, All | 4 min |
| 6 | Documentation | The published JSON-LD context as a shipped artifact. The v0.4.0 design-decision register and release notes. The interoperability page's Green Button section and its diagrams. Member-organization logos | Klaartje, All | 7 min |
| 7 | Test Data | Every shipped example now references the published context instead of carrying its own copy, and the corpus validates offline. Twelve of twelve conform. Questions from members' review | All | 10 min |
| 8 | Other Business & Next Steps | Volunteer roles (co-chair, secretary, community outreach); action items carried from meeting 15; next meeting date | Klaartje, All | 6 min |

---

#### 1. Quick Hellos

- Quick recap.
- Welcome any new or returning participants.
- Volunteer note-taker for today's minutes.

---

### 2. URPX Status Update

- **The v0.4.0 vocabulary is finished.** The ontology, the shapes and all twelve shipped examples are in their v0.4.0 state and the full corpus validates. What is left is documentation and one mapping refresh.

- **Three items stand before the tag**, and none of them changes the model.
  1. The pages that teach the old inline JSON-LD context are rewritten onto the published one.
  2. Prose wrapped at a fixed column is normalized across the shipped pages, sixteen of them, measured.
  3. The Green Button section of the interoperability page is reconciled against what the mapping now carries, and its two diagrams are refreshed.


- **What has landed since August 18th.**
  - **A calculation attaches at the measurement it applies to.** Section 3 carries the detail and the rewrite.
  - **URPX publishes a JSON-LD context**, generated from the vocabulary's own ranges and served beside the ontology and the shapes. Section 6 carries it.
  - **Every shipped example references that context** instead of carrying its own copy. Section 7 carries it.
  - **The v0.4.0 design-decision register and the changelog record both the published context and the rule that a conforming document is validated as its declared set.** Section 4 carries that rule.
  - **The Green Button mapping carries its settled alignments**, below.

- **The Green Button Alliance now officially supports URPX and has given permission to use its logo.** Don Coffin has been working the Green Button to URPX mapping with us. The settled part of that work is in the standard: the rider enrollment-status pairings, the alignment of a Green Button tariff profile to a rate plan name, and a structural correction recording that in ESPI V4 a rider reference and a wholesale pricing-node reference are two distinct structures rather than one containing the other. Three questions stay open and each is carried as a draft specification in the repository rather than settled inside the mapping file.

- **The release is still being cut in two, and what goes public when has one clarification.**
  1. **v0.4.0** carries the vocabulary, the shapes, the documentation content and the test cases, under Apache-2.0.
  2. **v0.4.1** carries the licence conversion and nothing else. Specifications move to the W3C Document License and datasets to CDLA-Permissive; source and metadata stay Apache-2.0. The vocabulary is unchanged across it, term for term. **The documentation goes public at this tag.**

- **The sequence after that is unchanged.** v0.5.0 moves the term identifiers to urpx.org and publishes them so they resolve. The LF Energy IP scan runs against the v0.5.0 tree, and the repository and urpx.org go public after it. v0.6.0 carries the additive highly dynamic prices bundle, and it lands after the public flip rather than before it.

---

### 3. Ontology

- **A calculation attaches at the measurement it applies to, rather than only at price level.** `hasCalculationMethod` previously reached only the three price classes, so an aggregation had to be restated on every price measuring the same quantity, and two prices on one metric input could disagree with nothing catching it. Its domain is now the union of `Ledger`, `MetricInput`, `MetricSpecification`, `Price`, `PriceDefinition` and `PriceSet`.

- **Which declaration governs, when more than one is present:** the one nearest the measurement. `MetricSpecification` before `MetricInput` before `Ledger`, resolved per property. A declaration on a price is a copy carried for tabular serialization where a measurement is reachable through the node's own references, and it is expected to agree with that declaration. Where no measurement is reachable, the price-level declaration is complete on its own. No shape reads across a reference to check a copy against its source; a copy that disagrees is a data-quality matter for the implementation holding both.

- **Before and after, the daily accrual on PG&E's base charge**, from the shipped E-ELEC example. The aggregation moves off the price definition and onto the ledger that carries it.

  v0.3.0, on the price definition:

  ```json
  {
    "@type": "urpx:PriceDefinition",
    "urpx:baseQuantity": "1",
    "urpx:hasCalculationMethod": {
      "@type": "urpx:CalculationMethod",
      "urpx:intervalDuration": "P1D"
    },
    "urpx:referencesLedger": { "@id": "pge:ledger-service" }
  }
  ```

  v0.4.0, on the ledger:

  ```json
  {
    "@id": "pge:ledger-service",
    "@type": "urpx:Ledger",
    "urpx:referencesMetricInput": { "@id": "pge:mi-meter-count" },
    "urpx:hasCalculationMethod": {
      "@type": "urpx:CalculationMethod",
      "urpx:intervalDuration": "P1D"
    }
  }
  ```

- **Two properties retire, and the rewrite is two lines.** A `MetricInput` carrying `calculationRule` carries `hasCalculationMethod` to a `CalculationMethod` instead. `formula` inside that old structure becomes `calculationFormula` on the calculation method, and `calculatedBasedOn` moves onto the calculation method unchanged. `calculatedBasedOn` now declares `CalculationMethod` as its domain, which is where a calculated metric input names its sources.

- **Greenhouse gas emissions and green tariffs.** Following the discussion at meeting 15, this is being worked as an addition to URPX rather than as a separate standard or a separate API: how the distribution and supply portions of a rate plan's emissions are represented, so a carbon calculation can be made from the rate plan itself. Stephen Suffian of WattCarbon offered at meeting 15 to help draft the stub specification, using EIA data for carbon intensity at the balancing-authority level. Design-stage, and open for input.

- **v0.6.0 direction, additive and changing none of the above:** machine-readable value expressions for price calculation in place of string formulas, and the highly dynamic prices bundle, covering published price series, how a consumer discovers them, and the mapping to California's MIDAS upload schema.

---

### 4. SHACL Rules

- **`LedgerShape`, `MetricInputShape` and `MetricSpecificationShape` each admit `hasCalculationMethod`**, optional and at most one. All three are closed shapes, which is why this change had to land before the tag rather than after it: a closed shape rejects any path it does not name, so the calculation could not be attached to these nodes by a later additive release.

- **`CalculationMethodShape` admits `calculatedBasedOn`**, optional and unbounded.

- **`calculationRule` is removed, together with the nested node shape inside `MetricInputShape` that carried it.** This breaks in two ways worth stating separately. A document stating `calculationRule` on a `MetricInput` no longer validates, because the shape is closed. And the property is gone from the vocabulary itself, whether or not any document used it.

- **What a conforming document is validated as.** The validation unit is the declared set: a document is validated together with the documents it cites, not on its own. That rule now ships in the v0.4.0 design-decision register rather than living only in the example sets' recipe.

- **The closed-shapes policy carries forward.** An unexpected property is reported as a violation rather than silently ignored.

---

### 5. API

The consuming API for published rate plans is still in requirements gathering. We are collecting input rather than reviewing an interface.

- **What would you need from an API that reads published rate plans?** What you would call, what you would need back, and what would make it unusable for your systems.
- The draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- The task carrying the design work, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md

---

### 6. Documentation

- **URPX publishes a JSON-LD context.** It is generated from the vocabulary's own ranges, declares datatypes for all 100 typed properties, and is served beside the ontology and the shapes at each release. Nobody hand-authors one any more. Because it is derived from the vocabulary rather than maintained alongside it, it cannot fall behind. The address ships in the release notes; the site serving it is not reachable yet.

- **The v0.4.0 design-decision register** carries the calculation change with its precedence rule and its data migration, the published context, and the validation-unit rule, each with the alternatives considered and the reason each was rejected.

- **The v0.4.0 release notes** will list every term-level change, retired terms included, so the rewrites in sections 3 and 4 have a single reference.

- **The interoperability page's Green Button section** is being reconciled against what the mapping now carries, and its two diagrams refreshed. Nothing in that section will reference a Green Button term the mapping does not support.

- **Member-organization logos:** if your organization would like to be featured on urpx.org and the LF Energy landing page, please send a logo and confirm we may display it.

---

### 7. Test Data

- **Every shipped example references the published context** instead of carrying its own copy. Twelve of twelve. Each example's `@context` is now the published address plus its own local prefixes, and nothing else moved in the file:

  ```json
  "@context": [
    "https://urpx-org.github.io/urpx/context/releases/v0.4.0/jsonld/urpx-context.jsonld",
    {
      "org": "https://urpx-org.github.io/urpx/fixtures/org/",
      "pge": "https://urpx-org.github.io/urpx/fixtures/pge/"
    }
  ]
  ```

- **Each example's graph is unchanged by the substitution**, checked file by file against the same examples before the change.

- **The corpus validates offline.** The validation resolves the published address from a local copy of the artifact, so a run reaches the network zero times. Twelve scenarios plus the supply-referenced example all conform.

- **Every shipped example still declares the URPX version it was written against**, and the declaration is checked rather than trusted.

- The California rate plan examples, including the Net Billing Tariff modifier, from the California Energy Commission participants. The ConEd example set and the two PG&E sets. The PG&E E-TOU-C example carries the worked organization identity chain.

- Contributing new examples, tasks, or feedback through the development-documents tasks folder in the repository.

---

### 8. Other Business & Next Steps

_Time-limited slot._

- Volunteer roles: co-chair, secretary, community outreach.
- Action items carried from meeting 15.
- Next meeting date.

---

## Materials for review

- The standard: https://github.com/urpx-org/urpx
- Documentation site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Consuming API draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- Consuming API design task, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md
