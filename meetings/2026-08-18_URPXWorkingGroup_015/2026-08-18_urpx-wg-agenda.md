# Utility Rate Plan Exchange (URPX) Working Group Meeting \#015

#### Date: 2026-08-18 11.30AM US ET (8.30AM US PT)

_The v0.4.0 content is finished and the tag is next. This session covers what it changes for anyone building against the model, and why the release goes out as two tags rather than one._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker for today's minutes | Klaartje, All | 4 min |
| 2 | URPX Status Update | The v0.4.0 content is complete and the tag is imminent. What it changes for anyone implementing against URPX, why the breaking changes land now, and why the release is being cut in two so the licence conversion ships on its own. What has landed since 4 August, and one correction to what the group was last told | Klaartje, All | 13 min |
| 3 | Ontology | One identifier pattern across organization, rate plan and rate plan modifier identifiers, with an open register. Worked before and after examples. The exchange package now carries every exchangeable unit through one property, so any of them can declare the URPX version it was authored against | Klaartje, All | 11 min |
| 4 | SHACL Rules | The three identifier shapes take one surface. A package must now carry at least one unit. How the union-class constraint is stated in SHACL core, and the closed-shapes policy carried forward | Klaartje, All | 7 min |
| 5 | API | The consuming API is in requirements gathering. General input welcome on what you would need from an API over published rate plans; the draft specification and its task are linked | Klaartje, All | 4 min |
| 6 | Documentation | The documentation site and data dictionary; the design-decision log for v0.4.0; what the release notes will carry; member-organization logos | Klaartje, All | 6 min |
| 7 | Test Data | Every shipped test case now declares the URPX version it was authored against, and the declaration is verified rather than asserted. The California and ConEd example sets; the worked organization identity chain; questions from members' review | All | 10 min |
| 8 | Other Business & Next Steps | Volunteer roles (co-chair, secretary, community outreach); next meeting date; action items. Time-limited slot, held to 5 to 7 minutes | Klaartje, All | 5 min |

---

#### 1. Quick Hellos

- Quick recap.
- Welcome any new or returning participants.
- Volunteer note-taker for today's minutes.

---

### 2. URPX Status Update

- **The v0.4.0 content is complete and the tag is imminent.** The vocabulary, the shapes, and every shipped test case are in their v0.4.0 state, the full fixture set validates, and there are no undefined terms left anywhere in the ontology or the shapes.

- **What has landed since 4 August.** Beyond the four vocabulary changes below:
  - **Test data.** The ten example files that carried no version declaration are now wrapped in a package that carries one, so every shipped example states the URPX version it was written against and the statement is checked. The PG&E E-TOU-C example folder lost its effective-date suffix, so the folder names the plan rather than one snapshot of it.
  - **The form of the term identifiers is decided.** At the namespace move, URPX terms become fragments of a single vocabulary document, `https://urpx.org/ns/urpx#RatePlan`, rather than one web resource per term. The write-up in the repository carries the reasoning, the case for the alternative stated fairly, and what it means if you hold data. It is open for comment.
  - **Release automation runs under the project's own identity.** Releases and site deployment moved off a personal account onto a GitHub App belonging to the project, so the standard does not depend on one person's credentials as it goes public. Regenerated content now arrives as a pull request to be reviewed rather than as a direct push, and both the credential step and the publication step stop rather than proceeding on a failed check.
  - **The documentation site is built from the pages themselves.** Each page now carries its own placement, replacing a separately maintained table that had drifted from the standard's tree; the drift is now checked automatically. The v0.4.0 design-decision page is published, and the identifier register is placed in the data dictionary. A check runs over generated pages and release bodies before they publish.
  - **The v0.3.0 release notes are finalized** as the tagged release page.

- **Four things change for anyone implementing against URPX.**
  1. **One identifier pattern** across organization, rate plan and rate plan modifier identifiers. All three take the same surface, and the register an identifier comes from is an open class, so an implementer running a register outside the published set names it with an identifier of their own instead of waiting for a vocabulary release.
  2. **The exchange package carries every exchangeable unit** through a single containment property. A rate plan, a modifier, either version snapshot, a pricing model, a tariff filing and a source publication can all be packaged. The consequence worth knowing is that any of them can now declare which URPX version it was authored against, which previously only a packaged rate plan could do.
  3. **A package must carry at least one unit.** An envelope holding only metadata and a version declaration no longer validates.
  4. **Every shipped test case declares the URPX version it was authored against**, and that declaration is now checked rather than trusted.

