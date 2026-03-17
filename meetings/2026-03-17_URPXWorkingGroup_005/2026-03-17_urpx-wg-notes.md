# Utility Rate Plan Exchange (URPX) Working Group Meeting \#005

#### Date: 2026-03-17 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | URPX LF Energy website, urpx.org website review, member contributions, semantic web learning progress | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions. Discussion: isCredit removal and credit representation strategy. | Klaartje, All |
| 4 | Test Data Review | Review test data examples and validation against ontology | Klaartje, Una, All |
| 5 | SHACL Rules | Overview of SHACL validation rules and constraints | Una, All |
| 6 | Documentation | Status updates, documentation updates needed, questions from materials review | Klaartje, All |
| 7 | Other Business & Next Steps | Next meeting date/time, volunteer roles status, action item assignments | Klaartje, All |

## 

## Meeting Notes

---

#### 1\. Quick Hellos

- Quick Recap  
- welcome any new or returning participants

Attendees:
- Klaartje de Schepper (KDS)
- Una Smithsimon (US)
- Bruce Nordman (BN)
- Yarille Ortiz (YO)
- Donald Coffin (DC)
- Sabil Rahim (SR)

Notes:
- DC introduces himself as technical manager for Green Button Alliance and host for OpenADE task force, KDS explains DC's expertise in customer data and bringing expertise from GBA to connect dots between customer utility statements and rate plan data and welcomes him to the WG.
- SR introduces himself, explaining he manages the energy services team at Apple, focuses on utility connections.
- KDS welcomes SR and says she looks forward to his contributions.

---

### 2\. URPX Status Update

- URPX LF Energy website is live: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- URPX.org website draft review
- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status

Notes: 
- KDS shares that the urpx.org website is nearly ready for publication and shares her screen to show the website content to the WG (notes continued below under Documentation)
- KDS offers to share repository access with DC and SR and explains that the URPX repository is currently private because the source code and data is shared with LF Energy by Flux Tailor under Apache 2.0 license, and cannot be released as W3C standard until WG approves our draft standard materials.
- KDS shares that in order to make this public, Flux Tailor has been doing IP scans, there are a few to-dos, mostly just adding proper licenses. She shares that we hope to be able to make the URPX repository available publicly soon.


---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale
- **Discussion:** Path towards ontology acceptance as public working group draft

Notes:
- KDS explains we will be defining v0.1.1 and moving on to 0.1.2 draft for upcoming updates.

---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review

Notes:
- KDS shares that Don Jackson submitted PR with URPX rate plans, and properly provided Tariff book PDFs in assets folders, and updated index CSV, KDS requests that any members who wish to make test data, follow this workflow by creating your own branch and creating a PR when ready to merge, we will either approve and merge or provide comments for resolution before merge, getting ready to implement automatic validation
- KDS asks if there are questions about creating test cases, no one asks any questions.
- KDS shares edge cases spreadsheet provided by National Laboratory of the Rockies (NLR), this is a wish list of rate plans to try to represent in URPX to see if it is possible to model them with our current schema, this is a list available for WG members who wish to more deeply explore the ontology and have a go at creating test data.


---

### 5\. SHACL Rules

- Overview of SHACL validation rules posted to repository  
- Key constraints and their purpose  
- Questions and feedback from members' review

Notes:

---

### 6\. Documentation

- Status updates on documentation materials  
- Documentation updates needed  
- Questions from members' github materials review  
- Github workflow feedback and process improvements

Notes:
- KDS shares screen to show urpx.org website and explains that DocuSource allows for static snapshots by version, with a banner signifying whether a version is active or not, she notes that this will be helpful as we update, to allow implementers to remain on their own schedule. KDS expects ontology elements to continue changing for a little while, so versioned documentation will be very helpful.
- KDS explains that all website content comes from documentation/ directory in urpx repository and quick link to urpx repository present on site
- KDS introduces data dictionary that includes auto-generated diagrams created using GraphViz.
- KDS shares URPX Core Rate Plan Entities diagram showing the visualized connections
- KDS then shares URPX ontology visualization using WebVowl, shares the "Pick and Pin" editing option to create custom visualizations, and shows the cross-reference between the WebVowl viz and the data dictionary section for each entity
- KDS shares charge classification taxonomy tree diagram
- KDS shares plans to visualize test case example library
- KDS goes through data diagram from Examples section, explains RatePlanVersions, eligibility rules which contain customer profiles and service point profiles
- KDS continues to show the data diagram from the Examples section and explains that condition modeling in Eligibility Rules is currently represented with a string logicExpression property, we are working to create a more structured representation that does not require string parsing.
- KDS continues to show the data diagram and introduce the Plan Elements container, with elements needed for calculation, including seasons, holidays, and metric inputs (for example, per meter and per bill, energy consumption in kWh). 
- KDS introduces billing model container from within Plan Elements in the data diagram, which includes TOU Schedule with tiers and periods, with validity expressed in TimeBrackets allowing specification of daytype and holiday applicability. KDS explains that billing model also includes the new concept of Ledgers, allowing for example for balancing of import and export prices.
- KDS shows in the data diagram that the Prices container contains prices or price sets and each price refers to its price definition that is associated with a ledger, with the linking not shown in the diagram.
- KDS shares Tutorial page of urpx.org site, its purpose is to walk user through creation of a rate plan.
- KDS points out that a couple of the pages on urpx.org are currently stub pages, for the API spec, for example, which will be populated but are visible so it is clear that we plan to include that.
- KDS shows Standards Integration page to DC, where we have created some draft mappings using SKOS between URPX and other open source standards. Right now the diagrams on this page are out of date and will be updated.
- KDS requests that WG members make pull requests to correct incorrect documentation elements or send a message in Slack to ensure things get fixed.
- Interoperability and internationalization guide will be used to represent URPX datasets across different languages.

