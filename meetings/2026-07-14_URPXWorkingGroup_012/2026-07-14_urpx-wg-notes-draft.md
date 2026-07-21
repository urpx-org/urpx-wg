

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#012

#### Date: 2026-07-14 11.30AM US ET

**Attendees:**
**Regrets:**
**Notetaker:**

## Meeting Notes

---

#### 1. Quick Hellos

-

---

### 2. URPX Status Update

- v0.3.0 candidate ontology + SHACL prepared and audited; five-part worked example (ConEd SC1 Rate I) validates end to end.
- Released v0.2.1 unchanged; all v0.3.0 material is candidate-stage pending group review.
- Questions on status:

---

### 3. Model Update Walkthrough

- Discussion:
- Concerns raised:
- Publication patterns members want exercised against the model:
- Position on the `RatePlanVersion` re-meaning:
- Feedback on the open vocabulary items (filing-level cancellation; component validity dates; confidence on the coverage claim):

---

### 4. Terminology: "price" replaces "rate"

- Reaction to the price / rate plan / `RateGroup` framing:
- Terminology-section draft (accepted / changes requested):

---

### 5. Release & Licensing

- Review window agreed:
- Assent to `RatePlanVersion` re-meaning (sense of the room):
- LFX vote to approve v0.3.0 and authorise going public (set up after this review):
- License conversion (W3C Document License + CDLA-Permissive) and LF Energy IP scan, as conditions of publication:

---

### 6. Test Data & SHACL

- Closed-shapes policy discussion:
- Validation workflow questions:

---

### 7. Other Business & Next Steps

- Feedback owners:
- Next regular meeting: 2026-07-21 (today is an additional v0.3.0 review session):
- Volunteer roles:

## Action Items

| # | Action | Owner | Due |
| :---- | :---- | :---- | :---- |
| 1 | | | |


Zoom AI Summary:

Quick Recap

The meeting focused on the progress and upcoming public release of the URPX standard, with Klaar presenting the major changes in the v0.3.0 draft version. The new model introduces the concept of rate plan versions, which reconcile pricing data from various sources into a consumable format for cost calculations. Don Jackson shared his implementation experience with URPX and a public OpenADR3 price server for California. The group discussed the timeline for making the standard public, with Klaar aiming for a launch soon, possibly before the next meeting. Jeremy Roberts from the Green Button Alliance and participants from the California Energy Commission were introduced and participated in the discussion. The meeting also covered the documentation and website preparations for the public release, and Klaar announced that a formal vote would not be required to go public.

Next Steps

Klaar: Merge the 030 draft version to the main branch after final review.
Klaar: Rename the 021 working group review branch to 030 after the meeting.
Klaar: Push the URPX website staging environment to production and make URPX.org go live, potentially before the next meeting.
Klaar: Reach out to the LF Energy team to redo the IP licensing scan for the 030 version.
Klaar: Send out communication to the working group about the public release and URPX.org go-live.
Klaar: Make herself available for feedback on the 030 draft via email, Slack, GitHub, or phone.
Jeremy: Review the 030 draft version and provide feedback within about a week.
Jeremy: Present the URPX support topic at the Green Button Alliance board meeting on the 23rd for official approval.
Shubham and Stefanie: Look into contributing complex California rate plan examples, specifically the NBT modifier, to test the URPX model.
Klaar: Send around links to the GitHub pages URLs for the URPX website and documentation.
Klaar: Reach out to the rest of the working group for potential logo contributions to the URPX website.
Working Group Members: Review the URPX documentation and website content for clarity and accuracy.
Working Group Members: Contribute new tasks or feedback directly into the URPX dev doc tasks folder.


Summary


Green Button and MIDAS Integration:

The meeting included introductions between team members, with Klaar welcoming Shubham from the California Energy Commission who manages the MIDAS standards, and Jeremy from the Green Button Alliance. Jeremy explained that the Green Button Alliance, founded in 2015, focuses on expanding beyond the Green Button standard to interface with other standards like MIDAS, noting the complementary nature of the two standards. The discussion touched on ongoing work mapping scenario inputs to cost models and rate plan data that can be mapped to bill line items, with Don Jackson's previous notes on this mapping already shared with the team.



URPX Draft Version Discussion:

Klaartje led a meeting to discuss the draft 030 version of URPX, highlighting significant changes that bridge traditional tariff filings with machine-to-machine capabilities, focusing on born-digital rate plans. Don Jackson, a prolific contributor, shared his work on setting up an OpenADR3 public price server using URPEX to compute modeled rate plans for California retail tariff filings. The team discussed the new system's four-layer structure, emphasizing that URPX handles data representation and structuring but does not include provider-specific calculation logic, leaving implementers to handle resolution and validation. Next steps include gathering expert reviews before going public, finalizing test data sets, and determining a reasonable timeline for the release.



URPX Framework and Reconciliation:

Klaartje explained that reconciliation functionality is not included in URPX and is currently the responsibility of consumers who either write their own code or use existing products/services. She described how URPX provides a framework for rate plan versions with simplified source references and new concepts like tariff filings and coverage claims. The discussion covered how pricing models can be linked to their original publications through price definition references, and how model collections allow grouping of related pricing models like heating assistance programs that span different iterations.



URPX Model Development Updates:

Klaartje presented updates on the URPX model development, including new concepts like rate plans and the ability to handle non-contiguous time series data through price definition cancellations. The working group discussed potential challenges with complex rate plans, particularly in California, and Shubham's team expressed interest in collaborating on handling NBT modifiers. Stefanie introduced herself as the load flexibility lead at the California Energy Commission working on the MIDAS project, and Klaartje invited her team to contribute complex use cases for testing the model. The conversation ended with a discussion about the timeline for releasing the new URPX version after review by the working group.



URPX Repository Public Launch:

The team discussed making the URPX repository and documentation public, with Klaar planning to launch URPX.org during the next Tuesday meeting. Jeremy and Don expressed support for going public without requiring a formal vote. Klaartje agreed, noting that the technical review with LF Energy was complete and the current version represents a reasonable starting point. The group reviewed documentation efforts including a new website and dev docs folder for ongoing collaboration, with Jeremy suggesting additional documentation and code examples to help users understand the system. Klaar will communicate the decision to the working group and proceed with making the repository public before the next meeting.