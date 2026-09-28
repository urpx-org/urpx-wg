# Utility Rate Plan Exchange (URPX) Working Group Meeting \#017

#### Date: 2026-09-15 11.30AM US ET (8.30AM US PT)

**Attendees:** Klaartje De Schepper (Flux Tailor, chair), Don Jackson.
**Regrets:** Green Button Alliance participants, at the LF Energy Summit in Berlin.
**Notetaker:** No volunteer note-taker; minutes written from the meeting recording.

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker for today's minutes | Klaartje, All |
| 2 | URPX Status Update | Where the release stands, and what remains before the standard goes public. Then a discussion: how the repositories should be laid out when the standard goes public | Klaartje, All |
| 3 | Ontology | No vocabulary change since v0.4.0. Where the design work is heading | Klaartje, All |
| 4 | SHACL Rules | No shape change. What validating against URPX has actually been like for you | Klaartje, All |
| 5 | API | Still requirements gathering. What you would need from an API over published rate plans | All |
| 6 | Documentation | Term identifiers now resolve at urpx.org, one document per term. One build produces the documentation site and the namespace pages from a single release tag. Member-organization logos | Klaartje, All |
| 7 | Test Data | The shipped examples. Then a discussion: what we should ask of a community data submission | All |
| 8 | Other Business & Next Steps | Volunteer roles; action items carried from meeting 16; next meeting date | Klaartje, All |

## Meeting Notes

---

#### 1. Quick Hellos

- Two participants. The Green Button Alliance participants who usually join were at the LF Energy Summit in Berlin, so the meeting was run as a working conversation rather than a presentation.
- No volunteer note-taker. These minutes were written from the recording.

---

### 2. URPX Status Update

- **The current tag is v0.5.0.** v0.5.1 carries the license transition and had not been tagged. It stands as a candidate pull request in the URPX repository, and Klaartje reported she was about to tag it. The agenda, written before the meeting, described that tag as already made. It had not been.
- **The LF Energy IP review follows the tag.** The tagged tree goes to LF Energy, and the review confirms that copyright and attribution are in order. It is also part of Flux Tailor's due diligence under the agreement covering the transfer of the standards material to LF Energy. Nothing had been submitted for review at the time of the meeting, and the agenda's statement that it had been was wrong. From the review onwards, URPX is a fully open source standard.
- **Publication is wired up.** Tagging a release now publishes the documentation site for that release, and creates the namespace pages for it if they do not yet exist, with proper dereferencing of the term identifiers. It runs on Semantic Flow, contributed to the project by Dave Richardson, who works with Flux Tailor as fractional CTO.
- **A written release workflow follows.** Klaartje will document the full release procedure so that somebody other than the two people who built it can run the next release. Don Jackson's point was that a defined process has to exist in any case. Tagging a release should not depend on any one person once the standard is open source.
- **OpenSSF badge.** Klaartje has begun looking at the OpenSSF badge requirements, which bear on what project stage URPX is assessed at. The current setup already meets many of them, and a high badge level at first evaluation shortens the work LF Energy would do to prepare the standard for ISO ratification. Don Jackson noted that ISO processes bring their own bureaucracy.
- **Repository history.** Whether the repository's older material is carried forward as it stands or condensed before the public flip was raised and left open.

**Discussion: how the repositories should be laid out when we go public.** The chair walked the four kinds of material the single repository holds today: the standard, the curated test cases, the design and process record, and community contributions. What the room reached on each question is below.

1. **Does the design and process record belong beside the standard, or in its own repository?** Its own repository. Don Jackson's reasoning was that the design and process record is a development activity and should read as one. The development documents folder moves out of the standard's repository, and the older design decision pages held at the top level of the standard's repository move with it. Everything that is process rather than the standard itself comes out.

2. **Do the curated test cases stay with the standard?** No move was proposed and none was agreed. The discussion turned instead to how a dataset qualifies for the curated set that the documentation site renders. That selection has been made by Flux Tailor to date, and no rule for it was settled.

