**Utility Rate Plan Exchange (URPX) Kickoff Meeting 2025-11-19**  

Zoom Meeting Recording and transcript: https://zoom.us/rec/share/b97EU4dOooWUMEwR8WRjVVeJAjUDxfUukhTQ7jJFHfefLjgY8sGP75SNxZ78rjKv.WtE4UC7oojFUNe5a

Follow Up:
* Next Meeting: Wednesday January 14th at 11.30 US ET, then every two weeks. You should have received an invitation, let me know if that isn't the case.
* The Semantic Web Guide draft with requested learning resources and introductory material has been shared
* We're working on setting up the repositories and ontology materials for review, this will be a private repository for the next month or so. I'll be inviting you with your github handle. Send me any specific Github handles to use.
* Our Github Org: https://github.com/urpx-org - stay tuned for updates


Other Practical Info:
* New working group e-mail list (use wisely): urpx-wg@lists.lfenergy.org
* Manage mailing list notifications: https://lists.lfenergy.org/g/urpx-wg

## Attendees:

| Name | Organization |
|---|---|---|
| Alex Thornton | LF Energy |
| Bruce Nordman | Lawrence Berkeley National Labs |
| Cooper Marcus | Quit Carbon |
| Dai Lin | UtilityAPI |
| Daniel Zimnyschmitt | NREL |
| Dave Richardson | Flux Tailor |
| John Mertic (The Linux Foundation) | The Linux Foundation |
| Jordan Hughes (Apple Inc.) | Apple Inc. |
| Jory Burson (The Linux Foundation) | The Linux Foundation |
| Klaartje De Schepper | Flux Tailor |
| Mohamed Zergaoui | Optimizix |
| Neil Williams | WattCarbon |
| Una Smithsimon | Flux Tailor |
| Yarille Ortiz (The Linux Foundation) | The Linux Foundation |

## Agenda

| nr | What | Topics | Who | Time (US ET) |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Welcome and Intros | Quick Hellos | Klaartje DS | 10:00 — 10:05 |
| 2 | URPX Overview | Goals and Timeline, github repo review | Klaartje DS | 10:05 — 10:45 |
| 3 | Ontology | Design approach, edge case research | Klaartje DS, Danny ZS |  |
| 4 | SHACL Rules | Approach and status | Klaartje DS, Una SS |  |
| 5 | API | Design approach, volunteers | All |  |
| 6 | Documentation | Documentation scope and status, volunteers | All |  |
| 7 | Test Data | Scope and maintenance, volunteers | All | 10:45 — 10:50 |
| 8 | Other Business & Next Steps | •Volunteers for co-chair, secretary/task manager •Meeting Cadence: Biweekly starting mid January? | All | 10:50 – 11:00 |



**Welcome and Intros**

* Flux Tailor has an MOU with NREL for URPX development, Danny Zimny-Schmidt works on URDB, collaborates on edge cases and rates that are difficult to model in standardized, machine-readable format  
* Neil WIlliams works at Watt Carbon.  
* Bruce Nordman has extensive experience with complex tariffs and highly dynamic pricing  
* Dai Lin works with customer data and billing at UtilityAPI  
* John Mertic offers help with operational backend needs  
* Jordan Hughes (Apple Energy Services Team) has experience with clean energy charging and expresses a strong interest in standardization  
* Jory Burson is VP of standards at LF, sees alignment with some other LF projects, offered connection with CDS  
* Mohamed Zergaoui focuses on the process of designing standards, validation, markup and XML expertise  
* Yarille Ortiz from LF offers operational support

**URPX Overview**

