---
id: minutesurpx20261027
title: "URPX Working Group #019 minutes (2026-10-27)"
desc: "Minutes of the 2026-10-27 working-group meeting, the first since the public launch: introductions, the launch and TAC report, the community data sandbox, five open vocabulary pull requests reviewed together, the data-dictionary automation, the committer-status discussion, the LF Energy status and OpenSSF badge, and an outreach discussion. Draft for the chair to review and publish to urpx-org/urpx-wg."
updated: 1794700800000
created: 1794700800000
author: "Draft for the chair to review + publish"
---

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#019

#### Date: 2026-10-27 11.30AM US ET (8.30AM US PT)

**Attendees:** Klaartje De Schepper (Flux Tailor LLC, chair), Shubham Attri (California Energy Commission), Adam Morse, Blade Chapman (Apple Inc.)
**Regrets:** Don Jackson (traveling), Don Coffin
**Notetaker:** from the recording

## Meeting Notes

### 1. Welcome and introductions

This was the first meeting since URPX went public. Adam Morse joined for the first time; an electrical engineer working on distributed-energy simulation, he is building a pricing-and-billing calculator and comes to URPX as a consumer, having worked with the National Laboratory of the Rockies REopt tool, the System Advisor Model, and URDB. He is interested in where URDB is incomplete and where URPX can carry the detail a calculator needs. The chair noted URPX's standing collaboration with the National Laboratory of the Rockies on URDB, and the shared goal of full open access to structured rate-plan data, including the eligibility detail current schemas summarize away.

### 2. Launch and TAC report

URPX is public, and the chair reported that the production machinery held: the website tracks the standard repository, and machines resolve the ontology and SHACL shapes at the hosted namespaces. URPX presented its annual review to the LF Energy Technical Advisory Council two weeks earlier and the response was positive. Shubham Attri congratulated the group on the release and noted that the California Energy Commission is in an early-stage assessment of growing MIDAS toward a rate database and is working to understand URPX more deeply. The Commission is the working group's first regulator.

### 3. Community data sandbox

The sandbox now carries a submission process and a README that explains what it is and is not. It is a place to deposit a transcribed rate plan, validated automatically for conformance to the URPX version it declares and for nothing else; it is not a curated database and not data represented as production-ready. A contributor can follow the written process by hand, or ask a language model to draft a submission from a rate plan and its source documents, with the understanding that accuracy still needs checking by the contributor. The chair distinguished this open deposit space from the separate, resource-intensive work of curating and reviewing datasets against source documents and real bills, which calls for domain expertise and will be a separate effort tied to the sandbox. All URPX datasets are intended to be freely licensed under CDLA-Permissive-2.0. The sandbox has no API; consuming the data into an application is a separate ingestion step that implementers build themselves. Members are invited to contribute a dataset and to tell the chair where the process does not work for them.

### 4. Vocabulary pull requests

The group reviewed five open pull requests from Don Jackson together.

- **Days of the week on a time bracket (#71).** Agreed: the enumerated day values will be ISO 8601 numbers acting as a code list, with the labels carrying the names, so the vocabulary translates cleanly into other languages. Shubham Attri noted MIDAS uses the same numeric ISO 8601 convention. The chair will finalize the change with Don Jackson and merge it.
- **Holiday observance (#77).** The addition of a Monday-if-Sunday observance rule was reviewed and looks correct. The chair noted that holiday rules matter for accuracy, because residential holiday usage runs high and the rate plan carries the rules to generate the holiday dates rather than the dates themselves.
- **Value expressions with minimum and maximum (#76).** The largest change, still under the chair's review and looking like a good path. It extends value expressions, previously used for eligibility, to metric inputs, so a tier threshold or time-of-use bound can be defined by a formula rather than a static value, including virtual inputs computed from measurements such as grid import against export. Shubham Attri observed that MIDAS today carries only time-varying components and skips calculation-based cases such as a net exporter whose price changes, and welcomed URPX addressing those edge cases.
- **Scenario cost model (#72).** Discussed and deferred to a dedicated working session with worked examples, with Don Coffin, Don Jackson and Bruce present. The scenario cost model ties into customer data from other standards, so it connects to the planned work with the Green Button Alliance and the Customer Data working group, which is also why the API shape is still open.
- Blade Chapman asked whether cost models declare the parameters they require; the chair confirmed that is the intent, the rate plan naming the metric inputs and the data granularity a calculation needs, including event prices pulled from an OpenADR server for critical-peak events.

### 5. Data dictionary automation

A change to the ontology automatically regenerates the data dictionary, so manual edits to the dictionary are overwritten. The chair, who is currently the only maintainer, set the automation up to keep her effort low and noted it can be changed if it gets in a contributor's way.

### 6. Governance: committer status

The chair proposed a committer status modelled on the EVerest governance. Blade Chapman cautioned that adding a status gate now would be a hurdle that could turn away interested newcomers, and framed growing contribution as a marketing and audience question for this stage, with a committer role better suited to a later phase once consistent contributors are known. The chair agreed to hold the proposal. She clarified the distinction the group does need: committer access, the ability to open pull requests, is already granted to every working-group member, while merge rights sit with a separate approvers group, today only the chair and Dave Richardson, which needs to grow. She asked for volunteers to help review pull requests and merge them, and for a co-maintainer and a co-chair to carry administrative work such as agendas and minutes.

### 7. LF Energy status and the OpenSSF badge

The working group is moving from incubation toward the next stage, which is tied to the OpenSSF Best Practices badge. The chair's reading is that URPX can meet the passing level now, with gold as the goal. LF Energy runs a mentoring program that could support the effort, and leading that work is something a member could pick up. The longer-term goal is an internationally ratified standard.

### 8. Outreach and other business

The group discussed how to grow involvement, especially from utilities. Blade Chapman suggested approaching utilities with a clear value proposition, and the discussion drew out several: operational efficiency, the cost of billing errors and the penalties and complaints they bring, the difficulty of legacy billing engines that hold rules as code rather than data, and the gains from getting customers onto the rate plans that fit them. The chair described a research and academic framing as a warm way to invite utilities and regulators in, rather than telling them they are doing something wrong, and said she is seeking academic partners and funding, alongside the existing National Laboratory of the Rockies collaboration. Shubham Attri noted that timing matters, since a utility planning a billing-system upgrade is the right moment to introduce URPX, and that MIDAS implementing URPX would build utility confidence. The chair mentioned a reference calculator for the net billing tariff modifier as a worked, hard example. Adam Morse was welcomed and will be added to the committee list and the URPX Committers team.

## Action Items

| Owner | Action |
| :---- | :---- |
| Klaartje, Don Jackson | Finalize #71 with numeric ISO 8601 day values and merge |
| Klaartje | Finish the review of #76 and merge if sound |
| Klaartje | Merge #77 |
| Klaartje | Schedule a dedicated working session on the scenario cost model (#72), with Don Coffin, Don Jackson and Bruce |
| Klaartje | Add Adam Morse to the committee list and the URPX Committers team |
| All | Review the open pull requests and leave comments before meeting #020 |
| All | Consider contributing a dataset to the community sandbox |
| Open | Co-maintainer and co-chair to carry administrative work; volunteers to review and merge pull requests |
| Open | Lead the OpenSSF badge effort, with LF Energy's mentoring program |
