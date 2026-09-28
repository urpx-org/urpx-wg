# Utility Rate Plan Exchange (URPX) Working Group Meeting \#018

#### Date: 2026-09-29 11.30AM US ET (8.30AM US PT)

_Two discussions carry this meeting: what URPX should and should not cover, and what we build next. Come with an idea._

## Agenda

| nr | What | Topics | Who | Time |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Quick Hellos | Recap; welcomes; volunteer note-taker | Klaartje, All | 4 min |
| 2 | URPX Status Update | Repository moves, then the v0.5.1 tag and the IP review. Diagram updates to review | Klaartje, All | 8 min |
| 3 | Ontology | A discussion: what URPX should and should not cover, with emissions as the live case | Klaartje, All | 16 min |
| 4 | SHACL Rules | No shape change. How validating against URPX has gone for you | Klaartje, All | 3 min |
| 5 | API | Requirements gathering. What you would need | All | 3 min |
| 6 | Documentation | Licenses, and the site after the split | Klaartje, All | 4 min |
| 7 | Test Data | Shipped examples; the community data repository | All | 4 min |
| 8 | Other Business & Next Steps | A discussion: what we build next, and where you would like to be involved. Volunteer roles; next meeting | Klaartje, All | 18 min |

---

#### 1. Quick Hellos

- Recap.
- Welcome new and returning participants.
- Volunteer note-taker.

---

### 2. URPX Status Update

- **The repositories are splitting into three**, as agreed at meeting 17. `urpx-org/urpx` keeps the standard. `urpx-org/urpx-dev` takes the design and process record. `urpx-org/urpx-data-sandbox` takes community data. `urpx-org/urpx-wg` is unchanged.
- **If you have a clone**, commit or move anything of your own under `dev-docs/` before you pull. The note sent before this meeting covers it.
- **Then, in order:** a final comprehensive scan, the `v0.5.1` tag, and the tree to LF Energy for IP review.
- **Please review the diagram updates** at https://fictional-chainsaw-y74j7yq.pages.github.io/ and send anything that looks wrong.

---

### 3. Ontology

- No vocabulary change since the last meeting.
- Emissions and green rate plans are in early design, following meeting 15. Nothing is ready for review; this is a scope conversation, not a proposal.

#### Discussion: what URPX should and should not cover

Emissions is the live case, and the questions underneath it are general:

- **Intensity or volumes.** Should URPX carry emissions proportions only, or volumes by gas? Choosing a global warming potential factor list belongs outside URPX either way.
- **Supply and delivery.** Delivery carries emissions as well as supply, and someone may want green delivery and green supply together.

- Is a rate plan's emissions profile part of a rate plan, or something it points at?
- Where is the line between what a rate plan says and what a system does with it?
- What would you not want in URPX, even if someone offered to build it?
- What is missing that you would expect a rate plan standard to carry?

Whatever the room lands on becomes a written scope statement, used to dispose of future proposals.

---

### 4. SHACL Rules

- No shape change. Closed-shapes policy carries forward.
- How validating against URPX has gone for you, if you have tried it.

---

### 5. API

- Still requirements gathering.
- What you would need from an API over published rate plans.

---

### 6. Documentation

- **Licenses:** specification files under the W3C Software Notice and Document License, data sets under CDLA-Permissive-2.0, source code and project metadata under Apache-2.0. The transition completed on September 9th.
- After the split, the documentation site builds from the standard repository alone.
- Member-organization logos, still open from meeting 17.

---

### 7. Test Data

- The shipped worked examples.
- `urpx-org/urpx-data-sandbox` is where community data goes after the split. It carries a plain statement that nothing in it is reviewed for content, completeness or accuracy, only for conformance to the URPX version it targets.

---

### 8. Other Business & Next Steps

#### Discussion: what we build next, and where you would like to be involved

URPX goes public shortly, which makes it easier to contribute to: readable without access, terms resolving at `urpx.org`, a live documentation site.

**What should we build next?**

- Emissions and green rate plans.
- Machine-readable value expressions, so a price calculation is a structure rather than a string formula.
- Highly dynamic prices: published price series, discovery, and the MIDAS mapping.
- An API over published rate plans.

Say which matters most. If what you need is not listed, that is the most useful thing you can say today.

**Where would you like to be involved?** Contributions come in very different sizes:

- Bring a rate plan, especially one that does not fit the model cleanly.
- Review a draft and say where it does not match your part of the industry.
- Validate your own data against the shapes and report what broke.
- Own a section of a specification.
- Bridge to a standard you already know.
- Write an explainer or a walkthrough.

If something is in the way, say so and we will remove it.

**Standing roles, still open:** co-chair, secretary, community outreach.

**Then:**

- Action items from meeting 17.
- Next meeting date.

---

## Materials for review

- The diagram updates: https://fictional-chainsaw-y74j7yq.pages.github.io/
- The note on the repository split.
- The minutes of meeting 17.
