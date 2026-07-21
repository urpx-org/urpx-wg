# URPX Branding & Language Kit

**Version:** 1.0 Draft  
**Last Updated:** January 2026  
**Maintainer:** Flux Tailor LLC

---

## Table of Contents

1. [Brand Identity](#brand-identity)
2. [Terminology Standards](#terminology-standards)
3. [Key Messages](#key-messages)
4. [Voice & Tone](#voice--tone)
5. [Boilerplate Text](#boilerplate-text)
6. [Visual Identity](#visual-identity)
7. [Usage Guidelines](#usage-guidelines)

---

## Brand Identity

### Name

**URPX** — Utility Rate Plan Exchange

- Always capitalize: URPX (not Urpx, urpx)
- Pronounced: "U-R-P-X" (spell out each letter)
- Full name on first reference, then URPX thereafter

### Tagline Options

**Primary:**
> The semantic switchboard for utility rate plan data

**Alternatives:**
> Machine-readable rate plans for the energy transition  
> Open standard for rate plan data exchange  
> Connecting rate plan data across the energy ecosystem

### Mission Statement

> Promote market competition, affordability, transparency, and innovation in the energy sector by introducing an open standard for the exchange and publication of machine-readable utility rate plan data from distribution, retail, and other utility service providers.

### Brand Traits

| Trait | Meaning | How It Shows Up |
|-------|---------|-----------------|
| **Transparent** | Open data, clear structures, nothing hidden | Open source, public documentation, community governance |
| **Interoperable** | Works across systems, standards, organizations | Formal mappings to Green Button, CDS, CIM, OpenADR |
| **Trustworthy** | Reliable, validated, community-governed | SHACL validation, LF Energy oversight, versioning |
| **Modern** | Built for the future | Semantic web technologies, JSON-LD, GraphQL |
| **Community-driven** | Open collaboration | Working group model, public contributions |

---

## Terminology Standards

### Required Terms

Always use these terms consistently across all URPX materials:

| ✅ Use | ❌ Avoid | Notes |
|--------|----------|-------|
| **Rate plan** | Rate, tariff, rate schedule, rate structure | "Rate plan" is the standard URPX term for the complete pricing structure |
| **Rate plan data** | Rate data, tariff data | When referring to the information URPX exchanges |
| **Charge** | Fee, cost component | Specific billable element within a rate plan |
| **Customer profile** | Customer type, customer class | The set of attributes describing a customer |
| **Service point profile** | Meter profile, usage profile | Physical connection characteristics |
| **Eligibility rule** | Qualification, requirement | Conditions for rate plan access |
| **Applicability rule** | Condition, trigger | When a charge applies |
| **Time-of-use period** | TOU period, time block | Acceptable to abbreviate as "TOU period" |

### Organization Names

| ✅ Correct | ❌ Incorrect |
|-----------|-------------|
| NLR (National Laboratory of the Rockies) | NREL |
| Flux Tailor | FluxTailor, Flux-Tailor |
| LF Energy | Linux Foundation Energy |
| LFESS | LF Energy Standards and Specifications (spell out on first use) |

### Technical Terms

| Term | Definition | Usage |
|------|------------|-------|
| **Ontology** | Formal semantic model defining rate plan concepts and relationships | "The URPX ontology defines..." |
| **Semantic web** | W3C standards for machine-readable linked data | Reference when explaining technical foundation |
| **RDF** | Resource Description Framework | Use in technical contexts |
| **OWL** | Web Ontology Language | Use in technical contexts |
| **SHACL** | Shapes Constraint Language | "SHACL validation ensures data quality" |
| **JSON-LD** | JSON for Linked Data | "Data delivered via JSON-LD" |

### Phrases to Use

**The switchboard metaphor:**
> URPX acts as the semantic "switchboard" for transforming flat rate plan data into structured rate plans with executable cost modeling instructions.

**The problem statement:**
> Today's utility rate plan landscape is fragmented. Each vendor uses proprietary systems. Rate plan data in machine-accessible form is rarely available.

**The value proposition:**
> URPX provides a comprehensive, standardized method for representing and exchanging utility rate plan data in machine-accessible format.

---

## Key Messages

### For Regulators

> URPX provides standardized, AI-ready access to rate plan data. With machine-readable rate plans, regulatory analysis that once took weeks can happen in hours. Market transparency improves when rate plan structures are consistently documented and comparable across utilities.

### For Developers

> Stop building custom parsers for every utility. URPX gives you consistent APIs and data structures across territories. The semantic model means your code understands rate plan relationships, not just data fields.

### For Utilities

> Publish rate plans once, serve them everywhere. URPX reduces customer service calls by making rate plan information self-documenting. Standardized formats lower vendor integration costs and improve data quality.

### For Customers

> Understand your energy costs. URPX-powered tools let you compare rate plans, see what you qualify for, and model how changes affect your bill — without calling your utility.

### For Researchers

> Analyze rate plan structures across markets with consistent data. URPX provides the standardized format needed for large-scale pricing pattern analysis and policy impact studies.

---

## Voice & Tone

### Voice Characteristics

| Characteristic | Description | Example |
|----------------|-------------|---------|
| **Clear** | No jargon without explanation | "Rate plans (the pricing structures that determine your energy bill)" |
| **Direct** | Say what needs to be said | "The current landscape is fragmented. URPX fixes that." |
| **Confident** | We know this problem well | "We've seen this across dozens of implementations." |
| **Collaborative** | Community-first | "Join us in solving this together." |
| **Pragmatic** | Focus on real problems | "Customers shouldn't need to call their utility to understand their bill." |

### Tone by Context

| Context | Tone | Example |
|---------|------|---------|
| **Technical docs** | Precise, detailed | "The `urpx:EligibilityRule` class encodes conditions..." |
| **Marketing** | Energetic, benefit-focused | "Finally — rate plan data that just works." |
| **Presentations** | Engaging, story-driven | "Imagine a world where..." |
| **Social media** | Conversational, punchy | "Rate plan complexity? There's a standard for that." |
| **Puppet/mascot** | Playful but honest | "Look, I know rate plans are confusing. That's kind of the point." |

### Words to Embrace

- Transparent, open, accessible
- Standardized, consistent, reliable
- Machine-readable, semantic, structured
- Interoperable, connected, integrated
- Community, collaboration, together

### Words to Avoid

- Proprietary, closed, siloed
- Complex (when describing URPX itself)
- Revolutionary, disruptive (too hyperbolic)
- Simple (rate plans aren't simple; URPX makes them manageable)

---

## Boilerplate Text

### One-liner (25 words)

> URPX is an open standard for exchanging machine-readable utility rate plan data, enabling transparent energy pricing across the industry.

### Short description (50 words)

> URPX (Utility Rate Plan Exchange) is an open standard for machine-readable utility rate plan data. Built on semantic web technologies, URPX acts as the switchboard for transforming flat rate plan data into structured formats with executable cost modeling instructions. Hosted by LF Energy Standards and Specifications.

### Medium description (100 words)

> URPX (Utility Rate Plan Exchange) is an open standard that enables transparent, machine-readable utility rate plan data exchange. While standards exist for customer usage data and grid operations, no comprehensive standard previously existed for the rate plan data that determines how customers are charged.
>
> Built on W3C semantic web technologies (RDF, OWL, SHACL), URPX provides a rich ontology for representing everything from simple flat-rate plans to complex time-of-use structures. Led by Flux Tailor with NLR collaboration, URPX is hosted by LF Energy Standards and Specifications (LFESS).

### Full description (200 words)

> URPX (Utility Rate Plan Exchange) addresses a critical gap in energy data infrastructure. While standards exist for customer usage data (Green Button) and grid operations (CIM), no comprehensive standard existed for the rate plan data that determines how customers are charged for energy.
>
> Today's utility rate plan landscape is fragmented. Each vendor uses proprietary systems for cost calculations. Rate plan data in machine-accessible form is rarely available from utilities. When it is available, there's no standard format for the logic, eligibility rules, or customer profile attributes needed to compute costs accurately.
>
> URPX acts as the semantic "switchboard" for transforming flat rate plan data into structured rate plans with executable cost modeling instructions. Built on W3C semantic web technologies (RDF, OWL, SHACL), the standard provides:
>
> - Modular ontology for rate plan structures
> - Machine-readable eligibility and applicability rules
> - Temporal versioning with regulatory approval tracking
> - Formal mappings to Green Button, LF Energy CDS, and other standards
>
> Led by Flux Tailor with formal NLR collaboration, URPX is developed through open collaboration under LF Energy Standards and Specifications (LFESS) governance.

---

## Visual Identity

### Color Palette

**Primary Palette**

| Color | Hex | RGB | Usage |
|-------|-----|-----|-------|
| URPX Teal | `#44BB99` | 68, 187, 153 | Primary brand color, nodes |
| URPX Blue | `#2563EB` | 37, 99, 235 | Accent color, edges, links |
| White | `#FFFFFF` | 255, 255, 255 | Backgrounds |
| Dark Green | `#008A5C` | 0, 138, 92 | Dark mode, contrast |

**Extended Palette (Paul Tol Light — for infographics)**

| Color | Hex | Name |
|-------|-----|------|
| Light Blue | `#77AADD` | For secondary data |
| Orange | `#EE8866` | Warnings, highlights |
| Yellow | `#EEDD88` | Caution states |
| Pink | `#FFAABB` | Tertiary accent |
| Cyan | `#99DDFF` | Information |
| Mint | `#44BB99` | Primary (same as brand) |
| Lime | `#BBCC33` | Success states |
| Olive | `#AAAA00` | Neutral accent |
| Grey | `#DDDDDD` | Disabled, borders |

### Typography

**Recommended fonts:**
- **Headings:** Inter, system sans-serif
- **Body:** Inter, system sans-serif  
- **Code:** JetBrains Mono, monospace

### Logo Usage

The co-branded LF Energy URPX logo package lives at [`branding/graphics/URPX_logo_Package/`](../graphics/URPX_logo_Package/): the full logo and the icon mark, each in Black, Color, and White versions, as EPS, PNG, and SVG.

- Minimum clear space: Height of "U" in URPX on all sides
- Minimum size: 24px height for digital, 0.5" for print
- Do not stretch, rotate, or add effects
- Use appropriate color version for background

---

## Usage Guidelines

### When Writing About URPX

1. **First reference:** "URPX (Utility Rate Plan Exchange)"
2. **Subsequent references:** "URPX"
3. **Always use:** "rate plan" (not rate, tariff, rate schedule)
4. **Include context:** Link to lfess.energy or urpx.org when possible

### Co-branding

When URPX appears alongside:

- **LF Energy / LFESS:** URPX logo should be equal or smaller
- **Flux Tailor:** Note "Led by Flux Tailor" in text, not logo lockup
- **NLR:** Note "In collaboration with NLR" in text

### Social Media

**Hashtags:**
- Primary: #URPX
- Related: #LFEnergy #OpenEnergy #EnergyData #RatePlans

**Handle:** none established yet — announcements go through LF Energy channels and the working group mailing list (urpx-wg@lists.lfenergy.org)

### Attribution

When referencing URPX in publications:

> URPX (Utility Rate Plan Exchange) is an open standard hosted by LF Energy Standards and Specifications. Learn more at [urpx.org].

---

## Appendix: Quick Reference Card

| Element | Standard |
|---------|----------|
| Name | URPX |
| Pronunciation | U-R-P-X |
| Full name | Utility Rate Plan Exchange |
| Primary color | `#44BB99` |
| Accent color | `#2563EB` |
| Key term | Rate plan (not rate, tariff) |
| Organization | NLR (National Laboratory of the Rockies, formerly NREL) |
| Tagline | The semantic switchboard for utility rate plan data |
| Host | LF Energy Standards and Specifications (LFESS) |
