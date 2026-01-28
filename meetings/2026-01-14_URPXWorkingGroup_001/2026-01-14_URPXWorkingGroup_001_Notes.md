# # Utility Rate Plan Exchange (URPX) Working Group Meeting 2026-01-12

## Agenda

| nr | What | Topics | Who | 
| :---- | :---- | :---- | :---- |
| 1| Quick Hellos | Quick Recap, welcome new participants | Klaartje DS|
| 2 | URPX Status Update | Github repository review, semantic web learning updates | Klaartje DS | 
| 3 | Ontology | a)Core element introduction, b)logic expression for eligibility | Klaartje DS, All|
| 4 | SHACL Rules | Approach and status | Klaartje DS |
| 5 | API | Design approach, volunteers | All |  
| 6 | Documentation | Status, materials introduction, WebVOWL implementation volunteer | All |  
| 7 | Test Data |  Select mock vs. actual data approach, decide next steps, volunteers | All | 
| 8 | Other Business & Next Steps | Volunteers for co-chair, secretary, community outreach| All|




## Meeting Notes


### | 1| Quick Hellos | Quick Recap, welcome new participants 
- KDS welcomed each participant as they joined and noted that we had no new members during this meeting.

### | 2 | URPX Status Update | Github repository review, semantic web learning updates 
- KDS gave an overview of the three repositories in the urpx-org Github organization. Meeting agendas, notes, and supporting documents such as meeting presentations can be found in the `urpx-wg` repository. Documentation materials can currently be found in the `urpx-website` repository. The `urpx` repository is currently private because it is in pre-draft stage and requires final IP review before handover to the Linux Foundation and licensing under the Apache 2.0 license.
- KDS further explained that content currently available on the public repository `urpx-website` is a version of our documentation that will be migrated to urpx.org.
- KDS clarifiesdthat the URPX ontology Version 0.1.1 is a draft version with outstanding design questions.
 
### | 3 | Ontology | 
a)Core element introduction
- KDS explained RatePlan to RatePlanVersion heirarchy and value of temporal versioning with RatePlanVersion.
- KDS also explained the roles of the EligibilityRule, PlanElements, and Prices containers directly under RatePlanVersion.
- BN asked whether there is a mechanism for representing dynamic prices in URPX format within the Prices container, KDS confirmed dynamic pricing rules can be expressed in URPX format within the Prices container.

b)logic expression for eligibility 
- BN asked about the purpose of CustomerProfile and ServicePointProfile, how they are used for universal eligibility vs. for individual customer data, KDS explained general elibility rules exist in CustomerProfile and ServicePointProfile without PII, but a Customer Scenario document in URPX format can be generated separately to contain individual customer information.
- KDS explained the use of logicExpression to combine inputs from Customer and ServicePointProfile to create complex eligibility expressions.
- Dai pointed out that information on calculation rules can be hard to access (in PDFs, PSC filings, other commnications from utilities and regulators). Dai asked where we ingest this data to ensure accurate inputs for accurate calculation models.
- DZM says that NLR has a pilot project to integrate ML and AI to interpret these complex calculation models from regulatory documents, beginning with PG&E. Dai and KDS expressed interest in collaboration, KDS highlights Flux Tailor's work with PG&E's Net Billing Tariff as a prime example of very complex calculation models and logic expressions.
- Dai confirms having variables with data type values wrapped in an eligibility rule is logical and comprehensive.

### | 4 | SHACL Rules | Approach and status 
- KDS said that this topic will be addressed in the next Working Group meeting.

### | 5 | API | Design approach, volunteers 
- KDS said that this topic will be addressed in the next Working Group meeting.

### | 6 | Documentation | Status, materials introduction, WebVOWL implementation volunteer 
- KDS introduced the concept of WebVOWL and noted that we will be looking for volunteers to support WebVOWL integration in the future.

see example implementation: https://service.tib.eu/webvowl/

### | 7 | Test Data |  Select mock vs. actual data approach, decide next steps, volunteers 
- KDS confirmed that PG&E's E-ELEC rate plan will be the first instance of URPX test data shared with the working group, and we will also provide an example rate plan with dynamic prices.
- KDS said that there will be an URPX instance of PG&E's E-ELEC rate plan in the `urpx` repository by the time of the next Working Group meeting in two weeks.

### | 8 | Other Business & Next Steps | Volunteers for co-chair, secretary, community outreach
- KDS expressed interest in community outreach effort after pre-draft URPX release.
- KDS requested that before the next Working Group meeting in two weeks, Working Group members should review the documentation available in the `urpx-website` repository, and review the contents of the `urpx`repository, which will be populated by end of day Friday 01/16/2026.