- **The breaking changes are deliberate, and they land before the first public tag.** No released vocabulary is affected: nobody outside this group can have bound to these terms yet, which is exactly why the corrections are being made now rather than carried.

- **One correction to what you were last told.** The 10 August note said the term identifiers move to urpx.org at v0.4.0. The release windows have since been renumbered: v0.4.0 is the vocabulary, v0.4.1 is the licence conversion, and the move to urpx.org term identifiers is v0.5.0. The identifier form described in that write-up is unchanged, and so is the reasoning; only the release it lands in has moved. The write-up still reads v0.4.0 throughout, so read it for the change and this agenda for the release it belongs to.

- **The release is being cut in two.**
  1. **v0.4.0** carries the updated vocabulary, under Apache-2.0. The full model exists as a tagged artifact before any licence conversion touches it.
  2. **v0.4.1** carries the licence conversion and nothing else. Specifications move to the W3C Document License and datasets to CDLA-Permissive; source and metadata stay Apache-2.0. The vocabulary is unchanged across it, term for term.

  Splitting them means the licence change arrives as its own release note rather than sitting underneath a list of retired properties. A short message goes to the group between the two tags.

- **What follows, at the level of the sequence rather than the work.** v0.5.0 moves the term identifiers to urpx.org and publishes them so they resolve. v0.6.0 carries the additive highly dynamic prices bundle. Then the LF Energy IP scan, the repository goes public, and urpx.org goes live. Nothing in the split above moves either of those windows.

---

### 3. Ontology

- **One identifier pattern.** `scheme` names the register the identifier came from, `skos:notation` carries the value, and `identifierJurisdiction` is optional. Organization, rate plan and rate plan modifier identifiers all take that pattern; previously the organization side and the rate plan side modelled the same thing two different ways.

- **The register is an open class.** `IdentifierScheme` publishes the common registers as defined members, and an implementer operating a register that is not among them mints an identifier for it and stays valid. Two registers are newly defined and both were previously referred to without existing: the California MIDAS RIN register, `urpx:caMidasRinScheme`, and the utility tariff code register, `urpx:utilityTariffCodeScheme`.

- **The exchange package.** `packages` is the one containment property, and its range is the union of rate plan, rate plan modifier, both version snapshots, pricing model, tariff filing and source publication. `hasRatePlan` and `hasRatePlanModifier` stay valid on a package, so a reader of package contents reads both paths.

- **Before and after, an organization identifier.** Pacific Gas and Electric's EIA identifier, as it appears in the shipped PG&E E-TOU-C example. Two keys change and both are now required; the register member identifier is unchanged.

  v0.3.0:

  ```json
  {
    "@type": "urpx:OrganizationIdentifier",
    "urpx:identifierScheme": { "@id": "urpx:eiaScheme" },
    "urpx:utilityId": "14328",
    "urpx:identifierJurisdiction": "US"
  }
  ```

  v0.4.0:

  ```json
  {
    "@type": "urpx:OrganizationIdentifier",
    "urpx:scheme": { "@id": "urpx:eiaScheme" },
    "skos:notation": "14328",
    "urpx:identifierJurisdiction": "US"
  }
  ```

- **Before and after, a rate plan identifier.** ConEd's Service Classification No. 1 Rate I, as it appears in the shipped ConEd example. Only the register identifier changes here, because this side already carried the pattern; the register it named was simply never defined.

  v0.3.0:

  ```json
  {
    "@type": "urpx:RatePlanIdentifier",
    "skos:notation": "SC1-RATE-I",
    "urpx:scheme": { "@id": "https://urpx-org.github.io/urpx/ontology/utility-tariff-code" }
  }
  ```

  v0.4.0:

  ```json
  {
    "@type": "urpx:RatePlanIdentifier",
    "skos:notation": "SC1-RATE-I",
    "urpx:scheme": { "@id": "https://urpx-org.github.io/urpx/ontology/utilityTariffCodeScheme" }
  }
  ```

