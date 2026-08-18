

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#014

#### Date: 2026-08-04 11.30AM US ET

_v0.3.0 is merged. This session covers what it carries and the three steps remaining before the standard goes public._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker for today's minutes | Klaartje, All | 4 min |
| 2 | URPX Status Update | v0.3.0 is merged. The remaining path to public in three steps: license conversion, the move to urpx.org term identifiers, then the LF Energy IP scan and going public | Klaartje, All | 10 min |
| 3 | Ontology | What v0.3.0 carries, and early v0.5.0 direction, additive to v0.3.0: machine-readable value expressions and the highly dynamic prices work; comments welcome while the design is soft | Klaartje, All | 8 min |
| 4 | SHACL Rules | Shape work following the v0.5.0 drafts; the closed-shapes policy carried forward from v0.3.0; validation workflow for example files that reference one another | Klaartje, All | 7 min |
| 5 | API | The consuming API for published rate plans, now an active design track: a draft specification is in the repository and design is in progress. Scope, and how the read path relates to the dynamic price series work and the MIDAS mapping | Klaartje, All | 9 min |
| 6 | Documentation | The documentation site and data dictionary ahead of the public site; worked examples and tutorial; a published JSON-LD context file; member-organization logos | Klaartje, All | 7 min |
| 7 | Test Data | California rate plan examples, including the Net Billing Tariff modifier; worked sample datasets for the dynamic-pricing drafts; how to contribute; questions from members' review | All | 9 min |
| 8 | Other Business & Next Steps | Volunteer roles (co-chair, secretary, community outreach); next meeting date; action items. Time-limited slot, held to 5–7 minutes | Klaartje, All | 6 min |

---

#### 1. Quick Hellos

- Quick recap.
- Welcome any new or returning participants.
- Volunteer note-taker for today's minutes.

---

### 2. URPX Status Update

- **v0.3.0 is merged to main.**
- **What landed in v0.3.0 since we last met.** Element-level consolidation lineage, so a resolved snapshot records which pricing model each of its elements came from and a consumer can trace it back to the source filing and rate case. Three enumerations that previously shipped as bare identifiers now carry a definition on every member, so they appear in the data dictionary and each value has a stated meaning. The phase codes are grouped under four categories. The plan-to-organization link is now `offeredBy`, naming the organization that offers the plan, with `publishedBy` reserved for the artifacts that are actually published. Every identifier the ontology refers to is now defined in it.
- **The path from here to public, in three steps.** We are deliberately not going public on the first tag:
  1. Convert the licenses: specifications to the W3C Document License, datasets to CDLA-Permissive. Source and metadata stay Apache-2.0.
  2. Move the term identifiers to urpx.org, and publish them so they resolve.
  3. Request the LF Energy IP scan, then make the repository public and bring urpx.org live.
- **Why the identifier move comes before we go public, and not after.** Every URPX term currently has an identifier under the project's GitHub Pages address. Those identifiers are what anyone building on URPX writes into their data, so changing them later would mean asking early implementers to rewrite. Doing it before the repository is public means nobody outside this group has to absorb it. This follows what comparable standards do: the identifiers live on the domain the governing body owns, so where the files are hosted can change later without any identifier changing. The existing published files stay reachable.
- **What this asks of members building on v0.3.0 now:** nothing yet, but expect the term identifiers to change once, before we publish, and plan to point at the urpx.org form when we announce it. If you have a branch or a dataset against the current identifiers, it is a mechanical find-and-replace and we will publish exactly what to replace.

---

### 3. Ontology

- **v0.3.0 as merged.** Questions on anything in the release notes, in particular the coverage-claim change: a claim now reports how complete a snapshot is separately from whether it is stale or fell back to a secondary source, so it can say "complete, but fallback-sourced" without one fact displacing the other.
- **Early v0.5.0 direction**, additive to v0.3.0 and not changing it: machine-readable value expressions for price calculation in place of string formulas, and the highly dynamic prices work (published price series, how a consumer discovers them, and the mapping to California's MIDAS upload schema).
- These are design-stage drafts. Comments are welcome now, while the design is soft.

---

### 4. SHACL Rules

- Shape work that follows the v0.5.0 vocabulary drafts once their direction settles.
- The closed-shapes policy carried forward from v0.3.0: unexpected properties are reported as violations rather than silently ignored, and what that means for implementers.
- Validation workflow for example files that reference one another (validating a file together with the files it cites).

---

### 5. API

- The consuming API for published rate plans is now an active design track: a draft specification is in the repository and the design is in progress. It is not yet ready for detailed review; comments on scope and priorities are welcome now.
- Scope: discovery of plans in a territory, retrieval of rate plan versions over a date range, and eligibility checks against a customer profile.
- Relationship to the highly dynamic prices work: the read path references, and does not duplicate, the dynamic price series discovery and conformance design and the mapping to California's MIDAS upload schema.

---

### 6. Documentation

- The documentation site and data dictionary as they stand ahead of the public site. The data dictionary now shows the three previously undocumented enumerations and the phase-code grouping.
- Worked examples and the tutorial; any follow-ups from members' reading of the review materials.
- One documentation item planned alongside the identifier move: a published context file for JSON-LD, so an implementer does not have to hand-write the namespace and datatype declarations that every example currently carries inline. Getting those wrong silently turns prices and dates into plain text.
- Organization logos: if your organization would like to be featured on urpx.org and the LF Energy landing page, please send a logo to urpx@fluxtailor.com and confirm we may display it.

---

### 7. Test Data

- California rate plan examples offered for the model, including the Net Billing Tariff modifier, from the California Energy Commission participants (MIDAS).
- The worked sample datasets that exercise the dynamic-pricing drafts.
- Contributing new examples, tasks, or feedback through the development-documents tasks folder in the repository. Contributions are written and reviewed by the person submitting them; drafting with an LLM does not remove that responsibility, and submissions should be concise, accurate, and actionable so that review stays manageable.
- Questions and feedback from members' review of the test data and shapes.

---

### 8. Other Business & Next Steps

_Time-limited slot, held to 5–7 minutes._

- Volunteer roles: co-chair, secretary, community outreach.
- Next meeting date.
- Action item assignments from today's meeting.

---

## Materials for review

- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md
- The standard: https://github.com/urpx-org/urpx
- Updated site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- Launch announcement drafts: blog https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-blog-post.draft.md · newsletter https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-newsletter.draft.md
