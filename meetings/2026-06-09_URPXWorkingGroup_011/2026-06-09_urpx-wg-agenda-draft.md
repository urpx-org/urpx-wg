

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#011

#### Date: 2026-06-09 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap, welcome new and returning participants | Klaartje, new participants |
| 2 | URPX Status Update | IP scan clean on main, documentation review feedback, urpx.org review links, v0.2.1 in place | Klaartje, All |
| 3 | Rate Plan Model Reframe | Main item. Walk through the circulated report; why the current version-timeline model can't represent how parts of rate plans are currently published: as tariff documents; the proposed direction | Klaartje, Dave, All |
| 4 | Release & Licensing | Proposal to hold the public release and the W3C document-license transition until the reframe is resolved | Klaartje, All |
| 5 | Documentation | Semantic Flow / dereferenceable IRIs; terminology page rewrite (waits on item 3) | Klaartje, Dave, All |
| 6 | Test Data & SHACL | Skip unless there are questions | All |
| 7 | Other Business & Next Steps | Review owners, next meeting date, volunteer roles, action items | Klaartje, All |

---

### Pre-read

- Walkthrough report: **"URPX Was Broken — we think we fixed it, please help us check"** (circulated; `urpx/dev-docs/reports`). Please read items 3 and 4 before the call.

---

#### 1. Quick Hellos

- Quick recap
- Welcome any new or returning participants

---

### 2. URPX Status Update

- IP scan complete on the main branch — zero findings; LF Energy's IP scanning specialist noted the code is very clean.
- Documentation review: comments received on some documentation pages; no feedback yet on the urpx.org page. Links below — please review.
  - Production (urpx.org content): https://github.com/urpx-org/urpx-website
  - Staging / hosted review site: https://legendary-adventure-2qlokyv.pages.github.io
- v0.2.1 in place; no ontology changes released since last meeting.

---

### 3. Rate Plan Model Reframe

- Background: today "Rate Plan" is spread across PDF text and tariff sheets; URPX exists to make it a first-class modelled thing.
- The problem: the current `RatePlanVersion` model assumes each version is complete, non-overlapping, and carries all its own prices. Real publications are partial — a section amends only eligibility, a statement carries only one month's adjustment, supply prices sit in separate contracts.
- The proposed direction: separate what utilities currently author in tariff documents and other sources (`PricingModel`, may be partial, grouped by `ModelCollection`) from what reconciliation derives (a complete snapshot carrying a coverage claim); one `RatePlan` covers both fully-authored and assembled-at-compute-time plans.
- This redefines an already-published class (`RatePlanVersion`), so we want the group's review before it is fixed.
- For the group: where the computed cost result belongs (URPX or the platform layer); whether the grouping construct is one class or split by role.

---

### 4. Release & Licensing

- Proposal: hold the public release and the move to the W3C document license until item 3 is resolved.
- Rationale: the change is breaking and touches a published class; the current design leaves room for two conformant implementers to model the same tariff differently; the license transition is gated on accepting a working-group draft, and we would rather ratify the corrected model once.
- This is a delay, not a redesign — the core direction is set; remaining work is closing the open questions and reframing the specs.

---

### 5. Documentation

- Using Semantic Flow to make URPX IRIs dereferenceable: https://semantic-flow.github.io/sflo
- Terminology page rewrite (`RatePlan` vs `RatePlanModifier`, the reframed vocabulary) — waits on item 3
- Questions from members' materials review

---

### 6. Test Data & SHACL

- Questions and feedback from members' review

---

### 7. Other Business & Next Steps

- Owners for written feedback on the reframe report
- Next meeting date and time confirmation
- Volunteer roles: co-chair, secretary, community outreach
- Action item assignments from today's meeting
