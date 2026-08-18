# Utility Rate Plan Exchange (URPX) Working Group Meeting \#015

#### Date: 2026-08-18 11.30AM US ET (8.30AM US PT)

**Attendees:**
**Regrets:**
**Notetaker:**

> _These notes were written up from the meeting summary rather than the recording transcript. If anything here is misattributed or missing, say so and it will be corrected._

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

- Stephen of WattCarbon joined the working group. He described his background in energy data standards and WattCarbon's work measuring energy and carbon savings from distributed energy resources, and his interest in contributing to tariff and bill savings work.
- Klaartje agreed to add Stephen to the URPX committers group and the working group.

---

### 2. URPX Status Update

_Reported: v0.4.0 carries the vocabulary changes and is ready to merge after final review. The licence transition follows at v0.4.1. The move to urpx.org term identifiers is v0.5.0, ahead of the public release._

- **v0.4.0 is available with the ontology updates.** Two changes were called out: an open identifier register, so an implementer can name a register outside the published set without waiting for a vocabulary release; and the exchange package, which now carries every exchangeable unit through one property rather than only rate plans and modifiers.
- Extensive housekeeping accompanied the release, across 57 changed files. Each version now has its own design decisions document.
- **The licence transition is v0.4.1**, and is a condition of hosting with LF Energy: specifications move to the W3C Document License and datasets to CDLA-Permissive-2.0, while source and metadata stay Apache-2.0.
- **v0.5.0 carries the namespace and publication path**, ahead of the public release. Klaartje described the challenges of namespace publication and versioning, referencing SPDX as a precedent, and reported ongoing work with LF Energy support on DNS and the namespace for urpx.org.
- **The namespace form is decided: hash rather than slash.** Klaartje explained that a hash namespace means publishing one top-level vocabulary document rather than a directory per term, so a consumer fetches the whole vocabulary in one request. It is the pattern W3C recommends for a vocabulary of this size, it is the form an RDF library, a validator or a language model wants, and it removes the duplication between per-term pages and the data dictionary.
- Klaartje also explained the URPX file structure and its ability to identify root nodes within packaged content.

---

### 3. Ontology

- **Identifier schemes for organizations and rate plans changed**, which affects dataset validation for anyone holding data against the previous form.

**Greenhouse gas emissions in URPX**

This was the meeting's substantial new topic, raised with Stephen of WattCarbon.

- The work is **an addition to URPX**, not a separate standard and not a separate API. Klaartje asked Stephen to help draft a stub specification describing how emissions would be represented in URPX and read through its API, so it can be shared publicly.
- The discussion covered the difficulty of measuring and verifying the emissions actually associated with retail energy purchases, particularly under green tariffs. Stephen acknowledged the complexity of tracing specific emissions sources and offered to help develop a scheme using EIA carbon intensity data at the balancing authority level.
- **What is missing today is a standard way to represent, in a rate plan, the emissions associated with the energy supplied under it.** A consumer buying clean energy through a green tariff or a community choice aggregation program has no transparent statement of the emissions attached to it, and has to verify the purchase after the fact rather than reading it up front. Carrying it in URPX would let carbon calculations and compliance work, including New York City's Local Law 97, be done from the rate plan itself.
- Stephen expressed interest in developing specifications for green tariffs and greenhouse gas emissions.

---

### 4. SHACL Rules

- Not covered in the available summary.

---

### 5. API

_Reported: the API specification will be public, and is designed as a read-only data consumption API with possible write support later._

- Klaartje confirmed the read-only scope and noted that write capability may follow.
- **Utilities publicly declaring their profiles in machine-readable form** was raised as important to consistent implementation across systems.
- API development continues, led by Flux Tailor, and implementers were asked to share their API requirements.
- Don Jackson noted the absence of established profiles in OpenADR, and pointed out that profiles are helpful for implementers.
- Klaartje mentioned collaboration on customer data, and noted the work is interconnected with Green Button.

---

### 6. Documentation

- **The automatically generated diagrams** work well for navigation, but crossing lines and other visual elements need improvement.
- **Automation moved onto a GitHub App with managed secrets**, so the publication and generation pipeline does not depend on one person's credentials as the team expands.
- Documentation snapshots and dictionary content are being generated automatically on major version updates. Stephen asked whether there are standards for adding navigation aids to a published vocabulary.
- Asked who the pipeline is aimed at, Klaartje described it as serving the whole path: helping utilities publish digitally, while bridging the gap between digital documents and the static PDFs that exist today.

---

### 7. Test Data

- Klaartje described plans for a separate repository to hold contributed test cases, set up as a community-maintained sandbox and kept apart from the standard's own shipped examples.
- The need for proper documentation and metadata on contributed data was discussed.

---

### 8. Other Business & Next Steps

- **New participant:** Stephen of WattCarbon, joining the committers group and the working group. WattCarbon's logo will be added as a supporting organization once Stephen confirms permission.
- **Green Button Alliance logo** to be added to the URPX materials, coordinating with Jeremy on the correct version.
- Klaartje will prepare a status update for the LF Energy technical committee.
- The draft communications announcements for the public launch remain open for review.
- Design principles, and keeping compatibility with existing data, were raised as things to improve as the standard grows.
- **Where to contribute.** Work in progress is tracked in the `dev-docs/tasks/` folder of the URPX repository, where contributors can add a task or pick one up. It is a lower barrier than filing an issue for anyone working with an assistant. One standing expectation goes with it: whatever you submit, you have written and reviewed it yourself. Drafting with a language model does not transfer that responsibility. Submissions should be concise, accurate and actionable rather than long and generated, because review time is the scarce resource here.
- Action items are recorded in the table below.

## Action Items

| # | Action | Owner | Due |
| :---- | :---- | :---- | :---- |
| 1 | Share GitHub handle with Klaartje to be added to the URPX committers group | Stephen | |
| 2 | Obtain permission from WattCarbon to add their logo as a supporting organization | Stephen | |
| 3 | Contribute to the specification for greenhouse gas emissions in URPX, defining green tariffs and their parameters | Stephen | |
| 4 | Merge v0.4.0, which carries the ontology updates, after final review | Klaartje | |
| 5 | Complete the licence transition at v0.4.1: specifications to the W3C Document License, datasets to CDLA-Permissive-2.0, source and metadata staying Apache-2.0 | Klaartje | |
| 6 | Work with LF Energy support on DNS and namespace resolution for urpx.org | Klaartje, Jerry Ortiz | |
| 7 | Meet to review the draft Green Button to URPX mapping | Klaartje, Don Coffin | This week |
| 8 | Send Klaartje a calendar link for the Green Button mapping review | Don Coffin | |
| 9 | Add the Green Button Alliance logo to the URPX materials, coordinating with Jeremy on the correct version | Klaartje | |
| 10 | Prepare a status update for the LF Energy technical committee | Klaartje | |
| 11 | Review and enhance the draft communications announcements for the public launch | Klaartje | |
| 12 | Continue the API specification work, incorporating requirements from implementers | Flux Tailor | |
| 13 | Review the v0.4.0 changes, especially the identifier pattern and the exchange package, and give feedback | Working Group | |

## Materials for review

- The standard: https://github.com/urpx-org/urpx
- Documentation site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Consuming API draft specification: https://github.com/urpx-org/urpx/blob/main/dev-docs/specs/spec.urpx.api.047.consuming-api.md
- Consuming API design task, where requirements can be added: https://github.com/urpx-org/urpx/blob/main/dev-docs/tasks/task.urpx.api.2026-07-22.consuming-api-design.md
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md

---

