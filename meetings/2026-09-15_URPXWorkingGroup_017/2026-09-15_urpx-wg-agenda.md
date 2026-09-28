# Utility Rate Plan Exchange (URPX) Working Group Meeting \#017

#### Date: 2026-09-15 11.30AM US ET (8.30AM US PT)

_v0.5.0 is tagged. v0.5.1 carries the license transition and follows shortly, and the tree goes to LF Energy for IP review after that tag. Two parts of this session are discussions rather than reports: how the repositories should be laid out when people outside this group can see them, and what we should ask of a community data submission. Both need your input more than they need our proposal._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Quick recap; welcome new and returning participants; volunteer note-taker for today's minutes | Klaartje, All | 4 min |
| 2 | URPX Status Update | v0.5.0 is tagged; v0.5.1 follows. One correction to the September 8th note on which tag carries the license transition. Then a discussion: how the repositories should be laid out when the standard goes public | Klaartje, All | 18 min |
| 3 | Ontology | No vocabulary change in either tag. Where the design work is heading, including greenhouse gas emissions and green rate plans | Klaartje, All | 5 min |
| 4 | SHACL Rules | No shape change in either tag. The closed-shapes policy carries forward. What validating against URPX has actually been like for you | Klaartje, All | 4 min |
| 5 | API | Still requirements gathering. What you would need from an API over published rate plans | All | 4 min |
| 6 | Documentation | Term identifiers now resolve at urpx.org, one document per term. One build produces the documentation site and the namespace pages from a single release tag. What the licenses are now. Member-organization logos | Klaartje, All | 6 min |
| 7 | Test Data | The twelve shipped examples at v0.5.1. Then a discussion: what we should ask of a community data submission | All | 14 min |
| 8 | Other Business & Next Steps | Volunteer roles; action items carried from meeting 16; next meeting date | Klaartje, All | 5 min |

---

#### 1. Quick Hellos

- Quick recap.
- Welcome any new or returning participants.
- Volunteer note-taker for today's minutes.

---

### 2. URPX Status Update

- **v0.5.0 is tagged.** The term identifiers moved to `urpx.org`. A term is now written `https://urpx.org/ns/ontology/RatePlan`, the published JSON-LD context sits at `https://urpx.org/ns/context/`, and every generated artifact was regenerated against that base.

- **v0.5.1 is the license transition, and it is not yet tagged.** Specification documents move to the W3C Document License, data sets move to CDLA-Permissive-2.0, and source code and metadata stay Apache-2.0. The vocabulary and the shapes do not change across it. Only license identifiers, version literals and generated artifacts moved.

- **One correction to the note of September 8th.** That note said the license transition would ship inside v0.5.0 and that there would be no separate tag for it. It shipped one tag later instead. v0.5.0 carried the namespace alone so the publication mechanism could be built against a tree whose identifiers were already final, and the license transition became v0.5.1. The content is the same; the tag it landed in is not.

- **The tree goes to LF Energy for IP review once v0.5.1 is tagged.** That review reads the tagged tree. It is the last gate before the repository and `urpx.org` go public.

- **What happens next, in order.** IP review clears, then the repository goes public and `urpx.org` serves the namespace and the documentation. v0.6.0 carries the additive highly dynamic prices work and lands after the public flip, not before it.

#### Discussion: how the repositories should be laid out when we go public

_Nothing here is decided, and the group has not seen materials in advance, so the proposal is walked from scratch._

**The problem.** One repository currently holds four different kinds of thing:

1. **The standard.** The ontology, the shapes, the published context, the documentation pages.
2. **The curated test cases.** The twelve worked examples that the documentation site renders as its example gallery.
3. **The design and process record.** Draft specifications, design decisions, reports, open tasks.
4. **Community contributions.** Branches and data sets from members, in varying states of readiness.

That is fine while nobody can see it. On the day it goes public, the first thing somebody who has never seen URPX meets is a repository whose root is mostly work in progress, and the first thing a contributor meets is a submission process written for a standard rather than for an experiment.