3. **Are `urpx-lab` and `urpx-data-sandbox` the right names?** The development repository is named `urpx-dev` rather than `urpx-lab`. Don Jackson proposed the change: `urpx-lab` is a good name, but for a different repository. `urpx-lab` is reserved for an actual lab environment later, which is where Klaartje would want to host wider collaboration and work aimed at contributors who do not write the technical materials but who carry the standard to public service commissions. The sandbox keeps `urpx-data-sandbox`, with "data" in the name because a sandbox could otherwise be a different kind of sandbox. Don Jackson offered `urpx-contrib` as an alternative and questioned whether "data" was needed, then left the choice to the chair. `urpx-wg` is unchanged.

4. **What does a split make harder?** Not reached. The question was not put and no answer was given.

**All repositories are public.** Don Jackson's position was that a public standard should be developed in public. Klaartje noted that a private repository would carry an additional cost and a seat limit on the LF Energy account, so keeping one private may not be an option in any case.

---

### 3. Ontology

- **No vocabulary change since v0.4.0.** The work since then has been the move of the namespace from the earlier GitHub-based location to `urpx.org`, in readiness for the DNS changeover. That changes how a term is written and does not change the model.
- The greenhouse gas emissions and green rate plan work listed on the agenda was not taken up.

---

### 4. SHACL Rules

- **No shape change.**
- **What the shapes cover today.** They are a base layer of core validation that runs over anything in the ontology. They do not carry commodity-specific content rules, for example a rule that a water rate plan cannot express a quantity in kilowatt hours. That layer would have to be built before conformance could speak to the content of a submission as distinct from its structure. This is the reason the sandbox submission bar in section 7 is set where it is.

---

### 5. API

- Not taken up in this meeting.

---

### 6. Documentation

- **The ontology namespace is hosted from `urpx.org`**, made possible by Semantic Flow. Klaartje noted that some longer established standards have not got this working.
- **The documentation site has further updates planned**, including the About page, which is generic as it stands. The member-organization logos are on it, but their relative sizes are out of balance and they should sit higher on the page.
- **Member-organization logos.** Klaartje invited Don Jackson to send a logo, or whatever representation of his contribution he prefers, and will add it. He agreed to send one and asked that nothing wait on him. No deadline was set.
- **The curated examples have grown large** and are hard to navigate on the site. A long series of prices belonging to one price set currently renders as a single horizontal run. That needs work before it is useful, though the examples are already worth having for showing the difference in structure between rate plans at a glance.
- **Diagrams.** The automatically generated data dictionary diagrams have not improved. A per-diagram mechanism exists to tune generation parameters, so the work is deciding which parameters to tune for each diagram and which rules always apply, such as avoiding crossing lines, which a network graph cannot always avoid. Klaartje pointed to the SPDX model diagrams as the quality she is aiming for, and intends to ask how they were produced; her reading is that they were laid out by hand. The plan is to lay out a reference diagram manually as the gold standard, then find a way to make the automated generation match it. The generated diagrams ship as they are in the meantime.
- Don Jackson suggested working the generated graph output with an assistant, and noted that for rendering quality Mermaid can be easier to get a good result from than Graphviz. Klaartje confirmed both are in use, including a Mermaid diagram in the tutorial.
- The documentation site preview link was shared in the chat: https://fictional-chainsaw-y74j7yq.pages.github.io/

---

### 7. Test Data

**What the sandbox is for.** A place where people can deposit datasets with some level of validation on them. It is explicitly not a curated community library that catalogs each dataset, records who created it and makes it searchable. That is a separate project and is out of scope for now. The sandbox holds draft datasets. It does not validate the accuracy of the numbers. It confirms that the datasets work for testing. The repository will carry plain disclaimers saying so.

**Where a contribution goes.** A contribution to the standard is a pull request against the standard. Rate plan data that is not yet ready for the sandbox stays on a branch in a pull request until it is. Anyone can fork the repository and work as they wish. What sits on the sandbox's main branch carries only what the disclaimers claim for it.

What the room reached on each question is below.

1. **Is the two-gate bar too high or too low for something you would actually submit?** Settled as automated validation only. A submission is validated by CI against the SHACL shapes, and on a pass any member of the approvers group can merge it. The second gate, a named reviewer approving content, was dropped for now. The work is significant, somebody has to do it, and a content sign-off carries a degree of liability, particularly while the shapes cannot check commodity-specific content. Don Jackson agreed. A peer review mechanism can be added later if the community grows.

