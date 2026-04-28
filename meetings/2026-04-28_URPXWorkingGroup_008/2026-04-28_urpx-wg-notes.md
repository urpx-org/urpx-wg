# Utility Rate Plan Exchange (URPX) Working Group Meeting \#008

#### Date: 2026-04-28 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | URPX LF Energy website, urpx.org website review, member contributions, semantic web learning progress, IP scan in progress, URPX v0.2.0 candidate. Discussion: Aiming towards May 12th public release. | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions. Discussion: updated ConditionLogic to ConditionExpression, expanded its use in URPX. | Una, Klaartje, All |
| 4 | Test Data Review | Review test data examples and validation against ontology. Discussion: test data submissions through PR. | Klaartje, Una, All |
| 5 | SHACL Rules | Overview of SHACL validation rules and constraints. | Una, All |
| 6 | Documentation | Status updates, documentation updates needed, questions from materials review | Klaartje, All |
| 7 | Other Business & Next Steps | Next meeting date/time, volunteer roles status, action item assignments. | Klaartje, All |

## 

## Meeting Notes

---

#### 1\. Quick Hellos

- Quick Recap  
- welcome any new or returning participants

Attendees:
Klaartje De Schepper (KDS)
Una Smithsimon (US)
Bruce Nordman (BN)
Don Jackson (DJ)
Dai Lin (DL)
Danny Zimny-Schmitt (DZS)


Notes:
- KDS notes that there are no new members today, DJ will be attending the second half of the meeting

---

### 2\. URPX Status Update

- URPX LF Energy website is live: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- URPX.org website draft review
- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status
- URPX v0.2.0 candidate
- IP scan still in progress
- **Discussion:** Aiming towards May 12th public release.

Notes:
- KDS shares that recent updates to URPX include updates to condition modeling
- KDS confirms we are still working on the IP scan of URPX
- KDS explains current license for URPX is an Apache 2.0 license for Flux Tailor's contribution, URPX will switch to a W3C license once made public
- KDS shares we are hoping to be able to release the standard publicly by May 12th and are seeking feedback so we can have a smooth approval process
- KDS provides a brief walkthrough of the URPX repository structure on current v0.2.0-candidate branch
- KDS provides walkthrough of new AGENTS.md and CONTRIBUTING.md files at the root of the URPX repository, which provide guidelines for humans and AI agents to ensure contributions meet the standards we expect from contributors and ensure contributions are digestible for maintainers.
- KDS highlights the section of CONTRIBUTING.md on adjectives that may be read as very negative, she explains that AI agents may use these words but that for URPX contributions, descriptions must be constructive and avoid negativity
- KDS highlights use of word Tariff in a GitHub Issue that was submitted, and emphasizes the importance of the consistent use of the word rate plan when discussing URPX.
- DZS confirms that he has found it simpler to stick to a single term, rate plan, to avoid introducing confusion with "tariff."
- KDS explains that a directory was created on a branch with an open pull request, that in order to avoid wild growth of directories within the repository, we request a Github Issue submission or discussion with the WG.
- KDS explains that review is currently handled entirely by the Flux Tailor team, and asks whether any WG members could volunteer to aid with review, especially with test data.
- DZS asks for an overview of the test data that has been submitted.
- KDS provides walkthrugh of test-cases/ directory, showing the presence of assets/ and data/ with both PDF and JSON-LD URPX instances, and explains the review should ensure compliance with ontology using SHACL for validation. KDS explains that we also expect that anyone submitting test data has already run SHACL validation, and that the test data review process also includes confirming that information in the JSON-LD test data instance matches the content of the accompanying tariff book PDF. 
- DZS asks about the level of technical expertise required for review
- KDS says we can include instructions that allow a less technical user to use an AI agent to run SHACL validation and review results.
- DZS says he would like some support getting set up to review test data and would like to help review moving forward
- KDS thanks DZS and confirms that she will follow up with him so he is set up to review test data.
- DL requests an example of the review process for test data submissions
- KDS confirms that in the next meeting, she can provide a walkthrough of the test data review process as a clear, repeatable workflow to make it easier for WG members to contribute to review mvoing forward.
- KDS shares that Don Jackson has found over 80% coverage of rate plans he has tried to model using the URPX model, which is great, but also that his LLM was allowed to make commits and erroniously made public URPX test data. She requests that WG members with access to this private repository do not share any URPX content publicly until the full standard is released publicly so we can ensure a cohesive release of a comprehensive model by the whole working group, instead of released by individuals.

---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale
- **Discussion:** updated ConditionLogic to ConditionExpression, expanded its use in URPX.

Notes:
- US explains the updated ConditionExpression model from the previously shared ConditionLogic model and explains that the documentation page urpx-condition-modeling.md is available for WG review in the URPX repository on branch v0.2.0-candidate, containing a thorough explanation of the model and its use in URPX, a diagram of the model, and sample JSON-LD implementations.