**The proposed layout, three repositories:**

```
urpx-org/urpx                the standard
                             ontology · shapes · published context
                             documentation · the curated test cases the site renders

urpx-org/urpx-lab            the design and process record
                             draft specifications · design decisions · reports · open tasks

urpx-org/urpx-data-sandbox   community data
                             contributed data sets · experiments
                             anything not yet validated, or needing vocabulary that does not exist yet
```

**Why three rather than one.** The standard repository is deliberately strict: it does not take new directories without discussion, and it rejects speculative submissions. That is right for a standard and wrong for experimentation. Someone drafting a test case for an unfamiliar utility, or trying a mapping they are not sure about, currently has nowhere to work that is not a pull request against the repository on the critical path to a release.

**Four questions for the group:**

1. **Does the design and process record belong beside the standard, or in its own repository?** Keeping it together means a reader can see how a decision was reached. Splitting it means the standard repository is only the standard. Which of those matters more to you when you open a repository you have never seen?
2. **Do the curated test cases stay with the standard?** They are the content the documentation site renders, so moving them moves the site's content pipeline with them. The proposal keeps them where they are. Is that right, or should everything data-shaped live together?
3. **Are `urpx-lab` and `urpx-data-sandbox` the right names?** A repository name appears in every clone URL anyone ever uses, so it is effectively permanent. Say now if either reads wrong to you.
4. **What does a split make harder?** The honest cost is that things become harder to find. If you have lived through a repository split that went badly, what would you want us to do about it here?

---

### 3. Ontology

- **Neither tag changed the vocabulary.** The last model change was v0.4.0: the identifier pattern, package containment, and the move of calculation method onto the measurement it applies to. If you rewrote your data for v0.4.0, nothing in v0.5.0 or v0.5.1 asks you to rewrite it again.

- **What did change is how a term is written.** Every URPX identifier your data quotes now sits under `urpx.org`. The local names are unchanged, so the rewrite is a prefix substitution rather than a model migration, and the release notes carry it.

- **Greenhouse gas emissions and green rate plans.** Following the discussion at meeting 15, this is being worked as an addition to URPX rather than as a separate standard: how the distribution and supply portions of a rate plan's emissions are represented, so that a carbon calculation can be made from the rate plan itself. Stephen Suffian of WattCarbon offered at meeting 15 to help draft the stub specification, using EIA data for carbon intensity at the balancing-authority level. Design-stage, and open for input.

- **v0.6.0 direction, additive and changing none of the above:** machine-readable value expressions for price calculation in place of string formulas, and the highly dynamic prices bundle, covering published price series, how a consumer discovers them, and the mapping to California's MIDAS upload schema. It lands after the public flip.

---

### 4. SHACL Rules

- **Neither tag changed a shape.** The shapes declare 0.5.1 and are otherwise the v0.4.0 shapes.

- **The closed-shapes policy carries forward.** A property a shape does not name is reported as a violation rather than silently ignored, and a document is validated together with the documents it cites rather than on its own.

- **Question for the group:** for anyone who has run their own data through the shapes, what was that like? Specifically, when validation failed, did the message tell you what to fix? Validation messages are the part of a standard that nobody designs and everybody meets, and we would rather hear about a bad one now than after the flip.

---

### 5. API

The consuming API for published rate plans is still in requirements gathering. There is nothing to review and no decision in it; we are collecting requirements.

- **What would you need from an API that reads published rate plans?** What you would call, what you would need back, and what would make it unusable in your systems.
- Requirements can go straight onto the design task in the repository.

---

### 6. Documentation

- **Term identifiers resolve to one document per term.** `https://urpx.org/ns/ontology/RatePlan` resolves to the definition of that one term, rather than to a fragment of one large file.

- **One build, one tag, two outputs.** The website deployment takes a single URPX release tag and produces both the documentation site and the namespace pages from it. The documentation and the identifiers are built from the same commit, so they cannot describe different versions of the vocabulary.

