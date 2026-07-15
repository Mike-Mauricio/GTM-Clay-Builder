---
title: Jigsaw Framework
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]"]
tags: [framework, clay-fundamentals, data-strategy, enrichment-strategy]
---

# Jigsaw Framework

**Corner Pieces → Edges → Fill**

A data strategy framework for deciding what to enrich and in what order. Introduced in [[clay-101-gtm-automation|Clay 101]] alongside [[fete-framework|FETE]]. While FETE describes the workflow phases, Jigsaw describes the data layering within the Enrich phase.

## The Three Layers

### Corner Pieces (Identifiers)
The minimum data needed to unlock everything else. Without these, other enrichments fail.

**For companies:**
- Company domain (required)
- Company LinkedIn URL (strongly recommended)

**For people:**
- LinkedIn URL (required)
- Full name (strongly recommended)

Corner pieces are collected during the Find phase of [[fete-framework|FETE]]. They're the keys that unlock [[waterfall-enrichment|waterfall enrichments]] — most enrichment providers need a domain or LinkedIn URL as input.

### Edges (Context)
Firmographic and demographic data that provides business context:

**Company edges:** Industry, headcount, funding stage, revenue, HQ location, tech stack, founding date
**People edges:** Job title, seniority, department, work email, phone number, location

Edges come from [[waterfall-enrichment|waterfall enrichments]] and standard providers. They enable scoring, segmentation, and routing.

### Fill (Specialized Data)
Custom, niche, or derived data specific to your GTM motion. This is where [[gtm-alpha]] lives — the unique data combinations your competitors don't have.

**Examples:** Free trial availability, specific technology mentions, recent content topics, hiring velocity, integration compatibility, customer testimonials

Fill data typically comes from [[claygent]] (AI web scraping), [[ai-formulas|AI Formulas]] (derived calculations), or custom HTTP API calls.

## Design Principle

**Always work from the outside in.** Corner pieces first, then edges, then fill. Each layer unlocks and informs the next:
1. Corner pieces tell enrichment providers *who* to look up
2. Edges tell you *whether* a record is worth deeper enrichment (gating)
3. Fill tells you *how* to engage — personalization, routing, messaging

This is also a [[credit-optimization]] strategy: corner pieces are cheap/free, edges are moderate, fill is expensive. Gating expensive fill behind edge-based qualification saves significant credits.

## See Also

- [[fete-framework]] — the complementary workflow pattern
- [[waterfall-enrichment]] — how edges are collected
- [[claygent]] — primary tool for fill data
- [[credit-optimization]] — cost implications of the layering strategy
