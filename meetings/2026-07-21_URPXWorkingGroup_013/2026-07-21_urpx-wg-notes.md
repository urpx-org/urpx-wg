

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#013

#### Date: 2026-07-21 11.30AM US ET

**Attendees:** Klaartje De Schepper (chair), Shubham Attri (California Energy Commission), Don Jackson (audio-only), Donald Coffin (Green Button Alliance)
**Regrets:**
**Notetaker:** No volunteer note-taker; minutes drafted from the meeting recording.

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap, welcome new and returning participants | Klaartje, new participants |
| 2 | Review Status | Feedback received on the v0.3.0 candidate since the last session; open questions from members' review | Klaartje, All |
| 3 | Approval to Publish | Record the working group's approval to publish v0.3.0 and authorise the license conversion and IP scan. A formal ballot is not required; the decision is recorded in the minutes, confirming the sense of the room from the last session | Klaartje, All |
| 4 | License Conversion & IP Scan | The steps between approval and publication: converting the specifications to the W3C Document License and the datasets to CDLA-Permissive, then the LF Energy IP scan of the converted materials. Publication follows once both are complete | Klaartje, All |
| 5 | Public Launch | Making the repository and the documentation site public, and urpx.org going live; where to find the published materials | Klaartje, All |
| 6 | Contributions & Test Data | California rate plan examples for the model (including the NBT modifier); how to contribute through the development-documents tasks folder; questions from members' review | All |
| 7 | Other Business & Next Steps | Volunteer roles, next meeting date, action items | Klaartje, All |

## Meeting Notes

---

#### 1. Quick Hellos

- Welcome to participants and a quick recap of where the v0.3.0 candidate stands ahead of the public release. Several participants were on audio only, so the meeting was kept light while keeping the regular cadence.

---

### 2. Review Status

- Since the 2026-07-14 session, further work landed on the v0.3.0 candidate, which is now ready to merge.
- Don Jackson's thorough reviews across every round of changes were acknowledged.
- It was noted that an identifier now sits on the rate plan version and rate plan modifier version, so a resolved snapshot carries its own MIDAS RIN. This resolves one of the two items that had been carried forward from earlier review, and connects to the MIDAS price-comparison idea under Contributions below.
<!-- confirm: Jeremy Roberts not present in transcript; verify with chair. The agenda listed his candidate review and a Green Button Alliance board presentation on 23 July, plus Don Jackson's OpenADR 3 price-server feedback — none of these was taken up in #013. Confirm whether to carry a status line on the board presentation. -->

---

### 3. Approval to Publish

- Klaartje reconfirmed the sense of the room from the 2026-07-14 session: publication does not require a formal ballot. She invited any objection during the meeting; none was raised.
- Recorded in the minutes: the working group's approval to publish v0.3.0 and to proceed with the license conversion and IP scan.

---

### 4. License Conversion & IP Scan

- On approval, the specification files convert to the W3C Document License and the dataset files to CDLA-Permissive; source and tooling files stay under Apache-2.0.
- The converted materials then go through the LF Energy IP scan. Because the newly added v0.4.0 task drafts contain proposed changes, they are part of what will be scanned.
- Publication follows once the conversion and the scan are both complete.

---

### 5. Public Launch

- All test cases raised will be merged into v0.3.0 before the tag, so they are part of the release and appear on urpx.org.
- The repository and the documentation site will then be made public and urpx.org brought live. The updated site is available for review in the staging environment (link under Materials for review).
- Website updates: the diagrams were improved and made expandable, and a prominent data-dictionary section was added. Use-case examples will also be added, following an earlier recommendation from Jeremy Roberts. <!-- confirm: Jeremy Roberts not present in transcript; verify with chair -->
- Timeline: Klaartje is aiming for a public release by the end of this week, at the latest early next week, depending on how quickly the IP scan completes and the announcement and newsletter are reviewed.
- Launch announcement drafts (blog post and newsletter) are posted to the working-group repository and open for review; members can place pull requests directly with suggested edits. Input from members who work with communications and copy is especially welcome. Klaartje plans to send these out shortly after launch, before the next meeting.
<!-- confirm: the standing logo ask (organisations that would like to be featured on urpx.org / the LF Energy landing page sending a logo) was on the agenda but was not raised in #013. Confirm whether to carry it to the next agenda. -->

---

### 6. Contributions & Test Data

