---
id: agendaurpx20261027
title: "URPX Working Group agenda, 2026-10-27 (#019)"
desc: "Draft pre-read agenda for meeting #019, the first since the public launch. Covers the launch update, the community data sandbox, Don Jackson's open vocabulary pull requests to review ahead of the meeting, a proposal to adopt a committer status, and the report back from the LF Energy Technical Advisory Council annual review. Draft for the chair to review and publish to urpx-org/urpx-wg."
updated: 1792972800000
created: 1792972800000
author: "Draft for the chair to review + publish"
---

# Utility Rate Plan Exchange (URPX) Working Group Meeting \#019

#### Date: 2026-10-27 11.30AM US ET (8.30AM US PT)

_This agenda is a pre-read. Each section ends with what to do before the meeting. The meeting decides and merges what the room agrees._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Launch update | URPX is public: release, site, namespace, repositories | Klaartje | 5 min |
| 2 | The community data sandbox | Open for datasets, with a worked example and a submission guide | Klaartje, All | 8 min |
| 3 | Vocabulary pull requests | Four open pull requests from Don Jackson, reviewed together in the meeting | Don Jackson, All | 22 min |
| 4 | Data dictionary updates | The protocol for regenerating the data dictionary when the ontology changes | Klaartje, All | 8 min |
| 5 | Governance proposal | A committer status for URPX | Klaartje, All | 10 min |
| 6 | TAC annual review | Report back from the LF Energy Technical Advisory Council | Klaartje | 4 min |
| 7 | Other Business & Next Meeting | Standing roles; action items from meeting 18; next meeting date | Klaartje, All | 3 min |

---

### 1. Launch update

URPX is public. v0.5.1, released on 2026-10-06, is the first public release. The documentation site is live at [urpx.org](https://urpx.org), and the term identifiers resolve under `urpx.org/ns`. The repositories [`urpx`](https://github.com/urpx-org/urpx), [`urpx-dev`](https://github.com/urpx-org/urpx-dev), [`urpx-data-sandbox`](https://github.com/urpx-org/urpx-data-sandbox) and [`urpx-wg`](https://github.com/urpx-org/urpx-wg) are all public.

**Before the meeting:** browse [urpx.org](https://urpx.org) and note anything that looks wrong or reads poorly.

---

### 2. The community data sandbox

[`urpx-data-sandbox`](https://github.com/urpx-org/urpx-data-sandbox) is open for community datasets. It holds a worked example, the PG&E E-ELEC rate plan, and a [submission guide](https://github.com/urpx-org/urpx-data-sandbox/blob/main/submissions/README.md) that covers what a submission contains, how to build one from a tariff, and how validation works. Every submission is checked for conformance to the URPX version it declares. Nothing in the sandbox is reviewed for content, completeness or accuracy.

Members are invited to contribute a dataset.

**Before the meeting:** read the submission guide and think about a rate plan you could contribute. Bring questions about the process to the meeting.

---

### 3. Vocabulary pull requests

Don Jackson has four open pull requests against [`urpx`](https://github.com/urpx-org/urpx). The meeting reviews them together, decides what the room agrees, and merges those changes live. Review comments left on the pull requests beforehand let the meeting spend its time on the points still open.

| Pull request | What it changes |
| :---- | :---- |
| [#71](https://github.com/urpx-org/urpx/pull/71) | Adds `urpx:DayOfWeekValue` and a `urpx:daysOfWeek` property on `urpx:TimeBracket`, so a bracket can name days such as Monday through Saturday. A bracket with `customDays` must list its days. |
| [#72](https://github.com/urpx-org/urpx/pull/72) | Adds `urpx:consumesModifierVersion` and `urpx:selectsProfileAlternative` to `urpx:ScenarioCostModel`, so a model can name the modifier versions and profile alternatives it prices under. A model names one base version. |
| [#76](https://github.com/urpx-org/urpx/pull/76) | Adds `urpx:ValueExpression`, a structured numeric calculation with `min` and `max` operators, for calculation methods and price update rules. Adds a currency unit of measure. |
| [#77](https://github.com/urpx-org/urpx/pull/77) | Adds `urpx:mondayIfSundayObservance` to `urpx:ObservanceRuleValue`: a holiday that falls on Sunday is observed on Monday, and one that falls on Saturday stays on Saturday. |

Under the pre-1.0 versioning table in the [README](https://github.com/urpx-org/urpx#versioning-scheme), additive changes are a patch release and breaking changes are a minor release.

**Before the meeting:** read the pull requests and leave review comments on those you have a view on.

---

### 4. Data dictionary updates

The data dictionary page and its diagrams are generated from the ontology, so an ontology change changes them. A pull request that changes the ontology can conflict with regenerated dictionary files, and the regeneration check fails when a new class has no section in the dictionary configuration, which sits outside the repository and which contributors cannot edit. The meeting discusses the protocol: who regenerates the dictionary when the ontology changes, in which pull request, and at what point.

**Before the meeting:** if you have changed the ontology in a pull request, note what you ran into with the dictionary files.

---

### 5. Governance proposal: a committer status

The chair proposes that URPX adopt a committer role, modelled on the [EVerest governance](https://everest.github.io/latest/project/governance/governance.html). Committers have write access and merge pull requests that have been approved. They become committers through contribution and a request to the committee, they take on triage and review duties, and they move to emeritus when they are no longer active. Maintainers, who are listed in [MAINTAINERS.md](https://github.com/urpx-org/urpx/blob/main/MAINTAINERS.md), would be committers who also hold ownership of specific areas.

For URPX this would spread merging and review across more members than the one maintainer listed today, and would put the expectations for contributors who take on that work in [GOVERNANCE.md](https://github.com/urpx-org/urpx/blob/main/GOVERNANCE.md). The committee is asked whether to adopt a committer role along these lines.

**Before the meeting:** read the EVerest page and the current [GOVERNANCE.md](https://github.com/urpx-org/urpx/blob/main/GOVERNANCE.md), and bring questions or objections.

---

### 6. TAC annual review report-back

The chair presented URPX's annual review to the LF Energy Technical Advisory Council on 2026-10-13. [TAC outcome, one line.]

**Before the meeting:** nothing is needed.

---

### 7. Other Business & Next Meeting

- Standing roles, still open: co-chair, secretary, community outreach.
- Action items from meeting 18.
- Next meeting date.

**Before the meeting:** if you would take one of the open roles, tell the chair.

---

## Materials for review

- The four pull requests: [#71](https://github.com/urpx-org/urpx/pull/71), [#72](https://github.com/urpx-org/urpx/pull/72), [#76](https://github.com/urpx-org/urpx/pull/76), [#77](https://github.com/urpx-org/urpx/pull/77).
- The [submission guide](https://github.com/urpx-org/urpx-data-sandbox/blob/main/submissions/README.md) for the data sandbox.
- The [EVerest governance page](https://everest.github.io/latest/project/governance/governance.html) and URPX's [GOVERNANCE.md](https://github.com/urpx-org/urpx/blob/main/GOVERNANCE.md).
