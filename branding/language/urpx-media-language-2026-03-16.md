# Utility Rate Plan Exchange (URPX)

**Last Updated:** 2026-03-16

## Table of Contents

- [Basic Info](#basic-info)
- [Description](#description)
- [Overview](#overview)
- [Technical Profile](#technical-profile)
- [Grid Context](#grid-context)
- [Related Projects](#related-projects)
- [Maturity & Adoption](#maturity--adoption)
- [Learn More](#learn-more)
- [Language & Attribution Guidelines](#language--attribution-guidelines)
- [Additional Notes](#additional-notes)

## Basic Info

- LF Energy webpage: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- Website: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- Code: https://github.com/urpx-org
- Documentation: https://github.com/urpx-org/urpx-website/blob/main/introduction/what-is-urpx.md
- Calendar: https://zoom-lfx.platform.linuxfoundation.org/meetings/utility-rate-plan-exchange?view=month
- LinkedIn:
- Community:
	- Mailing List: https://lists.lfenergy.org/g/urpx-wg
	- Slack: https://lfenergy.slack.com/archives/C09NTF8PZTJ
- LFX Insights:
- Other:
	- Working Group Admin Repo: https://github.com/urpx-org/urpx-wg

## Description

A standardized, machine-accessible format and Common Service API specification for representing and exchanging utility rate plan data.

## Overview

URPX (Utility Rate Plan Exchange) is an open semantic standard that provides a comprehensive, standardized method for representing rate plan data from distribution, retail, and other utility service providers — including energy, water, and other utilities — in machine-accessible format. The standard defines a modular ontology — covering rate plan structures, charge classifications, eligibility rules, applicability conditions, geographic territories, and temporal versioning — and a Common Service API specification, enabling governments, utilities, vendors, and technology companies to exchange rate plan information in a consistent, interoperable way.

While standards exist for customer usage data (Green Button / NAESB REQ.21 ESPI) and grid operations (CIM), no comprehensive standard exists for the rate plan data that determines how customers are charged. Today, vendors handling rate plan calculations work in silos using custom logic and proprietary data structures. There is no standard format for representing the logic and customer profile attributes used to compute cost and determine customer eligibility for rate plans. This fragmentation creates barriers to innovation, competition, and transparency in energy markets: customers cannot easily compare rate plans, vendors must build custom integrations for each utility territory, and those tasked with cost data ingest and bill estimation struggle with data quality across territories. URPX addresses this by defining a single semantic model and API specification that any party can implement, reducing the integration problem from N proprietary formats to one shared standard.

Initiated by [Flux Tailor](https://fluxtailor.com/) with collaboration from the National Laboratory of the Rockies (NLR), URPX was contributed to LF Energy in 2025 to ensure open, vendor-neutral governance. Flux Tailor serves as working group chair, guiding the specification's development within LF Energy's collaborative standards ecosystem. NLR maintains the Utility Rate Database (URDB), and a formal MOU governs the collaboration between the two organizations on open standard development. While the URPX ontology can reference URDB data, the two formats serve different purposes: URDB contains summary-level pricing data, whereas URPX defines structured rate plan representations with executable cost modeling logic, eligibility criteria, and applicability conditions that go well beyond what URDB captures. The standard is built on W3C semantic web technologies (RDF, OWL, SHACL) with data instances in JSON-LD, made available through GraphQL or REST APIs. From simple flat-rate plans to complex ratchet and time-of-use structures and highly dynamic pricing, URPX provides the shared language required to compute costs accurately and consistently.

## Technical Profile

### What It Does

Defines a standardized ontology, exchange format, and Common Service API specification for utility rate plan data, including rate structures, charge types, eligibility rules, applicability conditions, and temporal versioning, enabling machine-readable representation and programmatic exchange of rate plan information across utility territories.

### Problem(s) Solved

Eliminates the need for vendors and technology companies to reverse-engineer each utility's proprietary rate plan data structures. Provides a common semantic model and API that enables consistent rate plan representation across utilities, allowing customers to compare rate plans, vendors to scale across territories without custom integrations, DER developers to integrate structured pricing signals into optimization and control systems, and regulators to perform reliable analysis with lower data integration costs.

### Key Capabilities

- Comprehensive rate plan ontology in RDF/OWL covering core rate plan structure and billing model, charge classifications and calculation logic, geographic applicability and jurisdiction, and organizational and regulatory metadata — representing everything from simple flat-rate plans to complex ratchet and time-of-use structures and highly dynamic pricing
- Common Service API specification (REST and GraphQL) for programmatic discovery, retrieval, and querying of published rate plan data, with SPARQL endpoint for advanced semantic queries
- Multiple document types: rate plans, rate plan modifiers (add-on pricing that layers onto a base rate plan), tariff book documents, tariff statement documents (PSC filings), supply prices documents (competitive market pricing), real-time prices documents, and DER export prices
- Rich eligibility rules that define who qualifies for a rate plan, evaluating customer profile attributes (customer class, entity type, tax status, income level) and service point attributes (connection type, voltage level, service territory, DER capability)
- Applicability conditions that define when charges apply, evaluating usage conditions (thresholds, demand levels, power factor), time conditions (TOU periods, seasons, billing cycles, day types), and other conditions (service territory, voltage level)
- Rule evaluation logic with Boolean operators (AND, OR, NOT), comparison operators, and multiple condition types (customer-based, usage-based, time-based, geographic, measurement)
- Temporal versioning and regulatory tracking of rate plan definitions, including full version history and structured tracking of proposed, approved, and retired plans
- Standards alignment with formal SKOS-based mappings to Green Button / NAESB REQ.21 ESPI (rate plan context for usage data), LF Energy CDS (account and billing data alignment), CIM (grid operations), and OpenADR (demand response); interoperability with M2M communication standards including IEEE 2030.5 (SEP) and Matter
- Data validation and conformance using SHACL constraints for schema validation, conformance testing, and data quality enforcement
- Data instances in JSON-LD, accessible through GraphQL or REST APIs
- Reference implementation (planned)
- Test data repository for implementation validation (planned)

### Relevant Standards

URPX is itself an emerging standard — a new open semantic standard for rate plan data exchange. It does not implement an existing industry standard; it aims to become one. URPX is built on W3C semantic web standards (RDF, OWL, SHACL, JSON-LD) and provides formal semantic mappings to related industry standards including Green Button (NAESB REQ.21 ESPI), CIM, LF Energy CDS, and OpenADR.

## Grid Context

### Grid Segment

Behind the Meter, Distribution

### Function

Interoperability & Data

### Industry Solution Categories

#### Solution Type

- Rate Plan Data Standard: Provides a standardized ontology, exchange format, and Common Service API specification for utility rate plan data, enabling machine-readable representation, programmatic access, and interoperable exchange across utilities and vendors.

#### Component of

- Energy Data Infrastructure: Standardizes the rate plan data layer that connects DER optimization platforms, customer-facing applications, utility billing systems, regulatory analysis tools, and energy service providers, enabling interoperable exchange of rate structures, eligibility rules, and charge conditions across the energy data ecosystem.

### Cross-Cutting Tags

- **Project Intent:** Applied
- **AI/ML:** No
- **Deliverable Type:** Specification

## Related Projects

- **CDS Customer Data**: Complementary — CDS Customer Data defines how authorized third parties access customer energy data (accounts, billing, usage) from utilities via standardized APIs. URPX defines the standardized format for rate plan data that applies to those customers. A third party using CDS Customer Data to pull customer usage data would need URPX-formatted rate plans to calculate bill impacts. Specific integration points include service account references, billing cycle synchronization, and service agreement attributes used in URPX eligibility rules.
- **CDS Registration**: Complementary — CDS Registration defines how third parties discover utility API capabilities and establish secure connections. URPX leverages CDS Registration's Server Metadata for geographic territory mapping and utility capability discovery, providing the upstream connectivity layer needed to access URPX-formatted rate plan data from utilities.

## Maturity & Adoption

### LF Energy Stage

LFESS Working Group

### Deployment Maturity

R&D

### Supporting / Adopting Companies

- [Flux Tailor](https://fluxtailor.com/) (initiating sponsor, technical lead, and working group chair)
- National Laboratory of the Rockies (NLR) (formal MOU partnership for open standard development; maintains the Utility Rate Database)

## Learn More

- [TAC proposal](https://github.com/lf-energy/tac/issues/600)
	- Date: 2025-08-03
	- Type: TAC proposal
	- Local filepath: `LF Energy/ecosystem/projects/urpx/assets/2025-08-03_urpx.pdf`
- URPX: Utility Rate Plan Exchange Standard
	- Date: 2025-10-09
	- Type: Presentation
	- Local filepath: `LF Energy/ecosystem/projects/urpx/assets/2025-10-09_urpx.pdf`
- [LF Energy webpage snapshot](https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/)
	- Date: 2026-03-11
	- Type: Webpage
	- Local filepath: `LF Energy/ecosystem/projects/urpx/assets/2026-03-11_urpx-webpage.pdf`
- URPX code snapshot
	- Date: 2026-03-11
	- Type: Code
	- Local filepath: `LF Energy/ecosystem/projects/urpx/assets/2026-03-11_urpx-main`

## Language & Attribution Guidelines

This section provides guidance for anyone creating derived works (slide decks, webpage blurbs, press releases, social media) from this document.

### Terminology

Always use "rate plan" — not "rate," "tariff," or "rate schedule" — when referring to the pricing structures URPX represents. "Rate plan" is the standard URPX term and should be used consistently across all materials.

Additional terminology standards:

| Use | Avoid | Notes |
|-----|-------|-------|
| Rate plan | Rate, tariff, rate schedule | Complete pricing structure |
| Rate plan data | Rate data, tariff data | The information URPX exchanges |
| Charge | Fee, cost component | Specific billable element |
| Customer profile | Customer type, customer class | Set of attributes describing a customer |
| Service point profile | Meter profile, usage profile | Physical connection characteristics |
| Eligibility rule | Qualification, requirement | Conditions for rate plan access |
| Time-of-use period | TOU period, time block | Abbreviation "TOU period" is acceptable |

### Organization Names & Ordering

| Correct | Incorrect |
|---------|-----------|
| NLR (National Laboratory of the Rockies) | NREL |
| Flux Tailor | FluxTailor, Flux-Tailor |
| LF Energy | Linux Foundation Energy |
| LFESS (spell out on first use) | LF Energy Standards and Specifications (without abbreviation after first use) |

When listing project contributors, Flux Tailor is always listed first as the initiating sponsor and working group chair, with a link to https://fluxtailor.com/ where format allows. NLR is listed second as a collaboration partner. Example: "Initiated by [Flux Tailor](https://fluxtailor.com/) with collaboration from the National Laboratory of the Rockies (NLR)."

### Attribution in Derived Works

All derived materials should include:

- Flux Tailor as initiating sponsor and working group chair (listed first, with website link where format allows)
- NLR as collaboration partner (listed second)
- LF Energy / LFESS as the host organization and governance framework
- Link to the canonical version of this document at https://github.com/urpx-org/urpx-wg when practical

### Boilerplate Text

**One-liner (25 words):**
URPX is an open standard for exchanging machine-readable utility rate plan data, enabling transparent energy pricing across the industry.

**Short description (50 words):**
URPX (Utility Rate Plan Exchange) is an open standard for machine-readable utility rate plan data. Built on semantic web technologies, URPX acts as the switchboard for transforming flat rate plan data into structured formats with executable cost modeling instructions. Hosted by LF Energy Standards and Specifications.

**Medium description (100 words):**
URPX (Utility Rate Plan Exchange) is an open standard that enables transparent, machine-readable utility rate plan data exchange. While standards exist for customer usage data and grid operations, no comprehensive standard previously existed for the rate plan data that determines how customers are charged. Built on W3C semantic web technologies (RDF, OWL, SHACL), URPX provides a rich ontology and Common Service API for representing everything from simple flat-rate plans to complex time-of-use structures with dynamic pricing. Initiated by Flux Tailor with NLR collaboration, URPX is hosted by LF Energy Standards and Specifications (LFESS).

### Review Process

This document is maintained by the URPX working group at https://github.com/urpx-org/urpx-wg. Updates should be submitted as pull requests to ensure change tracking and working group review. The working group chair reviews and approves changes before they are merged.

## Additional Notes

URPX is positioned as an interoperability standard that complements — rather than competes with — existing vendor solutions and data sources. The standard aims to provide a common data layer that enables the broader ecosystem, including DER optimization platforms, customer engagement platforms, energy service providers, and billing system vendors.

While NLR's URDB is a valuable resource for utility rate plan data, the relationship between URDB and URPX is one of complementary scope rather than direct data transposition. URDB contains summary-level pricing data; URPX defines structured, semantically rich rate plan representations with executable cost modeling logic, eligibility criteria, and applicability conditions. The formal MOU between NLR and Flux Tailor governs collaboration on the open standard, and mapping pathways between the two formats are under development.

Standardized, machine-readable access to rate plan data is an emerging regulatory topic. Regulators are increasingly referencing standards like Green Button (NAESB REQ.21 ESPI) for customer data access; URPX positions itself as the analogous standard for rate plan data, which regulators could reference for rate plan publication requirements. For DER developers and aggregators, structured rate plan data with time-of-use schedules and export pricing enables optimization algorithms that respond to price signals, supporting grid flexibility and customer cost savings.
