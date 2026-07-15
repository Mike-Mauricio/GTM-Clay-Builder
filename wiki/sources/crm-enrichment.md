---
title: "CRM Enrichment"
type: source
created: 2026-07-14
updated: 2026-07-14
sources: []
tags: [source, clay-academy, crm, hubspot, salesforce, data-hygiene]
---

# CRM Enrichment — Source Summary

**Source:** Clay University course (7 lessons)
**URL:** university.clay.com
**Topic:** Building CRM enrichment and data hygiene workflows at scale using Clay

## Course Overview

Covers the complete CRM enrichment lifecycle — from importing CRM data into Clay through enriching, taking action, and keeping data fresh automatically. Includes platform-specific guides for both HubSpot and Salesforce integrations.

## Lesson Index

| # | Lesson | Key Topics |
|---|--------|------------|
| 1 | Intro to CRM Enrichment | Why CRM enrichment matters, Clay vs native CRM enrichment, cost of poor data |
| 2 | Importing from your CRM | HubSpot + Salesforce connections, object types, field architecture best practices |
| 3 | Enriching your CRM Data | Inbound lead enrichment, existing contact updates, company scoring, strategic data selection |
| 4 | Taking Action on Enriched Data | Slack notifications, signal-based sequence enrollment, human-in-the-loop |
| 5 | Keeping CRM Data Fresh | Dynamic refresh lists, scheduled imports, segmented refresh cycles |
| 6 | Clay x HubSpot Actions | Lookup/Create/Update, conditional logic, safe experimentation |
| 7 | Clay x Salesforce Actions | Sandbox testing, SOQL queries, Upsert, Lead Conversion |

## Key Contributions to Wiki

### New Pages Created
- [[clay-hubspot-integration]] — HubSpot-specific import, Lookup, Create, Update
- [[clay-salesforce-integration]] — Salesforce-specific sandbox, SOQL, Upsert, Lead Conversion
- [[crm-enrichment-lifecycle]] — Full import → enrich → action → refresh cycle

### Existing Pages Updated
- [[crm-export-dedup]] — referenced from broader lifecycle pattern
- [[conditional-runs]] — CRM-specific conditional patterns added

## Key Concepts Introduced

- **CRM field architecture** — design CRM fields before enriching (simplicity, naming, grouping, type compatibility)
- **Dynamic refresh lists** — CRM lists that auto-identify stale contacts for re-enrichment
- **Salesforce Upsert** — combined Create/Update using external ID (eliminates separate conditional logic)
- **SOQL queries** — Salesforce Object Query Language for complex data retrieval
- **Lead Conversion** — automated Lead → Contact + Account + Opportunity in Salesforce
- **Force multiplier mindset** — automation handles routine decisions, humans focus on high-value activities

## Relationship to Other Sources

- Builds on [[clay-101-gtm-automation]] (FETE framework, enrichment basics, CRM export patterns)
- Deepens the [[crm-export-dedup]] pattern from Clay 101 into a full lifecycle
- References [[waterfall-enrichment]] and [[conditional-runs]] extensively
- Introduces CRM-specific signal-based actions that connect to [[clay-signals]]