---

### 7\. Other Business & Next Steps
- **Discussion and Decision:** Github workflow: use of issues, PR review cycle.
- **Discussion and Decision:** Path towards ontology acceptance as public working group draft
- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting
- Staying on for 10 minutes after the meeting to ensure everyone who needs it has github access and answer questions

Notes:
- KDS discusses GitHub workflows, asks WG members whether they have input on GitHub workflow management, she explains that right now the workflow requires a PR to make changes, a group of "committers" can approve PRs. Right now "committers" are all from Flux Tailor, but KDS would like some additional WG member "committers". She requests that contributors ensure that there is review by at least one other person before merging.
- US notes that as WG members get comfortable with URPX and submit test cases as pull requests, they may request specific committers or tag people in comments on a PR to request additional review.
- DC suggests that using an AI to summarize things for GitHub issues may be most efficient, especially if it has access to the full repository, he finds the AIs are very verbose but do a good job of explaining the issue.
- KDS explains the Decision Log is verbose but precise for the same reason, AI can be good at summarizing but overly verbose, and that the AI-assisted decision log has undergone human review.
- KDS explains we want to add guidelines for machines and humans on repository structure, we do have a Syntax Guidelines documentation page for humans editing the ontology, but could use something like an AGENTS.md for machines.
- DC suggests creating an agent file for each type of AI and ensure the agent files pass tests, and that preferential sequencing will be very important.
- KDS explains the goal of having instructions that work for all WG members and their machines, she agrees with DC that having separate files for different agents may make sense. 
- KDS confirms she will add DC to the repository and he will be able to access AI instructions once they have been added to the repository.
- KDS asks BN whether he has input on a brief for navigating and contributing in the repository for users and their machines.
- BN requests a description of limitations of tariff books, some way to define a boundary on what features can be included in a tariff.
- KDS explains that the Quality Assurance page will help explain this by referencing the SHACL shapes. She further explains that the SHACL shapes will be used to automatically validate test cases as they are submitted, and that we can work on designing additional validation for different conditions, such as for highly dynamic pricing.
- BN says the California database for time-varying prices has over 56,000 different tariffs.
- KDS says this often occurs because under the "RatePlan" object there is a lot of variation, for example, what we call profile alternatives, with different baseline allowances per climate zone, for example, each may be released as a separate tariff document but could be represented as a single URPX RatePlan with profile alternatives.
- DC describes challenges of determining geographic applicability.
- KDS explains that a service point profile can define specific geographic eligibility, and that geographic zones can be used for differential applicability of prices, as well, using profile alternatives.
- DC asks how we represent zones, what "zone" means in URPX.
- KDS explains it can flexibly reference polygons, municipalities, or zip codes.
- DC points out that zip code overlaps can be challenging.
- KDS says shape line files for service territories by exact address provide the most precise service territory definitions, we will also be sure to not make the maps static as service territories change frequently.
- BN describes non-geographically contiguous service territories in California defined by circuits that each have their own prices.
- KDS explains those different service territories could exist as profile alternatives with differential prices by territory.
- KDS explains that a portion of the ontology that she still wants to update is introducing the idea of Scenario, representing a customer's service point profile and customer profile attributes, allowing a customer to see all rate plans available to them given that scenario.
- KDS requests input from WG members on how to perform community outreach, we are planning to share on LinkedIn and through LF Energy channels, she asks members to think about conferences to bring URPX to.
- BN proposes the Smart Electric Power Association, KDS thanks him for the suggestion.
- KDS shares that she has already reached out to GBA and asks whether DC has other ideas of groups that may want to join this effort? She mentions that we may want input from utilities.
- DC says he can provide a contact to someone at Con Edison for their input.
- KDS says that would be great, especially as they are local to Flux Tailor.
- KDS asks if members have any remaining questions, there are none. KDS ends the meeting.

