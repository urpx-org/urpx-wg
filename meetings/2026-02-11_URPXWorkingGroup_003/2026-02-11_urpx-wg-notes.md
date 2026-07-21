#  Utility Rate Plan Exchange (URPX) Working Group Meeting #003 
#### Date: 2026-02-11 11.30AM US ET

## Agenda

| nr | What | Topics | Who | 
| :---- | :---- | :---- | :---- |
| 1| Quick Hellos | Quick Recap, welcome new participants | Klaartje, new participants|
| 2 | URPX Status Update | LF Energy materials, Github repository review, member access and review status | All | 
| 3 | Ontology | Review updates to materials made available via github, initial feedback on ontology, questions | All|
| 4 | SHACL Rules | Review SHACL posted to repository| Klaartje, Una, All |
| 5 | API | Assign reviewer(s) for placeholder requirements documentation | All |  
| 6 | Documentation | Status, materials introduction, questions, github workflow, URPX website | All |  
| 7 | Test Data | High level review, assign test data reviewers | All | 
| 8 | Other Business & Next Steps | Proposal to update meeting day to Tuesday, Volunteers for co-chair, secretary, community outreach| All|




## Meeting Notes
---

#### 1. Quick Hellos 
- Quick Recap
- welcome any new or returning participants 

- Klaartje De Schepper (KDS) welcomes David Richardson (DR), Bruce Nordman (BN), and Don Jackson (DJ)
---

### 2. URPX Status Update 
- Website and logo brief submitted to LF Energy for posting on public website, awaiting logo proposal
- Github repository review:
Ontology:
https://github.com/urpx-org/urpx

Meetings:
https://github.com/urpx-org/urpx-wg/tree/main/meetings

Public Intro:
https://github.com/urpx-org/urpx-website/blob/main/introduction/index.md


- Semantic web learning updates/questions

---

### 3. Ontology 
- Review updates to materials made available via github, initial feedback on ontology, questions

---

### 4. SHACL Rules 
- Review SHACL posted to repository

- DJ agrees he will jump into reviewing `urpx-shacl.ttl` and related documentation materials

---

### 5. API
- Assign reviewer(s) for placeholder requirements documentation 

- DJ has agreed to review API documentation materials.

---

### 6. Documentation | Status, github workflow
- Status, materials introduction, questions,
- Github workflow including PR approval process
- Plans for visualization enhancement using  WebVOWL, see example at: https://service.tib.eu/webvowl
- URPX Website

- DJ will be reviewing documentation materials related to the SHACL [urpx-quality-assurance.md] and the API specification which is in the requirements-gathering phase [urpx-api-spec.md].
- KDS suggests that WG members who are not familiar with RDF begin by reading `urpx-semantic-web-guide.md` before beginning their review of the ontology and SHACL.
- KDS gives overview of urpx-website repository which contains materials planned to become public-facing, and explains that some documentation materials from the urpx repository will end being moved to urpx-website to become public-facing. 
- KDS introduces WG members to `skos/` folder, showing mapping to other standards, these are early draft efforts that we will build on. shows example from Green Button and explains that this is where we would draft mapping standards URPX to Matter and vice versa.
- DJ says he appreciates BN's input on Matter mapping and will look into this further.

---

### 7. Test Data  
- High level review
- Assign test data reviewers

