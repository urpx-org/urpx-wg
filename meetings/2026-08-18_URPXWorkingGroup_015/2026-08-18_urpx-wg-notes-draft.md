# Utility Rate Plan Exchange (URPX) Working Group Meeting \#015

#### Date: 2026-08-18 11.30AM US ET (8.30AM US PT)

**Attendees:**
**Regrets:**
**Notetaker:**

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker | Klaartje, All |
| 2 | URPX Status Update | The v0.4.0 content is complete and the tag is imminent. What it changes for an implementer, why the breaking changes land now, and why the release goes out as two tags | Klaartje, All |
| 3 | Ontology | One identifier pattern across the three identifier classes, with an open register; worked before and after examples. The exchange package carries every exchangeable unit through one property | Klaartje, All |
| 4 | SHACL Rules | The three identifier shapes take one surface; a package must carry at least one unit; the closed-shapes policy carried forward | Klaartje, All |
| 5 | API | Requirements gathering: what members would need from an API over published rate plans | Klaartje, All |
| 6 | Documentation | Documentation site and data dictionary; the v0.4.0 design-decision log; what the release notes will carry; member-organization logos | Klaartje, All |
| 7 | Test Data | Every shipped test case declares the URPX version it was authored against, and the declaration is verified; the California and ConEd example sets; the worked organization identity chain | All |
| 8 | Other Business & Next Steps | Volunteer roles; next meeting date; action items | Klaartje, All |

## Meeting Notes

---

#### 1. Quick Hellos

-

---

### 2. URPX Status Update

_Reported: the v0.4.0 content is complete and the tag is imminent. Four changes affect anyone implementing against the model: one identifier pattern across the three identifier classes, one containment property carrying every exchangeable unit on the exchange package, a package that must now carry at least one unit, and a verified URPX version declaration on every shipped test case. The breaking changes land before the first public tag. The release goes out as two tags: v0.4.0 carries the vocabulary, and v0.4.1 carries the licence conversion alone with the vocabulary unchanged across it._

-

**Questions or concerns raised on the two-tag release or the breaking changes:**

-

---

### 3. Ontology

_Reported: `scheme` names the register, `skos:notation` carries the value, and `identifierJurisdiction` is optional, on organization, rate plan and rate plan modifier identifiers alike. The register is an open class, so an implementer-minted register validates without a vocabulary release. `identifierScheme`, `utilityId` and `hasTariffPublication` are retired._

-

**Questions on the rewrite, or on data held against v0.3.0:**

-

---

### 4. SHACL Rules

_Reported: the three identifier shapes take one surface, which is a tightening on the organization side. A package must carry at least one unit. The union range is stated as `sh:or` over single-class shapes._

-

---

### 5. API

_Requirements gathering. What members said they would need from an API that reads published rate plans:_

-

---

### 6. Documentation

-

---

### 7. Test Data

-

---

### 8. Other Business & Next Steps

- Volunteer roles:
- Next meeting:
- Action items are recorded in the table below.

## Action Items

| # | Action | Owner | Due |
| :---- | :---- | :---- | :---- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |

## Materials for review

- The standard: https://github.com/urpx-org/urpx
- Documentation site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Consuming API draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- Consuming API design task, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md

---

<!-- Paste the raw Zoom AI summary below (Quick Recap / Next Steps / Summary), plus the transcript path, then ask for the notes write-up.

Standing rules applied on write-up:
- The "Next Steps" block is folded into the single Action Items table above and deleted; one action list per meeting, never two.
- Only what happened gets recorded. An agenda item not reached stays empty or is marked "not discussed".
- Never a bare "Don": Don Jackson and Donald Coffin are different people.
- Names the transcript garbles get a confirm flag, never a guess.
- The italic _Reported:_ lines are prefilled from the agenda. Correct them against what was actually said, or delete them if the item was not reached.
-->

## Raw meeting summary (paste below, removed before publishing)
