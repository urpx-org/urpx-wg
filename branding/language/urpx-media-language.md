# Utility Rate Plan Exchange (URPX)

**Last Updated:** 2026-03-13

## Table of Contents

- [Basic Info](#basic-info)
- [Description](#description)
- [Overview](#overview)
- [Technical Profile](#technical-profile)
- [Grid Context](#grid-context)
- [Related Projects](#related-projects)
- [Maturity & Adoption](#maturity--adoption)
- [Learn More](#learn-more)
- [Additional Notes](#additional-notes)

## Basic Info

- LF Energy webpage: https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/
- Website:
- Code: https://github.com/urpx-org
- Documentation:
- Calendar: https://zoom-lfx.platform.linuxfoundation.org/meetings/utility-rate-plan-exchange?view=month
- LinkedIn:
- Community:
	- Mailing List: https://lists.lfenergy.org/g/urpx-wg
	- Slack: https://lfenergy.slack.com/archives/C09NTF8PZTJ
- LFX Insights:
- Other:

## Description

A standardized, machine-accessible format for representing and exchanging utility rate plan data.

## Overview

URPX (Utility Rate Plan Exchange) is an open semantic standard that provides a comprehensive, standardized method for representing rate plan data from distribution, retail, and other utility service providers — including energy, water, and other utilities — in machine-accessible format. The standard defines a modular ontology — covering rate plan structures, charge classifications, eligibility rules, applicability conditions, geographic territories, and temporal versioning — that enables governments, utilities, vendors, and technology companies to exchange rate plan information in a consistent, interoperable way.

While standards exist for customer usage data (Green Button NAESB REQ.21 ESPI) and grid operations (CIM), no comprehensive standard exists for the rate plan data that determines how customers are charged. Today, vendors handling rate plan calculations work in silos using custom logic and proprietary data structures. There is no standard format for representing the logic and customer profile attributes used to compute cost and determine customer eligibility for rate plans. This fragmentation creates barriers to innovation, competition, and transparency in energy markets: customers cannot easily compare rate plans, vendors must build custom integrations for each utility territory, and those tasked with cost data ingest and bill estimation struggle with data quality across territories. URPX addresses this by defining a single semantic model that any party can implement, reducing the integration problem from N proprietary formats to one shared standard.

The project builds on an existing collaboration between the Nation Laboratory of the Rockies (NLR) — which maintains the Utility Rate Database (URDB) — and Flux Tailor. URPX enhances the data representation of the current URDB dataset and provides a standard interoperable format, while URDB provides rate plan data that can be expressed in URPX format. The standard is built on semantic web technologies (RDF, OWL, SHACL) with data instances in JSON-LD, made available through GraphQL or REST APIs. From simple flat-rate plans to complex ratchet and time-of-use structures and highly dynamic pricing, URPX provides the shared language required to compute costs accurately and consistently.

## Technical Profile

### What It Does

Defines a standardized ontology and exchange format for utility rate plan data, including rate structures, charge types, eligibility rules, applicability conditions, and temporal versioning, enabling machine-readable representation and exchange of rate plan information across utility territories.

### Problem(s) Solved

Eliminates the need for vendors and technology companies to reverse-engineer each utility's proprietary rate plan data structures. Provides a common format that enables consistent rate plan representation across utilities, allowing customers to compare rate plans, vendors to scale across territories without custom integrations, and regulators to perform reliable analysis with lower data integration costs.

### Key Capabilities

- Comprehensive rate plan ontology in RDF/OWL covering core rate plan structure and billing model, charge classifications and calculation logic, geographic applicability and jurisdiction, and organizational and regulatory metadata — representing everything from simple flat-rate plans to complex ratchet and time-of-use structures and highly dynamic pricing
- Multiple document types: rate plans, rate plan modifiers (add-on pricing that layers onto a base rate plan), tariff book documents, tariff statement documents (PSC filings), supply prices documents (competitive market pricing), real-time prices documents, and DER export prices
- Rich eligibility rules that define who qualifies for a rate plan, evaluating customer profile attributes (customer class, entity type, tax status, income level) and usage point attributes (connection type, voltage level, service territory, DER capability)
- Applicability conditions that define when charges apply, evaluating usage conditions (thresholds, demand levels, power factor), time conditions (TOU periods, seasons, billing cycles, day types), and other conditions (service territory, voltage level)
- Rule evaluation logic with Boolean operators (AND, OR, NOT), comparison operators, and multiple condition types (customer-based, usage-based, time-based, geographic, measurement)
- Temporal versioning and regulatory tracking of rate plan definitions, including full version history and structured tracking of proposed, approved, and retired plans
- Standards alignment with formal mappings to Green Button (rate plan context for usage data), LF Energy CDS (account and billing data alignment), CIM (grid operations), and OpenADR (demand response); interoperability with M2M communication standards including SEP and Matter
- Data validation and conformance using SHACL constraints for schema validation, conformance testing, and data quality enforcement
- Data instances in JSON-LD, accessible through GraphQL or REST APIs
- Common Service API specification with reference implementation (planned)
- Test data repository for implementation validation (planned)

### Relevant Standards

None. URPX is itself an emerging standard — a new open semantic standard for rate plan data exchange. It does not implement an existing industry standard; it aims to become one.

## Grid Context

### Grid Segment

Behind the Meter

### Function

Interoperability & Data

### Industry Solution Categories

#### Solution Type

- Rate Plan Data Standard: Provides a standardized ontology and exchange format for utility rate plan data, enabling machine-readable representation and interoperable exchange across utilities and vendors.

#### Component of

- Customer Information System (CIS): Standardizes the rate plan data object that CIS platforms manage, enabling interoperable exchange of rate structures, eligibility rules, and charge conditions between CIS and downstream systems.

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

- Flux Tailor (primary sponsor and technical lead)
- Nation Laboratory of the Rockies (NLR) (formal MOU partnership for open standard development; maintains the Utility Rate Database)

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

## Additional Notes

URPX is positioned as an interoperability standard that complements — rather than competes with — existing vendor solutions and data sources. The standard aims to provide a common data layer that enables the broader ecosystem, including CIS vendors, customer engagement platforms, DER optimization tools, and energy service providers. NLR's existing URDB provides a substantial foundation of rate plan data that can be expressed in URPX format, giving the standard an existing data corpus to build against.

Standardized, machine-readable access to rate plan data is an emerging regulatory topic. Regulators are increasingly referencing standards like Green Button (Connect) for customer data access; URPX positions itself as the analogous standard for rate plan data, which regulators could reference for rate plan publication requirements.
