---
title: Audiences Course
type: source
created: 2026-07-14
updated: 2026-07-14
sources: []
tags:
  - source
  - clay-academy
  - audiences
  - unified-data-layer
  - revops
  - scale
---

# Audiences Course

## Source Information

| Field | Value |
|---|---|
| **Source** | Clay University |
| **Format** | Video course, 9 lessons |
| **URL** | university.clay.com |
| **Topic** | Clay Audiences — building a unified data layer for enterprise-scale GTM operations |
| **Ingested** | 2026-07-14 |

## Lesson Index

| # | Lesson | Topic |
|---|---|---|
| 1 | What Are Audiences? | Introduction to the unified data layer concept, three problems it solves, four core capabilities |
| 2 | Audiences vs Tables | When to use each, the lab vs production mental model, scale differences |
| 3 | Setting Up Data Sources | Salesforce 4-object import, Snowflake/HubSpot/Gong/BigQuery connections, import sync vs record matching |
| 4 | Overwrite Rules & Field Mapping | Always/Never/Fill Blank per-field rules, export sync setup, preventing CRM data loss |
| 5 | Data Hub | Field-level fill rates across entire audience, gap identification, centralized signal management |
| 6 | CRM Enrichment at Scale | Import → gap analysis → bulk enrich → map back → continuous enrichment → export sync |
| 7 | TAM Sourcing with Audiences | Sculptor for net-new search, draft mode safety check, auto-dedup, dynamic territory routing |
| 8 | Signal-Based Plays | Signals follow the person not the list, auto-created filtered audiences, signal → enrich → act |
| 9 | AI Outbound with Audiences | Trigger → auto-enrich → sequencer handoff → AI personalization, human-in-the-loop review step |

## Summary

This course covers Clay Audiences — the production-grade data layer that sits above Tables in Clay's architecture. Where Tables handle one-off, experimental workflows capped at 50,000 rows, Audiences manage millions of records with continuous enrichment, live filtering, and automated CRM sync.

The course introduces the **SEA Framework** (Segment, Enrich, Act) as the operational model for every Audiences play, paralleling the [[fetc-framework|FETE framework]] used in Tables. It walks through four core use cases — CRM enrichment, TAM sourcing, signal-based plays, and AI outbound — showing how each pattern from earlier Clay courses scales to production in the Audiences layer.

A recurring theme is that Audiences solve the maintenance problem: instead of periodic reimports and manual enrichment jobs, Audiences auto-enrich, self-update, and continuously sync. The Data Hub provides visibility into field-level fill rates across the entire database, turning data quality from a guessing game into a measurable metric.

## Key Concepts Introduced

- **Unified data layer** — Audiences as one always-current home for all sales data
- **SEA framework** — Segment, Enrich, Act as the three-step operational model
- **Audiences vs Tables** — production vs lab, always-on vs one-off, millions vs 50K
- **Data Hub fill rates** — field-level data quality visibility across the entire audience
- **Overwrite rules** — Always Overwrite, Never Overwrite, Fill Blank Fields Only (per-field CRM protection)
- **Record matching / entity resolution** — merging the same person from multiple sources via unique key
- **Export sync** — continuous 24-hour sync cycles from Clay back to CRM
- **Continuous enrichment** — auto-enrichment on arrival and scheduled re-enrichment runs
- **Net-new search with Sculptor + auto-dedup** — natural language queries with automatic deduplication against existing records
- **Signal follows the person** — signals track individuals, not list membership
- **Field mapping optional for action-only runs** — skip mapping when you just need to trigger a sequence
- **Draft mode** — safety check before committing net-new records at scale

## Knowledge Base Impact

### New Pages Created
- [[clay-audiences]] — comprehensive tool page covering all 9 lessons

### Existing Pages Updated
- [[credit-optimization]] — added audience-level credit dedup and spend limits
- [[experiment-before-scale]] — strengthened with Audiences as the "graduation" destination for Table experiments

## Relationship to Other Sources

This course is the capstone of the Clay Academy sequence. It takes patterns introduced in earlier courses and shows how they operate at production scale:

- [[clay-101-gtm-automation]] — foundational Clay concepts (Tables, enrichments, formulas) that Audiences builds on top of
- [[crm-enrichment]] — CRM enrichment patterns now running continuously via Audiences instead of one-off Table workflows
- [[tam-sourcing-course]] — TAM sourcing with Sculptor and ICP filters, now with auto-dedup and dynamic routing at audience scale
- [[signals-and-abm]] — signal-based plays now with "signal follows the person" and auto-created signal audiences
- [[automated-outbound]] — outbound patterns now triggered by audience signals with sequencer handoff and human-in-the-loop review
- [[limitless-research]] — research enrichment techniques used within audience enrichment workflows

The course positions Audiences as where all prior Clay knowledge converges: you experiment with Tables using patterns from earlier courses, then graduate proven workflows to Audiences for continuous, scaled execution.
