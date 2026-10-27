---
id: minutesurpx20260929
title: "URPX Working Group #018 minutes (2026-09-29)"
desc: "Completed minutes for meeting #018, written from the Zoom transcript and corrected summary. Records the emissions scope discussion with Stephen Suffian, the release and repository status, the data sandbox approach, the API and validation check-ins, the discussion of highly dynamic prices, and the action items. Draft for the chair to review and publish."
updated: 1792972800000
created: 1792972800000
author: "Draft for the chair to review + publish"
---

> Draft for the chair to review and publish to the public working-group repository. It replaces the empty notes draft currently published there. The Zoom summary should be replaced with this text.

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#018

#### Date: 2026-09-29 11.30AM US ET (8.30AM US PT)

**Attendees:** Klaartje De Schepper (Flux Tailor, chair), Bruce Nordman (Lawrence Berkeley National Laboratory), Don Jackson, Stephen Suffian (WattCarbon), Blade Chapman (Apple Inc.).
**Notetaker:** No volunteer note-taker; minutes written from the meeting recording.

Stephen Suffian joined for the first part of the meeting and left partway through the emissions discussion for a standing call. Blade Chapman attended for the first time.

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Recap; welcomes; volunteer note-taker | Klaartje, All |
| 2 | URPX Status Update | Repository moves, then the v0.5.1 tag and the IP review. Diagram updates to review | Klaartje, All |
| 3 | Ontology | A discussion: what URPX should and should not cover, with emissions as the live case | Klaartje, All |
| 4 | SHACL Rules | No shape change. How validating against URPX has gone for you | Klaartje, All |
| 5 | API | Requirements gathering. What you would need | All |
| 6 | Documentation | Licenses, and the site after the split | Klaartje, All |
| 7 | Test Data | Shipped examples; the community data repository | All |
| 8 | Other Business & Next Steps | A discussion: what we build next, and where you would like to be involved. Volunteer roles; next meeting | Klaartje, All |

## Meeting Notes

---

#### 1. Quick Hellos

- Blade Chapman introduced himself. He works on the Energy Services team at Apple, which builds home energy features in the Home app
- Klaartje offered the shared notes document to anyone who wished to take handwritten notes, and said human-written notes are better than generated ones. No one volunteered.
- The agenda was taken out of order so that Stephen Suffian could join the emissions discussion before he had to leave.

---

### 2. URPX Status Update

- **The main branch reflects v0.5.1.** Klaartje planned to tag it later on the day of the meeting. The license is now the W3C license, declared consistently across the repository. She expected the standard to go public that day or the next.
- **Repository split.** Klaartje had emailed members about moving material out of the standard's repository. For anyone with a clone, nothing in the standard moves. Only the development documents and the test cases go to their own repositories. She planned to make the move shortly after the meeting.
- **Documentation site and diagrams.** Klaartje walked through the site preview. The generated diagrams have been improved, with fewer crossing lines, and can now be zoomed in and out. She asked members to say so if a diagram looks wrong. The PG&E example diagram was shown as an illustration of how much structure a real rate plan carries. The site is due to go live under urpx.org once v0.5.1 is tagged, and the term identifiers in the namespace are to resolve there as well.
- **Data dictionary.** Don Jackson has submitted two pull requests against the data dictionary page. Klaartje is reviewing them and will fold in what she can.
- **Examples and their origin.** The PG&E and Con Edison rate plans are the two converted to JSON-LD so far, both extracted from the tariff books. The Con Edison example is still being completed. It looks simpler than the PG&E one only because it does not yet carry all of the statement charges. The JSON-LD files currently sit in the test cases folder and are to move to the data sandbox. Klaartje credited Don Jackson with the time-of-use C example. The datasets now record the name of the publication platform and the company that generated the dataset, so a dataset's origin is visible.
- **Who publishes a rate plan.** Blade Chapman asked whether PG&E contributed its rate plan to build the example. Don Jackson clarified that the rate plans he has modeled were built from PDFs he fetched himself, with an assistant, and that PG&E had no part in it. Klaartje agreed and added that the publisher relationship in URPX is explicit: only the utility can be the publisher of a rate plan. The goal is that utilities eventually publish their own rate plans so that everything is verified at the source, and the author recorded on a dataset shows who modeled it.
- **Release announcement.** A newsletter blurb for LF Energy and a blog post are drafted. Klaartje will post on LinkedIn when they go out and invited members to spread the word.

---

### 3. Ontology

- **No vocabulary change since the last meeting**, apart from the publishing vendor property on datasets.

**Discussion: what URPX should and should not cover, with emissions as the live case.** Klaartje asked whether URPX should carry emission factors, or volumes of gases. Stephen Suffian shared the thinking behind a draft he has started, which he offered to share as a Google Doc.

