# Utility Rate Plan Exchange (URPX) Working Group Meeting \#004

#### Date: 2026-03-03 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | Github repository updates, member contributions, semantic web learning progress | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions. Discussion: isCredit removal and credit representation strategy. | Klaartje, All |
| 4 | Test Data Review | Review test data examples and validation against ontology | Klaartje, Una, All |
| 5 | SHACL Rules | Overview of SHACL validation rules and constraints | Una, All |
| 6 | Documentation | Status updates, documentation updates needed, questions from materials review | Klaartje, All |
| 7 | Other Business & Next Steps | Next meeting date/time, volunteer roles status, action item assignments | Klaartje, All |

## 

## Meeting Notes

Zoom summary available at: https://zoom-lfx.platform.linuxfoundation.org/meeting/95655220156-1772555400000/summaries?password=5b461314-91c8-406c-ac6e-a3924c50b6f6

---

#### 1\. Quick Hellos

- Quick Recap  
- Welcome any new or returning participants

Attendees:
- David Richardson (DR)
- Bruce Nordman (BN)
- Don Jackson (DJ)
- Klaartje De Schepper (KDS)
- Una Smithsimon (US)
- Yarille Ortiz (YO)
- Danny Zimny-Schmitt (DZS)

---

### 2\. URPX Status Update

- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status

Notes:
- KDS discusses open pull request:
  - Updates to documentation, goal to reduce documentation materials to reduce updates needed after ontology updates. 
  - Ontology changes are primarily for consistency, for example, updating `appliesInZone` to `appliesInGeographicZone` to align with existing property `geographicZone`. 
  - Test data is also updated to align with ontology changes. 
  - Changes are documented in the changelog which helps with migration of data from one version to the next.
- KDS suggests that future diagrams will likely be SVGs.
- DJ would like a format that is compatible with LLMs, and suggests that mermaid would be a good option that is machine-readable.
- DR will be working on educational materials for the next meeting and asks WG members for input on what they would like to see.
- DJ shares that he has new URPX implementations to share representing rate plans from his local municipal utility, and he needs write access to the urpx repository to create a pull request to share his data instances.
- KDS shares that WG repository now contains new URPX logo which WG members may use.
- KDS shares that updates to website brief for LF Energy website have been completed.

---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale
- **Discussion: Removal of `isCredit` boolean property**
  - `isCredit` was added (Jan 27) as an optional boolean on Price, PriceSet, and PriceDefinition to explicitly flag credits for accounting system integration
  - Removed (Feb 18) because it introduced ambiguity: a credit could be represented as a negative value, as `isCredit: true` with a positive value, or both -- making enforcement impossible at scale
  - Current approach: credits indicated exclusively through negative `unitPrice`/`amount` values combined with credit-specific `chargeType` enumerations (`creditEnergy`, `capitalCredit`, `creditGeneration`, etc.)
  - Open to revisiting credit tagging in the future with a less ambiguous mechanism
- **Discussion: Treatment of credits as negative numbers vs positive numbers**
  - Current convention: credits use negative values in `unitPrice` and `amount` fields
  - Question for the group: Should credits always be represented as negative numbers, or should positive numbers with a credit `chargeType` be an acceptable alternative?
  - Considerations:
    - Accounting systems may expect credits as positive amounts with a credit indicator
    - Mathematical simplicity favors negative values (summation works without special logic)
    - Some tariff source documents express credits as positive dollar amounts
    - Could a future `creditType` ObjectProperty (with controlled vocabulary) replace the boolean while avoiding the ambiguity?
- Questions and feedback from members' review
- Discussion of potential improvements or refinements

Notes:
- BN supports use of negative numbers to represent credits, especially with "adjustment" prices.
- DJ says one thing he gets from BN is that there are adjustments that are positive and negative (charges and credits), but endorses the idea of machine-readable semantic definition of a credit, like use of `isCredit`, open to removing negative values for credits if using a semantic credit identifier.
- KDS asks BN how he would represent grid support at a dynamic price with negative values.
- BN brings up example of electric wholesale prices that go negative.
- KDS clarifies the credit we are considering would be something like remuneration to customer for shutting off electric use during high-load periods.
- BN says when you're exporting electricity, consumption is negative, both consumption and prices would be negative and he views this as reducing ambiguity.
- KDS further clarifies the distinction between an account credit and a negative adjustment price for example to reconcile a previous charge.
- DJ reiterates the question: do we need a semantic definition of a credit in addition to the negative number?
- DJ describes the difference between modeling a rate plan and modeling a bill and asks for confirmation that bill modeling is out of URPX scope.
- KDS confirms that URPX modeling does not include bill modeling (such as late fees, line item names...), at a later stage we may need a mapping to these elements, but for now we are focused on development to support cost calculation.
- US explains adjustments are classifications of typical Prices, and the role of credits as negative prices, for example remuneration to customer of adjustment already charged, or volumetric credits for energy generation.
- BN describes adjustments that "go up" or "go down", US clarifies that while logically that describes adjustments, URPX models them as distinct prices with positive or negative values.
- KDS describes price using basePrice with "adjustments" using a multiplier or an adder as another example of "adjustment" in URPX.
- BN describes negative amounts for both unit prices and fixed prices and asks whether we can model both.
- US explains that current test data example has examples of negative unit prices and show WG example of bundled PCIA credit, and clarifies that fixed prices (`urpx:amount`) also use negative values to represent credits.
- Group determines that for now, URPX will continue to use negative values to represent credits, and will not use a semantic declaration of credits such as `isCredit`.


---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review

Notes:
- DJ shows his data instance of a hydro-electric rate plan with complex adjustments and makes plans to create a PR 
- US and DR ask DJ about his prompts and workflow for test case generation from PDF inputs, which can be challenging with LLMs.
- DJ says while the LLMs can read PDFs, most of the PDF information is structural and expands LLM context too much. He says ideally, there would be markdown-formatted (or similar) version of tariff documents, but the examples he has built are based on short, two page PDFs.
- KDS asks BN about dynamic pricing rate plans to use for modeling, either ComEd or PG&E.
- BN says he's not aware of the formal tariff for these rate plans, KDS says she will dig for them.
- DJ says he put his LLM prompt for test data generation in the URPX Slack chat for WG review.


---

### 5\. SHACL Rules

- Overview of SHACL validation rules posted to repository  
- Key constraints and their purpose  
- Questions and feedback from members' review

Notes:
- US shares that we will be providing materials for SHACL validation that will be completed before a merge of any new test data.
- KDS explains workflow where user can perform validation before creation of PR.

---

### 6\. Documentation

- Status updates on documentation materials  
- Documentation updates needed  
- Questions from members' github materials review  
- Github workflow feedback and process improvements

Notes:
- KDS says recent documentation updates were mostly cleanup, we are aware of the importance of reducing verbosity and redundancy to enable updates on ontology updates.
- BN asks about documentation on use cases, what types of users URPX is useful for.
- KDS points him to urpx-website repository for documentation materials.
- BN asks about URPX for formal representation of external prices, KDS confirms that is the goal to serialize those prices into a single rate plan.
- BN brings up wholesale electricity prices as a potential complexity as they are released in real time, KDS explains they can be represented in URPX as a historical price series.
- US highlights urpx-overview.md as a resource for BN to better understand use cases and typical URPX users.

---

### 7\. Other Business & Next Steps

- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting

Notes:
- KDS encourages WG members to invite people who may have joined once or who may be interested to join our next meeting as we will be focusing on educational materials.
- KDS says we are interested in presenting at conferences this year and asks WG members to submit recommendations of conferences at which we could present URPX.