- **A register URPX has not published.** This is what the open class buys. No vocabulary release is needed to name your own register, and the identifier validates as it stands.

  ```json
  {
    "@type": "urpx:OrganizationIdentifier",
    "urpx:scheme": { "@id": "https://your-regulator.example.gov/registers/utility-id" },
    "skos:notation": "UTIL-0042"
  }
  ```

- **What to rewrite, term by term.** On organization identifiers, `identifierScheme` becomes `scheme` and `utilityId` becomes `skos:notation`, and both are now required. On a package, `hasTariffPublication` becomes `packages`. Where a `scheme` value was written as a hyphenated name for either of the two registers above, it becomes the defined camelCase member. That is the whole list, and the release notes will carry it term by term.

- **v0.6.0 direction, additive and not changing any of the above:** machine-readable value expressions for price calculation in place of string formulas, and the highly dynamic prices work, which covers published price series, how a consumer discovers them, and the mapping to California's MIDAS upload schema. These are design-stage drafts and the design is still soft.

---

### 4. SHACL Rules

- **The three identifier shapes take one surface:** `scheme` required, `skos:notation` required, `identifierJurisdiction` optional and at most one. This is a tightening on the organization side, where an identifier carrying nothing used to validate.

- **The register constraint is a node-kind constraint,** not a list of permitted values. That is what makes a register outside the published members legal, and it is why the register moved from an enumeration to a class.

- **A package must carry at least one unit.** The shape requires one of `packages`, `hasRatePlan` or `hasRatePlanModifier` on every package. Each path stays optional on its own; the requirement is that a package uses one of them, not any particular one.

- **How the union range is stated.** `sh:class` takes exactly one class, so the union is expressed as `sh:or` over single-class shapes. Worth knowing if you are reading the shape file and expecting a single class constraint.

- **The closed-shapes policy carries forward:** an unexpected property is reported as a violation rather than silently ignored, and validating a file together with the files it cites remains the recipe for the example sets.

---

### 5. API

The consuming API for published rate plans is in requirements gathering. We are collecting input rather than reviewing an interface.

- **What would you need from an API that reads published rate plans?** What you would call, what you would need back, and what would make it unusable for your systems. General input is what is useful at this stage, in the meeting or on the draft.
- The draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- The task carrying the design work, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md

---

### 6. Documentation

- The documentation site and the data dictionary. The identifier register now appears as an open register rather than as a closed list of permitted values, which is a change in how the dictionary presents it as well as in what it means.
- The design-decision log for v0.4.0 carries both changes with the alternatives that were considered and the reason each was rejected, including the two cases where a proposed shortcut would have entailed something untrue about the data.
- The v0.4.0 release notes will list every term-level change, retired terms included, so the rewrite in section 3 has a single reference.
- Member-organization logos: if your organization would like to be featured on urpx.org and the LF Energy landing page, please send a logo and confirm we may display it.

---

### 7. Test Data

- **Every shipped test case declares the URPX version it was authored against, and the declaration is verified.** Each fixture is checked against the version it names, so a declaration that does not hold fails rather than sitting in the corpus. All twelve currently pass.
- The California rate plan examples, including the Net Billing Tariff modifier, from the California Energy Commission participants. The ConEd example set and the two PG&E sets.
- The PG&E E-TOU-C example carries the worked organization identity chain, so an EIA, DUNS or LEI value has a modelled path to follow rather than a prose description.
- Contributing new examples, tasks, or feedback through the development-documents tasks folder in the repository.
- Questions and feedback from members' review of the test data and shapes.

---

### 8. Other Business & Next Steps

_Time-limited slot, held to 5 to 7 minutes._

- Volunteer roles: co-chair, secretary, community outreach.
- Next meeting date.
- Action item assignments from today's meeting.

---

## Materials for review

- The standard: https://github.com/urpx-org/urpx
- Documentation site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Consuming API draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- Consuming API design task, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md
