---
title: FETE Framework
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[ai-powered-gtm-automation]]"]
tags: [framework, clay-fundamentals, workflow-design]
---

# FETE Framework

**Find → Enrich → Transform → Export**

The foundational workflow pattern for every Clay build. Introduced in [[clay-101-gtm-automation|Clay 101]] as the answer to the "blank canvas problem" — new users open Clay and don't know where to start. FETE provides the universal sequence.

## The Four Phases

### Find
Source your target records into Clay. Three primary methods:
- **Clay's native datasets** — [[clay-find-companies|Find Companies]] (100+ providers), [[clay-find-people|Find People]]
- **External sources** — [[clay-google-maps|Google Maps]], job postings, CSV import, CRM import
- **Connected sources** — LinkedIn, Salesforce, HubSpot imports

The goal is to get your initial list with [[jigsaw-framework|corner pieces]] (company domain + LinkedIn URL for companies; LinkedIn URL + full name for people).

### Enrich
Add context to raw records. This is where [[jigsaw-framework|Jigsaw]] "edges" and "fill" come in:
- **[[waterfall-enrichment|Waterfall enrichments]]** — Multi-provider chains for firmographics, technographics, emails
- **[[claygent]]** — AI web scraping for custom, niche data no database has
- **Standard enrichments** — Single-provider lookups for specific data points

Key principle: Enrich with intent, not availability. Every field must answer: Does it change routing? Improve scoring? Improve copy? If none — skip it.

### Transform
Clean, normalize, and reshape data for downstream use:
- **[[clay-normalization-tools|Normalization tools]]** — Credit-free deterministic cleaning (company names, phone numbers, locations, whitespace)
- **[[ai-formulas|AI Formulas]]** — Credit-free structured transformations (extract, calculate, format, classify)

Transform is often underused. Clean data dramatically improves CRM hygiene and outbound copy quality.

### Export
Get data out of Clay into activation systems:
- **CSV download** — Universal, one-time transfer
- **Google Sheets** — Live sync with Add Row / Lookup+Update actions
- **CRM integrations** — HubSpot, Salesforce, etc. with [[crm-export-dedup|dedup-first patterns]]
- **Email sequencing tools** — Direct push to outbound tools

## Design Principle

FETE is sequential but iterative. You'll often loop back — enrich results inform new Find criteria, Transform reveals data quality issues that need re-enrichment. The framework gives direction, not a rigid checklist.

## Relationship to Jigsaw

FETE describes **what you do** at each step. [[jigsaw-framework|Jigsaw]] describes **what data you collect** at each step. They work together:
- Find = get corner pieces
- Enrich = build edges, then fill
- Transform = clean everything
- Export = activate the assembled puzzle

## Evolution: FETC

[[ai-powered-gtm-automation|AI-Powered GTM Automation]] introduces [[fetc-framework|FETC]] — replacing "Export" with "Create" for AI-powered workflows where the goal is content generation (personalized messages, sequences, battle cards) rather than just data movement. FETE remains the foundational pattern; FETC is the advanced evolution. Use FETE when the goal is data movement, FETC when the goal is deliverable creation.

## See Also

- [[fetc-framework]] — the advanced evolution (Export → Create)
- [[jigsaw-framework]] — the complementary data strategy
- [[experiment-before-scale]] — how to test each FETE phase
- [[clay-101-gtm-automation]] — source course