2. **What does a submission need to carry so that somebody else can trust it?** Agreed:
   - Whether the dataset was built from a real dataset.
   - Effective dates and, separately, service period dates, for the coverage of the data. The two are distinct, and naming only "effective dates" is confusing.
   - Jurisdiction, at least the utility and the state, so the set can be searched.
   - The source document itself, captured alongside the data rather than only linked. Utility hosting is not reliable, and a reorganized site leaves no forwarding. Capture the download date with it, because files with the same name downloaded on different dates can be entirely different documents.
   - Don Jackson's own sets carry a README, the scraped source document and the data files per case, which he offered as a starting point for what a submission should look like.

   **Directory structure.** Country first, then the state or equivalent by its ISO subdivision code, then the utility, then the commodity type, so that gas and electric sit under the same utility. Utility-specific identifiers such as New York service classes do not become directory levels; they are metadata on the dataset, so the structure holds across jurisdictions.

   **An organization list as the skeleton.** URPX can express a dataset that lists organizations, and that list can form the skeleton of the directory structure. No example of this exists yet. For the sandbox, Klaartje would like to publish one for US electric utilities as a wish list to work against.

3. **Does the disclaimer read as fair?** Not reached. The draft wording was not read out or reviewed. What was agreed is that the repository carries prominent disclaimers and makes no claim about the accuracy of the data.

4. **Should a sandbox dataset ever be promoted into the curated test cases, and on whose judgment?** Discussed, not decided. Promotion has so far been Flux Tailor deciding what appears on the urpx.org site, and no rule replaced that. The concrete step agreed instead was seeding.

**Seeding.** Klaartje proposed Don Jackson's existing test case set as the first datasets in the sandbox, and to try to get some of them onto the documentation site as further examples. Don Jackson agreed to the versions he has already shared being ported. He does not want to publish his own set until he has reworked it to the released version of URPX, which is several weeks out for him. Klaartje also expects to add a number of New York State examples, and is working out which rate cases are worth joining at the modeling stage.

---

### 8. Other Business & Next Steps

- **Branding and trademark.** Don Jackson asked whether URPX is trademarked. The logo is, in principle. Klaartje's view is that the standard should not be: the direction is a certification program with a compliance badge, where the badge is legitimate once certification is passed, and using it without passing, or while validation shows non-compliance, is on the party using it. She contrasted this with tightly protected marks that leave people unsure whether they may even reference a standard in a presentation. Branding is managed under LF Energy.
- **Community launch and workshops.** Once the sandbox exists and holds datasets to work with, Klaartje would like to run a series of workshops at venues such as cleantech incubators and libraries, so that people can work with URPX datasets for their own area. Don Jackson supported it.
- **Sequence.** The repository moves, including creating the new repositories and moving material out of the standard, happen before v0.5.1 is tagged. Asked for a round-number date for the announcement that everything is live, Klaartje said the day after the meeting or the day after that, with the IP review as the remaining gate.
- **Volunteer roles and the action items carried from meeting 16** were not taken up.
- **Next meeting:** 2026-09-29, 11.30AM US ET (8.30AM US PT), on the standing fortnightly schedule. The date was not discussed in the meeting.

---

## Action Items

| Owner | Action | Due |
| :---- | :---- | :---- |
| Klaartje De Schepper | Create `urpx-dev` and `urpx-data-sandbox`, reserve `urpx-lab`, and move the development and process material out of the standard's repository | Before v0.5.1 is tagged |
| Klaartje De Schepper | Tag v0.5.1, which carries the license transition, and send the tagged tree to LF Energy for the IP review | |
| Klaartje De Schepper | Write the complete release workflow, so that a core team member other than the two who built it can run the next release | |
| Klaartje De Schepper | Work out the OpenSSF badge requirements and aim for a high badge level at first evaluation | |
| Klaartje De Schepper | Port the test case versions Don Jackson has already shared into the public data sandbox, and try to add some to the documentation site examples | |
| Klaartje De Schepper | Lay out a reference diagram by hand as the template the automated diagram generation should match | |
| Klaartje De Schepper | Add further URPX examples for New York State | |
| Don Jackson | Send a logo, or another representation of his contribution, for the About page | |
| Don Jackson | Rework his own dataset set to the released version of URPX before publishing it | |