---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review
- **Discussion:** test data submissions through PR.

Notes:
- KDS explains that the PGE E-ELEC test case on branch v0.2.0-candidate will be update to align with the v0.2.0 ontology and SHACL model.
- KDS proposes that we make it possible, when we merge a new ontology version to the main branch of the URPX repository, to have test data that is not yet updated. She adds that URPX v0.2.0 introduces a property to allow test data to directly reference which ontology version it complies with.
- US confirms that could work as long as we ensure that when we create a new version tag, we only include test data that is up to date with that ontology version in that release.
- KDS suggests we could create a GitHub Issue listing the files that are known not to be up to date, and members could pick up that issue as a task to update test data even if they were not the initial submitter.

---

### 5\. SHACL Rules

- Overview of SHACL validation rules posted to repository  
- Key constraints and their purpose  
- Questions and feedback from members' review

Notes:
- KDS shares that the v0.2.0-candidate branch of the URPX repository will contain SHACL that is up to date with the v0.2.0 URPX model.

---

### 6\. Documentation

- Status updates on documentation materials  
- Documentation updates needed  
- Questions from members' github materials review  
- Github workflow feedback and process improvements

Notes:
- KDS shares there will be updates to documentation pages to reflect URPX v0.2.0 model updates.
- KDS asks which parts of documentation material WG members would be able to help review and update to prepare to go public.
- DL asks the timeline for review, KDS explains our goal is to complete review in the next two weeks, so we can get WG approval across the board and make URPX public by May 12th.
- DL says she is happy to review overview documentation pages and some of the technical pages that she feels comfortable with, asks whether we can make a spreadsheet for review sign-up per file by working group members.
- KDS agrees that we can create a tracking spreadsheet for review as DL requested, and asks DL to review API spec page as that is highly technical material she may already be comfortable with, DL agrees.
- KDS mentions the FAQ page as easy for review and a good place for WG members to add questions that they may have had during this process, BN says he will perform review of the FAQ.
- US shares that the change log and design decisions files are good resources to review and update documentation pages and test data, as each of these documents list every change made to the ontology by date, these files can be used for either manual or AI-assisted updating.
- DL asks how KDS would like changes to be made to documentation pages, KDS says that if you are certain of the change that needs to be made, you may create a pull request (PR) with your updates, and other WG members can comment inline on the PR if they have additional comments, notes, or updates to request.
- KDS explains that if you are uncertain of your update, it may be created as a GitHub Issue, but our preferred method is PRs.
- KDS asks DZS whether he can handle review and update of urpx-tutorial for building a rate plan, and he confirms he is comfortable doing so as it overlaps with his work on URDB at NLR.

---

### 7\. Other Business & Next Steps
- **Discussion and Decision:** Path towards ontology acceptance as public working group draft
- Aiming to have the V0.2.0 version and IP scan updates in over the next week and aim to call a vote in the April 28th meeting to accept V0.2.0 as formal draft URPX W3C standard
- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting

Notes:
- KDS shares that we will reach out to folks who may not have attended recently for review of the standard and approval before publicizing.
- KDS provides a high level overview of the URPX repositories. Within the uurpx-org organization, she explains that we have three repositories: urpx-website contains materials from urpx.org which includes our documentation materials from the urpx repository in a human-digestible format for less-technical users who may not want to navigate GitHub to explore URPX, urpx-wg contains agendas and meeting notes for our WG meetings, and urpx is the currently private repository containing the URPX model that we hope to make public by May 12th.
- KDS shares that we will include in the urpx repository some basic language that WG members can use to aid in a coordinated outreach campaign upon launch.
- KDS lists the LF Energy Slack channel and the DER taskforce Slack channel as two communities where we could share about URPX upon release, and asks members to consider other avenues for outreach upon publication.
- KDS mentions the option to perform outreach to incubators that would use this type of data and offer workshops on using URPX so they can integrate it into their models, she asks members to consider incubators who may be a good fit.
- KDS requests advice on conferences to attend or NARUC, DZS says he may be able to make an introduction, NLR is sharing at the NARUC Innovation Web Series about URDB tools. KDS thanks him for the offer of introduction and says it would be great.
- KDS also says she hopes to have regulators join the WG to serve as motivation to get utilities on board.
- DZS agrees that it has been challenging to get utilities on board but that this sounds like a great plan.
- KDS shares that Flux Tailor has soft-launched the UtiliPub product which is based on the URPX data model, KDS shares that WG members can learn more on Flux Tailor's website, fluxtailor.com.
- KDS says we will wrap up the meeting a few minutes early, she looks forward to reaching out to members in the next week with the 0.2.0 model for review and approval so we can go public live in the next meeting.
- DZS asks how requests for changes or erros should be made during documentation review, KDS shows an example of a PR and how to submit inline comments on an open PR, and also the option to provide an overall comment on a PR.
- DZS says this feature is new to him, KDS offers to meet separately to walk him through the github workflow in more detail, he agrees.