- **The publication runs on Semantic Flow**, which builds the per-term namespace from the ontology, the shapes and the context. David Richardson wired it into the release build, and Semantic Flow is his project. Two things are worth stating plainly about the choice. URPX carries no Semantic Flow vocabulary, because those terms were removed from the ontology before v0.3.0. And what the tool produces is static files, so nothing has to be reachable at read time for a URPX term identifier to resolve.

- **`urpx.org` currently redirects to the LF Energy project page.** The served namespace replaces that redirect at the public flip. Until then the identifiers are correct and permanent but do not yet answer.

- **The licenses, stated once so nobody has to go looking.** Specification documents are under the W3C Document License. Data sets, including the test cases, are under CDLA-Permissive-2.0. Source code, tooling and repository metadata stay Apache-2.0.

- **Member-organization logos:** if your organization would like to be featured on urpx.org and the LF Energy landing page, please send a logo and confirm we may display it.

---

### 7. Test Data

- **Twelve shipped examples, all at v0.5.1.** Each one declares the URPX version it was written against, each references the published context rather than carrying its own copy, and the whole corpus validates offline. The California rate plan examples including the Net Billing Tariff modifier, the ConEd set, and the two PG&E sets.

- **Twelve is the current count rather than a target.** It is enough to exercise the vocabulary and not enough to represent the range of rate plans in the field, which is the reason for the discussion below.

#### Discussion: what we should ask of a community data submission

_Also not decided. The sandbox does not exist yet, so nothing below is in force._

**What it would be for.** Data sets and experiments that are not ready to be part of the standard: unvalidated data, work in progress, and anything that needs vocabulary URPX does not have yet. A data set that already validates against a released version and needs no vocabulary change does not need the sandbox and can go straight into the curated test cases.

**The proposed bar, in two gates.**

**Gate one, automated.** A submission is validated with SHACL against the shapes of the URPX version it declares, not against whatever is current, and a summary query records what it contains into a browsable index: the organization and jurisdiction named, counts of the principal classes, the effective-date range, and whether it references prices published elsewhere. That gate answers "is this conformant URPX, and what is in it" and nothing else.

**Gate two, a person.** A named reviewer approves before anything is merged, and the approval is recorded as a pull request approval so the record sits with the change.

**What we would say about the data.** Draft wording, and we would rather hear objections now than after it is published:

> Nothing in this repository is reviewed for data content, completeness, or accuracy. A submission is checked for conformance to the URPX version it states it targets, and for nothing else.

**Four questions for the group:**

1. **Is that bar too high or too low for something you would actually submit?** If the answer is that you would not submit under it, that is the most useful thing you can tell us today.
2. **What does a submission need to carry so that somebody else can trust it?** The source document it was built from, the effective dates, the jurisdiction, the date it was captured. What is on your list that is not on ours.
3. **Does the disclaimer read as fair, or as a warning that would stop you using anything in there?** It has to be honest without making the repository useless.
4. **Should a sandbox data set ever be promoted into the curated test cases, and on whose judgment?** That is a governance question rather than a technical one, and it is the group's to answer rather than the chair's.

---

### 8. Other Business & Next Steps

_Time-limited slot._

- Volunteer roles: co-chair, secretary, community outreach.
- Action items carried from meeting 16.
- Next meeting date.

---

## Materials for review

- The standard: https://github.com/urpx-org/urpx
- v0.5.0 release notes: https://github.com/urpx-org/urpx/blob/v0.5.0/documentation/pages/urpx-release-notes-v0.5.0.md
- v0.5.1 release notes: https://github.com/urpx-org/urpx/blob/v0.5.1/documentation/pages/urpx-release-notes-v0.5.1.md
- License transition plan: https://github.com/urpx-org/urpx/blob/v0.5.1/TRANSITION.md
- Meeting agendas and notes: https://github.com/urpx-org/urpx-wg/tree/main/meetings

---

_Corrected 2026-09-28: this agenda as first published stated that v0.5.1 was tagged and that the tree had been submitted for the LF Energy IP review. Neither had happened. The text above is corrected; nothing else in the agenda changed._