* “Rate plan” verbiage is a deliberate decision in the URPX project, “rate plan” is used in the Tesla app, for example.  
* Klaartje De Schepper is open to guidance from LF on licensing for URPX  
* Klaartje De Schepper outlines the URPX project timeline  
* Klaartje De Schepper raises the possibility of future pilot programs  
* Klaartje De Schepper highlights the existing problems with rate plan data accessibility and challenges to implementation of URPX including a fragmented data landscape across territories  
* Klaartje De Schepper gives a general overview of modular ontology in RDF including core rate plan ontology, charge classification ontology, geography ontology, and organization ontology, using SHACL constraints for data quality validation.  
* Klaartje De Schepper expresses that URPX data instances will be available in JSON-LD through GraphQL or RestAPI  
* Klaartje De Schepper confirms that integration with other standards is necessary, including Customer Data Specification and Green Button Connect  
* Klaartje De Schepper offers a basic overview of structure of rate plans and rate plan versions, eligibility (applies to rate plan) and applicability (applies to charges) rules, and rule expression methods using operators and condition definitions.

**Ontology**

* Klaartje De Schepper will make a Github repository for the standard. She will also create a website with important information about the URPX standard for people without Github experience.   
* Ontology organized by datatype (Classes, then properties, then enumerations) and in alphabetical order within each section  
* Asked for input from anyone with RDF experience–Jordan Hughes from Apple says he is unfamiliar, **Dai Lin and Neil are both unfamiliar but would like to learn and contribute**  
* Klaartje De Schepper points out that semantification allows for easy AI integration, AI very good at understanding ontologies and knowledge graphs  
* Flux Tailor can lead further ontology development but would like volunteers for support

**SHACL Rules**	

* SparQL can be used for more advanced constraints but we are currently keeping the SHACL simple with basic property constraints  
* Looking for a volunteer to captain advanced SHACL development

**API**

* Dai Lin doesn’t have strong experience with JSON-LD but has strong API experience, would like to draw up user requirements as a group, then choose dynamic tools to leverage that can connect with RDF. Before committing to taking on the first draft of requirements, Dai would like to learn more about the standard and be a collaborator.  
* Neil Williams would like to be involved with API design.  
* Klaartje would like examples of API standards Neil and Dai approve of.

**Documentation**

* Klaartje De Schepper notes that the documentation section of the URPX repository is currently being updated.  
* Klaartje De Schepper announces the need for volunteers to manage the documentation section of the URPX repository  
* Dai Lin expresses a desire to expand her technical knowledge, Klaartje De Schepper responds that the documentation portion of the repository will contain a section with educational materials.  
* Klaartje De Schepper proposes that after a period for WG members to explore the educational materials, the next WG meeting can be used to more deeply explore ontologies and members can contribute their new knowledge or ask core questions which may influence further education.

**Test Data**

* Klaartje De Schepper reports that test data is not yet in the URPX repository  
* Danny Zimny-Schmidt has provided edge cases that URDB cannot model, for example, charges that are calculated using complex formulas. Edge cases such as these can be transformed to URPX JSON-LD format.  
* Klaartje De Schepper expresses a need for volunteers to support this effort, but expects it will take some time for everyone to get acquainted with RDF before supporting test data creation and validation.

**Other Business & Next Steps**

* URPX needs support with operations  
* Klaartje De Schepper is seeking a volunteer co-chair to support running meetings and a “secretary” for administrative assistance including meeting notes and agendas (this can be the same person as the co-chair or someone else)  
* Meeting minutes and agendas will be available on Github to all members regardless of whether they are able to attend, and members can contribute to the URPX project regardless of whether they can attend WG meetings  
* Meeting frequency: Klaartje proposes bi-weekly meetings beginning mid-January, others agree.  
* Meeting timing: 11:30 AM eastern time, Wednesdays (approved by Dai Lin and Neil Williams)

**General Comments and Questions**

* Cooper Marcus from QuitCarbon is interested in an URPX pilot to support the development of a rate plan database for work on a contract funded by CEC  
* Bruce Nordman has worked on the OpenADR standard and is interested in URPX to OpenADR mapping. Klaartje De Schepper confirms that standards mapping and interoperability is a priority.

