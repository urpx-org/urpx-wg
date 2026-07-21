#  Utility Rate Plan Exchange (URPX) Working Group Meeting #002 
#### Date: 2026-01-28 11.30AM US ET

## Agenda

| nr | What | Topics | Who | 
| :---- | :---- | :---- | :---- |
| 1| Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants|
| 2 | URPX Status Update | Github repository review, semantic web learning updates | All | 
| 3 | Ontology | Review materials made available via github in urpx-org/urpx, follow up on logic expression for eligibility, share proposed approach | Klaartje, Dave, All|
| 4 | SHACL Rules | Preview SHACL in progress, assign documentation reviewer(s) | Klaartje, Una |
| 5 | API | Assign reviewer(s) for placeholder requirements documentation | All |  
| 6 | Documentation | Status, materials introduction, questions, github workflow | All |  
| 7 | Test Data | High level review, assign test data reviewers | All | 
| 8 | Other Business & Next Steps | Volunteers for co-chair, secretary, community outreach| All|




## Meeting Notes
---

#### 1. Quick Hellos 
- Quick Recap
- welcome new participants 

- KDS welcomes Dai and Neil.
- KDS reminds WG members that meeting notes are always available after each meeting.
- KDS introduces Dave Richardson from Flux Tailor, an expert on semantic web technologies.
- KDS introduces Mohammed Zergaoui, who is not present today.
- DR introduces himself and describes his professional experience and experience with semantic web technologies.
- Neil Williams shared his Github handle: @spladug
- Dai shared her Github handle: @dai-utilityapi
- Don Jackson, based in SF Bay Area, strong advocate for electrification and decarbonization and is currently working as a contractor with SPAN. Don is also a contributor to the OpenADR standard.
---


### 2. URPX Status Update Github repository review, semantic web learning updates 
- Github repository review
- Semantic web learning updates

- KDS introduces the URPX repository under the urpx-org organization in Github.
- KDS begins documentation overview by sharing index.md, a type of homepage for all documentation pages, and showing participants how they can navigate core documentation pages through links in index.md.
- KDS epxlains that the data dictionary goes into all classes,properties, and enumerations in a human-navigable manner for those who are less familiar with RDF and JSON-LD syntax.
- KDS says that systems exist to manage this type of data dictionary over time
- KDS says design decisions docuemnts include descriptions of the process of the development of URPX v0.1.1 pre-draft with numbered decisions that were made during development. Each decision presents alternatives cconsidered and decision reasoning
- KDS introduces design-principles.md as a good resource for reviewers to ensure suggestions and pull requests are aligned with organization format and standards.
- As a result of this meeting, KDS is hoping for commitments to sections for review, need reviewers of documentation, so participants should begin to think about which sections they would like to review.

---
### 3. Ontology 
- Core element introduction
- logic expression for eligibility and `CalculationMethod` `logicExpression` choices:
 1. Raw strings
 2. SQL syntax
 3. Reverse Polish Notation (RPN)
 4. SPARQL

- KDS explains we now have one ontology file.
- KDS describes URPX goal of creating an ontology that is small enough that it is navigable by AI agents.
- KDS announces that Dave will lead a follow-up conversation about how to structure logic expressions after she provides an overview of the ontology.
- Apache 2.0 license as source code contributed by FT. As updates come in and the WG approves a draft, this will become a W3C licensed standard
- First we define all of the classes, each ontology element has a label, a comment that could be used as a tool tip for users, and a little more context for developers in the form of a note.
- FOllowing the classes, we have what are called enumeration classes. KDS requests that Dave provide an explanation of how we naviagate from a property on a class to an enumeration value.
- DR explains that each enumeration is represented as a class and the possible values are instances of that class. 
DR gives example of accumulationMethod under MetricSpecification, the third node of the triple is the enumeration value class. 
We specify in the main ontology what the possible values are, and in the SHACL re-specify the possible values for the purpose of constraining,
- KDS explains that in OWL we have an "open world assumption", but that by using SHACL, we are able to constrain the OWL. It is also possible to create more specific SHACL, for example, specific constraints for a specific location, to further constrain.
- KDS explains that the classes are the nodes, and the properties are the links between the nodes. This is different than representing data hierarchically, because insteaad of defining from a clas what its attributes are, we defined class attributes through domain on properties. The range provides the object of the property, which can be another class reference or a string. Domain and range can both have multiple values for each property.
- KDS describes the "has" properties as creating a link between two classes, which might be expressed with a join table in a relational database.
- Some relationships can be expressed as the inverse specifically which allows for simple processing. 
- KDS asks for any questions from participants.
- Dai says she cannot yet access the Github, and is new to RDF and SHACL, and asks for a deeper explanation of SHACL
- KDS agrees we can move on to a deeper dive into SHACL later on in the meeting and provides a brief explanation of how an ontology defines relationshsips, and SHACL constrains the relationships.
- KDS shows an example of WebVOWL and expresses a goal to show the URPX ontology using WebVOWL as it can be helpful for viewing complex relationships.
- DR presents a sample SPARQL query and explains that this is an example of a simple query used
---
### 4. SHACL Rules 
- Preview SHACL in progress 
- Assign documentation reviewer(s) 

- US gives another overview of the differences between an ontology and SHACL and provides an explanation of SHACL structure.
- US shares an excerpt of the pre-pre-draft 
- KDS suggests that Don review documentation materials related to SHACL and ideally contribute to SHACL review and further development.
- Don says he is a big proponent of specification-driven development and will review SHACL documentation.
---
### 5. API
- Assign reviewer(s) for placeholder requirements documentation 

- KDS requests reviewers of brief API documentation.
- Don says he would be open to reviewing and asks for further details on the URPX API.
- KDS explains role of API as a standardized way of exchanging URPX information.
- Don draws comparison to OpenADR RestAPI specification.

---
### 6. Documentation | Status, github workflow
- Status, materials introduction, questions,
- Github workflow including PR approval process
- Plans for visualization enhancement using  WebVOWL, see example at: https://service.tib.eu/webvowl

- KDS asks Neil which portion of the documentation he may be able to review, and potentially provide input towards the development of a representation of greenhouse gas emissions in URPX.
---
### 7. Test Data  
- High level review
- Assign test data reviewers

- Test data will be reviewed by Dai and DZM (NLR).
---
### 8. Other Business & Next Steps
- Volunteers for co-chair, secretary, community outreach
- Ongoing conflict for Bruce and Don until 12 PM.
- KDS expresses interest in further supporting asynchronous work, including creating "office hours" on the off weeks from WG meetings for check-ins.
- Don explains that Wednesday and Thursday mornings are the most popular times for standards WG meetings with European collaborators, and asks whether it would be possible to move the meeting to Monday or Tuesday
- KDS agrees that we can consider moving the meeting to Tuesday, and she will check with Dai and DZM. 
- Don and Bruce express that. they can meet as early as 7 AM pacific time.





