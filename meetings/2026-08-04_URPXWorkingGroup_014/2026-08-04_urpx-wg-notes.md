

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#014

#### Date: 2026-08-04 11.30AM US ET

**Attendees:**
**Regrets:**
**Notetaker:**

> _These notes were written up from the meeting summary rather than the recording transcript. If anything here is misattributed or missing, say so and it will be corrected._

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker | Klaartje, All |
| 2 | URPX Status Update | v0.3.0 is merged. The remaining path to public in three steps: license conversion, the move to urpx.org term identifiers, then the LF Energy IP scan and going public | Klaartje, All |
| 3 | Ontology | What v0.3.0 carries, and early v0.5.0 direction, additive to v0.3.0 | Klaartje, All |
| 4 | SHACL Rules | Shape work following the v0.5.0 drafts; the closed-shapes policy; validation workflow for cross-referencing example files | Klaartje, All |
| 5 | API | The consuming API for published rate plans; scope and its relationship to the dynamic price series work and the MIDAS mapping | Klaartje, All |
| 6 | Documentation | Documentation site and data dictionary; worked examples; a published JSON-LD context file; member-organization logos | Klaartje, All |
| 7 | Test Data | California rate plan examples including the Net Billing Tariff modifier; worked sample datasets; how to contribute | All |
| 8 | Other Business & Next Steps | Volunteer roles; next meeting date; action items | Klaartje, All |

## Meeting Notes

---

#### 1. Quick Hellos

- Not covered in the available summary.

---

### 2. URPX Status Update

_Reported: v0.3.0 is merged. The room agreed to fold the planned v0.3.1 into v0.4.0 rather than tag two releases, so one release carries the licence transition and the namespace move together._

- **v0.3.0 is merged.** Klaartje explained that although it was intended for public release, the release was held so that several changes could be made now rather than forcing a significant refactor later.
- **30 items on the public release checklist are complete.**
- **The version strategy was the decision of the meeting.** Klaartje proposed splitting the remaining work into v0.3.1, carrying the namespace resolution changes, and v0.4.0, carrying the major updates including the licence impacts. Don Jackson suggested combining both into v0.4.0 to streamline the process, particularly as the v0.3.1 changes would be relatively simple. Klaartje agreed to consolidate into v0.4.0, noting that the LF Energy IP scan depends on having a tagged version available.
- **The namespace moves to urpx.org**, which LF Energy now owns, replacing the current namespace built on a GitHub address. Klaartje said she did not want to go public while the identifiers carried that dependency.
- The licence transition moves specifications to the W3C Document License and datasets to CDLA-Permissive-2.0, while source and metadata stay Apache-2.0.

**Questions or concerns raised on the identifier move:**

- Not recorded separately in the available summary; the namespace discussion is captured above.

---

### 3. Ontology

- Ontology cleanup continued, including refining naming conventions.
- The move to the urpx.org namespace was described as a change made now specifically to avoid a later refactor.
- The Green Button and LF Energy mappings were updated, and draft mappings to the MIDAS standard are in progress.

---

### 4. SHACL Rules

- Not covered in the available summary.

---

### 5. API

- API work at this point is minimal and consists mainly of drafting tasks. No design work is under way and nothing else is gated on it.

---

### 6. Documentation

- Website documentation is being prepared for the public site at urpx.org.
- **A JSON-LD context file is planned**, so an implementer does not have to declare data types at the top of every file.
- Navigation and layout of the documentation site need work, including how the generated data visualizations are navigated.
- **The Green Button Alliance logo** was approved for the contributor page, with Don Coffin confirming the board's decision and Jeremy to provide the correct version.
- Members were asked to read the documentation and site content for unedited generated wording and to submit pull requests for improvements.

---

### 7. Test Data

- Klaartje proposed a separate URPX sandbox repository to hold contributed test data sets, kept apart from enterprise-grade datasets to avoid liability, with clear rules of engagement for contributions.

---

### 8. Other Business & Next Steps

- **A task and specification system is now in use** for the work on the standard, so contributions can be assigned and tracked and participation can extend beyond Flux Tailor.
- **Where to contribute.** Work in progress is tracked in the `dev-docs/tasks/` folder of the URPX repository, where contributors can add a task or pick one up. It is a lower barrier than filing an issue for anyone working with an assistant. One standing expectation goes with it: whatever you submit, you have written and reviewed it yourself. Drafting with a language model does not transfer that responsibility. Submissions should be concise, accurate and actionable rather than long and generated, because review time is the scarce resource here.
- Bruce was invited to review the specifications and the dynamic pricing work in the development documents.
- Don Coffin requested a one-on-one with Klaartje on the Green Button mapping and standards integration.
- A draft mapping from URPX to OpenADR exists; Klaartje offered to coordinate with Don Coffin on it.
- The public launch is expected in the coming weeks, including a blog post for the LF Energy newsletter.
- Action items are recorded in the table below.

## Action Items

| # | Action | Owner | Due |
| :---- | :---- | :---- | :---- |
| 1 | Merge the v0.3.1 work, which includes the licence transition, and tag it for the LF Energy IP scan | Klaartje | |
| 2 | Work with LF Energy to move the namespace to urpx.org and set up an independent automation identity for generated content, as part of the v0.4.0 release | Klaartje | |
| 3 | Reach out to LF Energy to schedule the IP scan for the tagged version | Klaartje | |
| 4 | Set up a dedicated URPX sandbox repository for contributed test data sets | Klaartje | |
| 5 | Finalize and publish the urpx.org website for the public launch | Klaartje | |
| 6 | Review and improve the navigation and layout of the documentation website | Klaartje | |
| 7 | Set up a one-on-one with Klaartje to review and add to the Green Button mapping | Don Coffin | |
| 8 | Review the draft mapping to OpenADR and coordinate with Klaartje | Stefanie | |
| 9 | Review the specifications for highly dynamic pricing and give feedback | Bruce | |
| 10 | Review the draft blog post for the public launch and give feedback or contributions | Working Group | |
| 11 | Read the documentation and website content for unedited generated wording and submit pull requests | Working Group | |

## Materials for review

- v0.3.0 release notes: https://github.com/urpx-org/urpx/blob/main/documentation/pages/urpx-release-notes-v0.3.0.md
- The standard: https://github.com/urpx-org/urpx
- Updated site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/main/dev-docs/reports
- Contribute tasks and examples: https://github.com/urpx-org/urpx/tree/main/dev-docs/tasks
- Launch announcement drafts: blog https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-blog-post.draft.md · newsletter https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-newsletter.draft.md

---

