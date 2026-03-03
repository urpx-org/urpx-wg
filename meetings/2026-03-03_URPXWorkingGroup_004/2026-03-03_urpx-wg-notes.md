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

