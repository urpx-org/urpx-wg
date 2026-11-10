---
id: agendaurpx20261110
title: "URPX Working Group agenda, 2026-11-10 (#020)"
desc: "Draft agenda for meeting #020, built to turn attendance into contribution: open vocabulary pull requests reviewed and merged live, a sandbox submission each member can make, the scenario cost model working session, the specific roles the group needs filled, and how members can help grow the group. Draft for the chair to review and publish to urpx-org/urpx-wg."
updated: 1794700800000
created: 1794700800000
author: "Draft for the chair to review + publish"
---

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#020

#### Date: 2026-11-10 11.30AM US ET (8.30AM US PT)

_This agenda is built around contribution. Most items end with one small, concrete thing you can do, in the meeting or after._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Welcome and introductions | New members; what you are building; where you would like to contribute | Klaartje, All | 5 min |
| 2 | Open pull requests | Don Jackson's open vocabulary pull requests, reviewed together and merged where the room agrees | Klaartje, All | 20 min |
| 3 | Contribute a rate plan | The first sandbox submission is in; a walk-through, and a plan each member can bring | Klaartje, All | 10 min |
| 4 | Scenario cost model | Schedule the working session; cost models and customer data | Klaartje, All | 7 min |
| 5 | Roles we are looking to fill | Co-maintainer, co-chair, approvers, the OpenSSF badge effort | Klaartje, All | 8 min |
| 6 | Growing the group | Outreach to utilities and researchers, and how members can help | All | 8 min |
| 7 | Other business and next meeting | Action items from #019; next meeting date | Klaartje, All | 2 min |

---

### 1. Welcome and introductions

Anyone joining for the first time is welcome to say hello, how they found URPX, what they are building, and where they would like to contribute.

**One thing you can do:** if URPX has come up in a conversation since the launch, bring it to the group.

### 2. Open pull requests

Don Jackson has several open pull requests against [`urpx`](https://github.com/urpx-org/urpx). The meeting reviews them together and merges what the room agrees; two already have the group's agreement from #019 and are ready to finalize.

| Pull request | What it changes | Status |
| :---- | :---- | :---- |
| [#71](https://github.com/urpx-org/urpx/pull/71) | Days of the week on a time bracket | Agreed at #019 to use numeric ISO 8601 day values; finalize and merge |
| [#77](https://github.com/urpx-org/urpx/pull/77) | A Monday-if-Sunday holiday observance rule | Reviewed at #019; ready to merge |
| [#76](https://github.com/urpx-org/urpx/pull/76) | Value expressions with minimum and maximum, for formula-defined thresholds and bounds | Under review; discuss the open points |
| [#72](https://github.com/urpx-org/urpx/pull/72) | A scenario cost model naming the modifier versions and profile alternatives it prices under | Deep-dive scheduled; see item 4 |
| [#80](https://github.com/urpx-org/urpx/pull/80) | Bound offsets on a service bracket | New since #019; first look |
| [#70](https://github.com/urpx-org/urpx/pull/70) | Documentation: multi-valued `basedOnPrice` and `applicableTo` values are alternatives | Documentation only |
| [#88](https://github.com/urpx-org/urpx/pull/88) | Pin the regeneration workflow runner | Housekeeping |

Under the pre-1.0 versioning table in the [README](https://github.com/urpx-org/urpx#versioning-scheme), additive changes are a patch release.

**One thing you can do:** pick one pull request and leave a comment on it, even a short one. A second reader is the single most useful contribution right now.

### 3. Contribute a rate plan

The community sandbox, [`urpx-data-sandbox`](https://github.com/urpx-org/urpx-data-sandbox), now carries its first worked submission, the PG&E E-ELEC rate plan, and a [submission guide](https://github.com/urpx-org/urpx-data-sandbox/blob/main/submissions/README.md). A submission is a rate plan transcribed into URPX, its source document alongside it, validated automatically for conformance. The worked example is there to copy. We will walk the process in the meeting for anyone who wants to see it.

**One thing you can do:** pick a rate plan you know and bring it, or bring the one question stopping you from submitting it.

### 4. Scenario cost model

The scenario cost model, where a rate plan and its modifiers are assembled with a customer's situation to produce a cost calculation, needs a dedicated working session with worked examples, because it is where URPX meets customer-data standards such as Green Button. We will set a date and confirm who should be in the room.

**One thing you can do:** if cost modelling or customer data is your area, say so, and we will make sure the session suits you.

### 5. Roles we are looking to fill

The work is growing faster than one maintainer can carry, and spreading it is how the group becomes a group. Three concrete openings:

- **Co-maintainer and co-chair** to carry administrative work, such as agendas and minutes, so the chair can focus on the vocabulary itself.
- **Approvers** who review pull requests and merge them. Opening a pull request is already open to every member; merging is held by a small group that needs to grow.
- **A lead for the OpenSSF badge effort**, which LF Energy's mentoring program can support, and which moves URPX toward its next project stage.

**One thing you can do:** if any of these fits the time you have, tell the chair, in the meeting or by email.

### 6. Growing the group

The clearest gap is utility participation. The group discussed the value a standard offers a utility, from the cost of billing errors to getting customers onto the rate plans that fit them, and a research framing as a warm way to bring utilities and regulators into the conversation. We are also looking for more academic partners.

**One thing you can do:** bring one introduction, to a utility contact or a researcher working in this space, or help spread the word that the meetings are open.

### 7. Other business and next meeting

Action items from meeting #019, any other business, and the next meeting date, 2026-11-24.
