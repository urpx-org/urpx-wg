# Utility Rate Plan Exchange (URPX) Working Group Meeting \#007

#### Date: 2026-04-14 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | URPX LF Energy website, urpx.org website review, member contributions, semantic web learning progress, URPX v0.1.2 release and v0.2.0 candidate | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions. Discussion: new Condition Logic architecture. | Una, Klaartje, All |
| 4 | Test Data Review | Review test data examples and validation against ontology. Discussion: implementation of new ConditionLogic model and RateCase reference object, Don Jackson's test data | Klaartje, Una, All |
| 5 | SHACL Rules | Overview of SHACL validation rules and constraints. Discussion: closing of SHACL shapes | Una, All |
| 6 | Documentation | Status updates, documentation updates needed, questions from materials review | Klaartje, All |
| 7 | Other Business & Next Steps | Next meeting date/time, volunteer roles status, action item assignments. Discussion: Path towards ontology acceptance as public working group draft | Klaartje, All |

## Meeting Notes

---

#### 1\. Quick Hellos

- Quick Recap  
- welcome any new or returning participants

---

### 2\. URPX Status Update

- URPX LF Energy website is live: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- URPX.org website draft review
- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status
- URPX v0.1.2 release
- URPX v0.2.0 candidate

---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale
- **Discussion:** New Condition Logic architecture.

---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review
- **Discussion:** implementation of new ConditionLogic model and RateCase reference object, Don Jackson's test data

---

### 5\. SHACL Rules

- Overview of SHACL validation rules posted to repository  
- Key constraints and their purpose  
- Questions and feedback from members' review
- **Discussion:** closing of SHACL shapes 

---

### 6\. Documentation

- Status updates on documentation materials  
- Documentation updates needed  
- Questions from members' github materials review  
- Github workflow feedback and process improvements

---

### 7\. Other Business & Next Steps
- **Discussion and Decision:** Path towards ontology acceptance as public working group draft
- Aiming to have the V0.2.0 version and IP scan updates in over the next week and aim to call a vote in the April 28th meeting to accept V0.2.0 as formal draft URPX W3C standard
- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting

---

## Minutes

Attendees: Bruce Nordman, Klaartje De Schepper, David Richardson, Donald Coffin, Una Smithsimon

- Donald suggested he knew a working group with only two members, suggested mail-in voting for acceptance
- Klaartje said we would provide "outreach materials"
- v0.2.0 candidate circles back to "structured logic expressions" in fully machine-readable approach
- Una presented "URPX Condition Logic" : conditions and combinations of conditions
  - new model:
    - structured condition modeling
    - supports nested rule calculation
    - condition combination structure
  - Condition: "independently evaluable predicate", with left, right and operator
  - Don brought up the necessity of being able to explain (with examples or AI-driven proofs of concept) for people who might not be familiar with, say, left/right operands
- Klaartje will reach out to attendees who've been here from the beginning
- Daniel has a system set up for reaching out to attendees
- Once we go live, planning outreach to DER task force, Mission Data, LinkedIn;
  - maybe NARUC/NERUK(sp?), NASBY (doing EDI/contract definitions), SEEPA
  - "Agreements" might be important for custom pricing; FERK (sp?) is more contract-oriented