- California rate plan examples, including the Net Billing Tariff (NBT) modifier, were offered by the California Energy Commission's MIDAS participants. Shubham Attri confirmed that only three intervals are currently allowed (hour, 15 minutes, and 5 minutes), and that the interval is fixed once set — if the first upload is hourly, it stays hourly.
- Shubham will review the MIDAS and highly-dynamic-pricing materials Klaartje points him to, and plans to bring questions to the next meeting and to share California price edge cases as a use case for the schema. The aim discussed was to connect URPX and MIDAS so that URPX inputs can be transformed into MIDAS inputs; the next meeting will take up the URPX-to-MIDAS mapping.
- Shubham noted that the official MIDAS documentation on GitHub now links related repositories as additional resources, and suggested adding the URPX-to-MIDAS mapping there once it is ready.
- Don Jackson noted that after the v0.3.0 release he plans to publish work he has built on URPX, including a set of modeled California rate plans; a repository name change was discussed and will be handled offline.
- Don Jackson also raised a price-comparison idea: taking a rate plan modeled in URPX, resolving its prices, and comparing them against the prices published under the same RIN on MIDAS, as a cross-check. Shubham noted this is close to their planned California use case.
- New v0.4.0 tasks and worked examples were added and are open for working-group review. The additional worked examples show how published snapshots resolve into a reconciled, rolled-up time-series rate plan version suitable for machine-readable use; the tasks reference sample instances so members can work directly from them.
- Contributions — new examples, tasks, or feedback — go through the `dev-docs/tasks/` folder in the `lf-energy/urpx` repository. Contributions are written and reviewed by the person submitting them; drafting with an LLM does not remove that responsibility, and submissions should be concise, accurate, and actionable rather than fully generated or padded, so that review stays manageable for the maintainers.
- Klaartje proposed adding contributor helper "skills" to the repository — including an ontology-aware skill for implementers — together with AI-assistant configuration guidance, and asked the group for feedback. Don Jackson and Donald Coffin shared experience with AI-assistant configuration files in their own repositories, and the proposal was welcomed.
- Donald Coffin offered to set up Zoom sessions on the Green Button mappings when that work is ready; he will send a scheduling link, and Klaartje expects to schedule in the next few weeks.

---

### 7. Other Business & Next Steps

- Volunteer roles remain open: co-chair, secretary, and community outreach.
- Next meeting: 2026-08-04 (biweekly).
- Action items are recorded in the table below.

## Action Items

| # | Action | Owner | Due |
| :---- | :---- | :---- | :---- |
| 1 | Merge the v0.3.0 candidate, then run the W3C / CDLA license conversion and request the LF Energy IP scan | Klaartje | |
| 2 | Make the repository public and bring urpx.org live once the IP scan passes | Klaartje | |
| 3 | Fold Don Jackson's California examples and the additional worked examples into the v0.3.0 release | Klaartje | |
| 4 | Point Shubham to the MIDAS-mapping and highly-dynamic-pricing materials | Klaartje | |
| 5 | Email the group with the public-release timeline | Klaartje | |
| 6 | Discuss the repository name change offline | Klaartje & Don Jackson | |
| 7 | Send a scheduling link and set up Zoom sessions on the Green Button mappings in the next few weeks | Klaartje & Donald Coffin | |
| 8 | Review the materials, prepare questions for the next meeting, and share California price edge cases as a use case | Shubham | |
| 9 | Review the blog post and newsletter drafts in the working-group repository and give feedback via pull requests | Working Group | |
| 10 | Add contributor helper "skills" (e.g. an ontology-aware skill) and AI-assistant configuration guidance to the repository | Klaartje | |

## Materials for review

- v0.3.0 candidate pull request: https://github.com/urpx-org/urpx/pull/48
- Updated site (staging preview): https://fictional-chainsaw-y74j7yq.pages.github.io/
- Reports and reviews folder (post feedback here): https://github.com/urpx-org/urpx/tree/v0.3.0-wg-review/dev-docs/reports
- Review information and sign-up sheet: https://github.com/urpx-org/urpx/blob/v0.3.0-wg-review/dev-docs/review/urpx-v0-3-0_public-release-review-wg-info-and-signup.md
- Launch announcement drafts: blog https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-blog-post.draft.md · newsletter https://github.com/urpx-org/urpx-wg/blob/main/announcements/2026-07-09.lf-energy-newsletter.draft.md

_Announcement links resolve once the drafts (staged under `announcements/`) are committed and pushed to `main`._
