

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#012

#### Date: 2026-07-14 11.30AM US ET

_An additional session, called to review the v0.3.0 candidate ahead of the release vote. The next regular meeting is 2026-07-21._

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap, welcome new and returning participants | Klaartje, new participants |
| 2 | URPX Status Update | v0.3.0 candidate ontology + SHACL prepared and audited; documentation status | Klaartje, All |
| 3 | Model Update Walkthrough | Main item. Walk through the circulated pre-read: the revised model carried through the vocabulary, what's new / changed / retired, and the ConEd SC1 Rate I worked example from identity to resolved snapshot | Klaartje, Dave, All |
| 4 | Terminology: "price" replaces "rate" | Proposed tutorial/terminology update: "price" replaces the "rate" entry; why URPX avoids the bare word "rate"; `RateGroup` as the mapping to what utilities colloquially call rates | Klaartje, All |
| 5 | Release & Licensing | With the model validated end to end, the path to release: an electronic vote in the LFX control panel to approve v0.3.0 and authorise going public. Publication then follows the license conversion (specifications to the W3C Document License, datasets to CDLA-Permissive) and the LF Energy IP scan. Assent to the `RatePlanVersion` re-meaning is the gate before the vote opens. | Klaartje, All |
| 6 | Test Data & SHACL | Closed shapes policy; validation workflow for cross-referencing example files; questions from members' review | All |
| 7 | Other Business & Next Steps | Review owners, next meeting date, volunteer roles, action items | Klaartje, All |

---

### Pre-read

- **URPX Model Update — Walkthrough of the v0.3.0 Candidate** in urpx/dev-docs/reports (accessible to members). Please read sections 2, 6, and 8 before the call.

---

#### 1. Quick Hellos

- Quick recap
- Welcome any new or returning participants

---

### 2. URPX Status Update

- v0.3.0 candidate ontology and SHACL shape set prepared; full shape audit complete (closed shapes, ontology/shape alignment, retired-class cleanup).
- Five-part worked example (ConEd SC1 Rate I) validates end to end: identity, tariff book filing, statement filing, market price feed, resolved snapshot, both individually and as one connected graph.
- Released v0.2.1 unchanged; all v0.3.0 material is candidate-stage pending this group's review.

---

### 3. Model Update Walkthrough

- The model in one paragraph: rate plan = stable identity; published pricing content = `PricingModel` (may be partial, reaches plans by reference or applicability); regulatory wrapper = `TariffFiling`; what consumers read = `RatePlanVersion`, a resolved snapshot with an explicit `CoverageClaim`.
- What is new / what changed / what is retired (pre-read sections 3–5).
- The worked example, end to end (pre-read section 6): how three fragmented sources (a tariff book leaf, a monthly statement, a market price feed) consolidate into one readable snapshot without losing provenance.
- Open vocabulary items queued as a follow-up change set (pre-read section 7).
- For the group: does the example set cover your publication patterns? Which additional pattern should be exercised next?

---

### 4. Terminology: "price" replaces "rate"

- Proposed update to the tutorial terminology section (walked through during the call): the "Rate" entry becomes **Price**; URPX consistently says *price* for a single value and *rate plan* for the complete package.
- Why: "rate" is ambiguous. Utilities use it for a single price, for a price grouping, and for the whole plan.
- `RateGroup` gives the ambiguity a home: it models the named grouping within a service class (e.g. Rate I within SC 1) that utilities colloquially call a "rate", so rate plans can map to utility groupings without importing the ambiguous word into the vocabulary.

---

### 5. Release & Licensing

- At #011 the group agreed to hold the public release and the license transition until the model update was resolved.
- The model is now carried through the vocabulary and shapes and validated against the worked example set. Proposed path: review and assent on the walkthrough, then an electronic vote in the LFX control panel to approve v0.3.0 and authorise going public.
- What the approval authorises: converting the licenses (specifications to the W3C Document License, datasets to CDLA-Permissive) and the LF Energy IP scan. Publication follows once both are complete.

---

### 6. Test Data & SHACL

- Closed-shapes policy: unexpected properties are flagged as violations rather than silently ignored, and what this means for implementers.
- Validation workflow for example files that reference each other (validating a file together with the files it cites).
- Questions and feedback from members' review.

---

### 7. Other Business & Next Steps

- Owners for written feedback on the walkthrough
- Next regular meeting: **2026-07-21** (today's 2026-07-14 session is an additional v0.3.0 review meeting)
- Volunteer roles: co-chair, secretary, community outreach
- Action item assignments from today's meeting
