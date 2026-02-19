# Utility Rate Plan Exchange (URPX) Working Group Meeting \#004

#### Date: 2026-03-03 11.30AM US ET

## Agenda

| nr | What | Topics | Who |
| :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants |
| 2 | URPX Status Update | Github repository updates, member contributions, semantic web learning progress | Klaartje, All |
| 3 | Ontology | In-depth review of ontology structure, classes, properties, relationships, and design decisions | Klaartje, All |
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

---

### 2\. URPX Status Update

- Github repository updates and recent contributions  
- Semantic web technology learning progress and questions  
- Member engagement and material review status

---

### 3\. Ontology
- In-depth review of ontology structure and architecture  
- Classes: definitions, hierarchies, and relationships  
- Properties: data properties and object properties  
- Design decisions and rationale 
- - Removal of `isCredit`: Reasoning: Credits are currently negative numbers in URPX. `isCredit` was added as optional explicit way for grouping and validating credits. It was removed as it introduces ambiguity. Keeping it means we potentially risk unreliable by introducing ambiguity and thereby resulting in duplicate credit handling for negative values, impossible to enforce proper use of optional boolean property with large datasets. We are open to a discussionon this topic on better ways to handle credits, and to revisiting credit tagging in the future.

- Questions and feedback from members' review  
- Discussion of potential improvements or refinements

---

### 4\. Test Data Review

- Review of test data examples  
- Validation of test data against ontology  
- Coverage: what scenarios are represented  
- Questions and feedback from members' review

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

---

### 7\. Other Business & Next Steps

- Next meeting date and time confirmation  
- Volunteer roles status: co-chair, secretary, community outreach  
- Action item assignments from today's meeting