- KDS introduces WG members to the test-cases folder in the URPX repository, showing the one JSON-LD URPX example and the tariff book PDF that that example rate plan came from.
- KDS asks WG members whether they have ideas for other rate plans to represent in URPX, whether real or synthetic.
- BN describes his interest in rate plans with prices that change frequently, and wonders whether URPX can currently represent those rapidly changing prices.
- KDS says there will likely be updates needed to the ontology but so far we have included what we think will be needed for complex modeling including for dynamic pricing and market supply prices.
- KDS shows example in JSON-LD of where rules for dynamic pricing would live, within the BillingModel where TOU Schedules also live.
- BN suggests that we should not allow for both dynamic pricing and TOU schedules, that URPX should put limits on the complexity of rate plans that can be represented. 
- KDS says that she and DZS agree that there will need to be limitations.
- DJ asks about price expression in URPX rate plans with TOU Schedules, KDS explains that prices refer to the TOU period number after TOU periods have already been defined and shows an example in the PG&E test case.
- DJ asks about calculation of dynamic pricing, suggests that there is no real way to calculated these prices
- KDS raises concept of "Current Price" along with rules for calculation of dynamic pricing, and agrees that the current price likely comes from an external source and will have a reference to the source.
- DJ says in order to support use case of highly dynamic prices, we may need to allow for workflow to include link to OpenADR to find current price, KDS suggests this could exist on PriceDefinition.
- BN says most common is day ahead price announced 5 PM day before price is effective. Suggests that prices could be loaded into/submitted to URPX server so URPX server has same UTD information.
- DJ reiterates importance of link or workflow to retrieve highly dynamic prices.
- KDS agrees with DJ that this will likely be necessary, and we will additionally need to be able to represent the highly dynamic pricing in URPX once it has been retrieved.
- KDS suggests that path or process to find most UTD price could be defined on Price Definition, but also keep reference to source on all Price objects.
- KDS says one of the major benefits of URPX is the simplicity for the user of accessing prices that may be published externally.
- DJ determines he will read up a little more on this side of the utility domain so he can contribute further to this type of modeling.
- BN brings up PGE pricing: PGE published price components, not the full price. BN reiterates KDS' explanation that URPX contains those components to calculate the price. BN states his understanding that URPX can have both calculated price amounts and the components and calculation rule used to calculate that price, which is useful for researchers.
- KDS confirms that URPX is able to model both calculated prices and the rules to calculate the price. She confirms the utility of the calculation components and rules to be able to calculate future prices, for example.
- BN brings up scenario where forecasted prices are released, you should always know the price some time before the price becomes effective
- BN recounts that Commonwealth Edison has a model where they will release the price at the end of the hour, BN suggests we do not allow for this type of price publication in URPX.
- KDS shares her understanding of pending prices, valid/approved prices. Asks BN whether there is a standard for representing the status of a price?
- BN says it is either a guaranteed price or a forecasted price when released by a utility.
- DJ thinks that even if the release of prices at the end of the hour seems unfair, the goal of URPX is to model real-world tariffs, so URPX should be able to represent prices available after their effective period. He proposes that we model that rate plan to test URPX's modeling abilities of edge cases.
- BN suggests ConEd rate plan could work as well because there are typically forecasted prices, same as the ComEd tariff.
- BN says PUC required this tariff, Elevate Energy runs this tariff for ComEd, BN has a connection there. 
- KDS says that the challenge is that these rules and prices are all published in different formats, this is the URPX solution that allows for uniform modeling that allows for integration with standards like OpenADR
- DR says it is very challenging to create a process to retrieve external information within a JSON-LD URPX instance, may be better as part of another system
- KDS says at least on the receiving end there are some standards for representing these prices that URPX can map to, the goal is to make URPX a centralized standard everyone can map to.
- BN asks whether we have investigated Matter's representation of TOU prices (or dynamic prices), KDS says she has not yet but that is a goal for improving URPX representation of dynamic pricing and mapping to other standards. 
- BN explains that Matter has developed way to represent TOU prices and tiered prices, suggests that they allow you to layer the TOU periods and the usage tiers. He feels that streaming TOU periods to device is not efficient and could be improved. 

---

### 8. Other Business & Next Steps
- Proposal to update meeting day to Tuesday 11.30AM ET
- Volunteers for co-chair, secretary, community outreach

- KDS called a vote to approve moving the WG meeting to Tuesdays moving forward, members assent, WG meeting will be held on Tuesdays beginning with the next meeting.
- BN and Yarille raise that the TAC WG meets on the second Tuesday of the month which could conflict with our new schedule, Yarille recommends that we adjust our cadence to meet on the 1st and 3rd Tuesdays of the month to avoid frequent conflicts with TAC meetings. KDS and BN approve adjusting meeting cadence, which will mean an additional URPX WG meeting next week, before resuming the bi-weekly schedule.
- DR recommends sharing materials in such a way that we could circulate blog posts on platforms such as Medium.
- KDS explains that a draft URPX logo is on the way, which will affect the styling of the public-facing website and allow us to move forward with publishing the website.
- Yarille says a possible platform for sharing materials that LF ENergy already uses is X.
- KDS expresses interest in WG members using their existing networks for community outreach.
- KDS suggests that another method of community outreach could be attending conferences, she mentions an open source conference possibly being held in May in Minneapolis.

