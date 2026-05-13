# Utility Rate Plan Exchange (URPX) Working Group Meeting \#009

#### Date: 2026-05-12 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | URPX LF Energy website, urpx.org website review, member contributions, semantic web learning progress, IP scan in progress, URPX v0.2.0 candidate. Discussion: Aiming towards May 19th public release vote. | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions. Discussion: New ServiceBracket model for flexible ServiceTier boundaries. | Una, Klaartje, All |
| 4 | Test Data Review | Review test data examples and validation against ontology. | Klaartje, Una, All |
| 5 | SHACL Rules | Overview of SHACL validation rules and constraints. | Una, All |
| 6 | Documentation | Status updates, documentation updates needed, questions from materials review. | Klaartje, All |
| 7 | Other Business & Next Steps | Next meeting date/time, volunteer roles status, action item assignments. Discussion: Path towards ontology acceptance as public working group draft. | Klaartje, All |

## 

## Meeting Notes

---

#### 1\. Quick Hellos

- Quick Recap  
- welcome any new or returning participants

Attendees:
- Klaartje De Schepper (KDS)
- Una Smithsimon (US)
- Donald Coffin (DC)
- Don Jackson (DJ)
- Bruce Nordman (BN)
- David Richardson (DR)

---

### 2\. URPX Status Update

- URPX LF Energy website is live: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- URPX.org website draft review
- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status
- URPX v0.2.0 candidate
- IP scan still in progress
- **Discussion:** Aiming towards May 19th public release vote.

Notes:
- KDS explains that Flux Tailor is not quite ready to publicize, pending IP review and license transition from Apache 2.0 to W3C, but content is very close to what Flux Tailor is confident going public with
- KDS requests review from WG this week and will share signup sheet
- DC asks why Apache 2.0 has to transition to W3C, KDS explains that is per FT's agreement with LF Energy, for open standard compliance will have W3C on the road to ISO standard.

---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale
- **Discussion:** New ServiceBracket model for flexible ServiceTier boundaries.

Notes:
- US shares presentation on new ServiceBracket model. DC asks whether there can be more than two ServiceTier objects per ServiceTiers container, and how many ServiceBracket objects may live on a single ServiceTier, US responds that cardnality for ServiceTiers>ServiceTier and ServiceTier>ServiceBracket is 1*n which is represented in urpx-shacl.ttl.

---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review

Notes:
- DJ says that he has used Claude to keep his test cases up to date with all URPX changes as they are merged to main and will ensure they are up to date so they can be merged to main in the coming week.

---

### 5\. SHACL Rules

- Overview of SHACL validation rules posted to repository  
- Key constraints and their purpose  
- Questions and feedback from members' review

---

### 6\. Documentation

- Status updates on documentation materials  
- Documentation updates needed  
- Questions from members' github materials review  
- Github workflow feedback and process improvements

Notes:
- KDS shares URPX review signup sheet for working group members, and explains that ontology and SHACL review are split into sections that align with the sections of the data dictionary. There is a section for review of test cases, and also a section for each documentation page. We are aiming for 1-4 reviewers for eahc section. 
- KDS asks DC to focus on diagrams for data dictionary, he agrees.
- KDS asks DJ which part of the standard review he would like to focus on, DJ responds that he is happy to try to help but feels like others may have deeper domain knowledge than he does. He confirms he will help review anything that is needed.
- DJ agrees to review materials on creating test data.
- KDS asks DC to review the FAQ that breaks down URPX, he agrees.
- KDS requests that DR assist in reviewing the semantic web guide documentation page, he agrees. KDS further requetss that DR review the design pricnciples documentation page and the explanation of condition expression modeling and he agrees.
- Getting started, tutorial, and test cases documentation pages are assigned to DJ for review.
- Data dictionary is assigned to DC for review.
- KDS confirms with DR that the best approach for WG members to make changes to documentation pages is to create a new branch off of branch `v0.2.0-candidate-patch02`.
- Syntax guidelines documentation is assigned to DR for review.
- Quality assurance documentation review assigned to US and KDS.
- US confirms that Dai Lin agreed during the previous meeting to review the API specification.
- KDS points DC to the directory documentation/diagrams/ to review all diagrams used in the data dictionary and assigns this section to him for review.
- Design pricnciples assigned to DJ for review.
- KDS asks DC whether he can review preliminary mappings to Green Button, and explains that they are very preliminary and may be able to be expanded, KDS further confirms a goal of expanding mappings to other LF Energy standards with DC.
- DJ asks the process for review. KDS requests that members perform review and file issues if they cannot resolve issue, otherwise make change on open branch v0.2.0-candidate-patch02 that has an open PR with changes, if everything looks good after  review, reviewer can comment on open v0.2.0-candidate-patch02 "Reviewed [file or section name], all looks good to me".

---

### 7\. Other Business & Next Steps
- **Discussion and Decision:** Path towards ontology acceptance as public working group draft
- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting

Notes:
- KDS will share the signup sheet for URPX review with the WG so members can continue to sign up for review sections.
- KDS explains that the URPX website will move to the public urpx-website repository and will be transferred to LF Energy to be hosted at urpx.org. The site provides documentation in clearer, more readable format for users who are less familiar with GitHub, and shows the WebVowl ontology diagram.
- KDS confirms that we will aim to release the URPX standard publicly under version number 1.0.0 with a vote to be released on May 19th.
- DC requests to verify name of PR 39, KDS updates PR title and confirms that WG members should review material on branch v0.2.0-candidate-patch02 in the open PR.