- **"Green" rate plans.** Stephen's draft encodes the choices a customer has on a green tariff, such as the percentage renewable, gas or solar. He hesitated to put actual emission rates in the model, because the carbon intensity of a fuel or of electricity is measured in many ways, with marginal and average intensity and different fuel factors among them, and downstream users hold differing opinions about the sources. His proposal was to stop at the proportional description of what a customer signed up for. Klaartje summarized this as the contracted resource mix, with the addition, from his draft, of whether renewable energy credits can offset what is in that mix. Stephen noted that green tariff plans differ in kind. Community choice aggregators procure supply, while some retail providers purchase renewable energy credits.
- **What happened afterwards.** Don Jackson asked how the commitment a provider makes on a green tariff relates to what actually happened. Klaartje said the outcome after the fact belongs with customer data, which is the rate plan combined with usage. Stephen agreed and linked it to the LF Energy customer data specification working group. Klaartje described the relationship as a recipe, which is URPX, and the food that was delivered and eaten, which is the customer data.
- **How to compute emissions.** Stephen asked whether the accounting for supply and delivery should sit in the specification, or whether a user would take the supply rate plan and the delivery rate plan from URPX and make their own accounting choices. Klaartje's answer was that URPX should not state what the emissions were, since that depends on choices such as a 20-year or 100-year horizon and which list of factors is used. URPX should instead describe how the calculation is made, in machine-readable form, so that everyone calculates in the same steps and can explain their method. Stephen's worked example was a customer on an 80 percent wind tariff, who takes consumed intensity for the remaining 20 percent and zero for the 80 percent. The consumed intensity itself is a choice made outside URPX. Klaartje agreed that this would make URPX outputs interoperable with an emissions model, and said existing standards for describing the methodology would be reviewed for naming alignment.
- **Supply and delivery.** Klaartje explained that a customer with retail supply has two rate plans: a delivery rate plan from the distribution provider and a supply rate plan. Delivery is already partly covered. Stephen's work concerns supply. The two would need to be combined, so that a customer buying green supply sees the benefit and an accountant can see the total.
- **Location-based and market-based emissions.** Stephen distinguished emissions from the consumed grid mix, which two neighbors share, from market-based emissions, which differ with the green tariff each has signed up for. Bruce Nordman observed that customers on different tariffs would then simply carry different greenhouse gas signals.
- **Dynamic operation.** Bruce Nordman described two different contexts. His own work is the dynamic operation of devices, where a marginal greenhouse gas signal is sent alongside the price, as in OpenADR 3 and as he added to IEEE 2030.5. The customer multiplies the signal by a price per ton and adds it to the retail price. Emissions accounting after the fact is a different exercise, and the two may diverge. Stephen agreed and said WattCarbon works in both.
- **Apple's position.** Asked by Klaartje, Blade Chapman said Apple's features are focused on grid mix, which is location-based and does not account for supply. Apple is interested in how electricity cost aligns with cleanliness for an individual's rate plan, since the two signals are separate today and Apple would like to bring them together once it understands the rate plan. 
- **Modeling what is needed.** Klaartje added that URPX can set what data becomes available. The model should work from the requirements, including where data was not historically available, in the same way URPX introduces the rate plan as the thing that strings together the static tariff publications.
- **Next steps.** The discussion continues at a later meeting. Stephen will move his initial proposal to the development repository and share it. Klaartje invited members to send green rate plans as test cases.

---

### 4. SHACL Rules

- **No shape change.**
- Don Jackson said validation is useful and a key part of his workflow. He noted that his assistant tends to search structured data with text tools, which works poorly, and that it does much better when reminded to use SPARQL. Klaartje agreed that SPARQL is the right tool for RDF data, with or without an LLM.
- The documentation has a learning and education section with a semantic web guide. 
- The ontology and JSON-LD are in triples. The API design in draft also allows for data in a more traditional tabular form.

---

### 5. API

- Still requirements gathering. Klaartje again asked for requirements for an API that publishes rate plans and modifiers, including anything members have found unwelcome in APIs they have used. The draft design is in the repository.

---

### 6. Documentation

- Klaartje asked members to flag any part of the urpx.org documentation that still reads as machine-written. The material was produced with assistance from tools and she reviewed it closely, but may have missed passages. She noted a few documentation suggestions from Don Jackson.
- The agenda items on licenses and the site after the split were not discussed beyond the points under item 2.

---

### 7. Test Data

- **Sandbox approach.** For the data sandbox, the position agreed at the last meeting stands. Deposited datasets receive only basic SHACL validation and carry clear disclaimers that they are experimental and not for production use. The group will not curate at length. The review process for submitted datasets is not fully defined, and a volume of submissions would be a welcome problem to solve.
- **Don Jackson's closed pull requests.** Klaartje noted that Don Jackson had closed his pull requests containing test datasets and asked whether he would deposit them in the new sandbox. Don replied "Potentially, yes."
- **Larger datasets.** Klaartje intends to invite organizations that hold large bodies of rate plan data to try transforming it into URPX. She has found that most existing models are less detailed than URPX, so a transformed dataset often reduces to a summary price. The exercise is still helpful.
- **Invitation to submit.** A message to the committee at large will invite members to submit datasets once the new sandbox is ready.

---

### 8. Other Business & Next Steps

**What we build next.** Klaartje said the emissions work is important and that highly dynamic prices, which interest Bruce Nordman and Don Jackson, are still on the list. She asked how the group would like to focus and contribute after the public release.

**Highly dynamic prices.**

- Bruce Nordman asked whether Don Jackson already has a way to stream prices. Don said he computes a stream of prices from a scenario, meaning a rate plan together with what else is needed. Prices for a flat or time-of-use rate plan can be computed from URPX alone. What a URPX rate plan would look like for PG&E's hourly pricing pilot is unclear to him, because a static document cannot state future prices at publication. Past prices might be captured from the stream. He linked this to machine-readable value expressions.
- Bruce Nordman suggested that if URPX defines standard price server functionality, URPX could both put out streaming prices in that form and take in prices from an external price server. The key would be to define a boundary on what streaming prices can contain. A demand charge, for example, could appear in a URPX rate plan but would not be part of a price server dataset. He also asked how far URPX should go in calculating prices, as against taking them in or putting them out. The computation might be as simple as a wholesale price stream from a defined location plus ten cents, or very complicated.
- Don Jackson's view is that a rate plan should say what the prices are. For a highly dynamic rate plan the document cannot give the future price, but it can state how to compute it, and that would be valuable. A user would follow the link to the dynamic part and use the URPX description to compute the price.
- Klaartje agreed that the method for computing a price belongs in the recipe, including the case where the price is calculated from a wholesale price, which URPX does not yet define. She said most people want to know future prices, and that today each party predicts them in its own custom way, so the methodology should be part of the standard. She invited members to bring extremely complicated cases so that the design can be tested against edge cases, and said the existing condition expression logic, with its left and right operands, can largely be reused.
- Klaartje will share what has been done so far with Bruce Nordman and Don Jackson. The group will discuss scope and who can work on it at the next meeting.
- Bruce Nordman asked what to read in advance. Klaartje pointed to the specs and tasks folders in the development repository, which hold draft material on price series, how prices are retrieved, and the transform for MIDAS, which relates to the PG&E rate Don Jackson mentioned. She explained that a spec holds a design and a task implements part of it or develops the design further, and that files follow a decimal-style naming convention that suits working with AI tools. The README of the development repository will explain the system.

**Release and outreach.** Klaartje expected more new members at the next meeting.

**Slack.** Klaartje offered Blade Chapman access to the working group's Slack workspace and will invite him at his Apple email address. Bruce Nordman introduced his focus on OpenADR 3 and price communication and offered to talk with Blade, who said he would connect Bruce with colleagues interested in OpenADR.

**Next meeting.** In two weeks, on the standing fortnightly schedule.

**Not taken up.** The volunteer roles of co-chair, secretary and community outreach, and the action items carried from meeting 17.

**Where to contribute.** Contributions and proposals can be developed in the `urpx-org/urpx-dev` repository, in its specs and tasks folders, where members can add and pick up tasks. Contributions are written and reviewed by the person submitting them. Drafting with an LLM does not remove that responsibility, and submissions should be concise, accurate and actionable. The chair and maintainers have limited review bandwidth, so please do not add to the review burden. The working group's [CONTRIBUTING.md](https://github.com/urpx-org/urpx/blob/main/CONTRIBUTING.md) and [AGENTS.md](https://github.com/urpx-org/urpx/blob/main/AGENTS.md) set out the same expectations.

---

## Action Items

| Owner | Action | Due |
| :---- | :---- | :---- |
| Stephen Suffian | Move the initial emissions and green tariff proposal to the development repository and share it with the group | |
| Klaartje De Schepper | Move the development documents and test cases into their own repositories, `urpx-dev` and `urpx-data-sandbox` | Shortly after the meeting, 2026-09-29 |
| Klaartje De Schepper | Tag v0.5.1 and take the standard and documentation site public | 2026-09-29 or 2026-09-30 |
| Don Jackson | Deposit the datasets from his closed pull requests in the new data sandbox (confirmed as "potentially") | |
| Klaartje De Schepper | Review Don Jackson's two data dictionary pull requests and fold in what fits | |
| Klaartje De Schepper | Share the highly dynamic prices work so far with Bruce Nordman and Don Jackson | |
| Klaartje De Schepper | Explain the specs and tasks conventions in the README of the development repository | |
| Klaartje De Schepper | Invite Blade Chapman to the Slack workspace at his Apple email address | |
| Klaartje De Schepper | Invite organizations holding large bodies of rate plan data to try transforming it into URPX | |
| Klaartje De Schepper | Message the committee at large to invite dataset submissions once the sandbox is ready | |
| Klaartje De Schepper | Send out the LF Energy newsletter blurb and the blog post for the release | |
| Blade Chapman | Gather how Apple interacts with rates and bring back requirements for the API design | |
| Working Group | Send green rate plans as test cases for the emissions work | |
| Working Group | Send requirements for the API that publishes rate plans and modifiers | |
| Working Group | Bring extremely complicated dynamic price calculations to test the design against | |
| Working Group | Submit more datasets to the data sandbox once it is ready | |
