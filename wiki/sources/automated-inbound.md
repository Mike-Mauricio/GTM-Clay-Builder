---
title: "Automated Inbound — Clay University"
type: source
created: 2026-07-14
updated: 2026-07-14
sources: []
tags:
  - source
  - clay-academy
  - inbound
  - automation
  - speed-to-lead
---

# Automated Inbound — Clay University

**Source:** Clay University course (10 lessons)
**URL:** university.clay.com
**Topic:** Automated inbound lead processing — enrich, score, route, personalize, and export at machine speed

## Lesson Index

| # | Lesson | Content |
|---|--------|---------|
| 1 | Introduction to Inbound Automation | Course overview, speed-to-lead stats, Clay-first routing philosophy |
| 2 | Capturing Inbound Signals | Webhooks, native Typeform integration, real-time import setup |
| 3 | Short Form Philosophy | Why fewer fields = higher conversion, let Clay enrich the rest |
| 4 | Enrichment Strategy | Native enrichments, AI formulas, Claygent decision tree |
| 5 | Data Normalization | Free cleanup tools, company names, phones, whitespace, locations |
| 6 | Deep Dive: Web Intent | *(Video-only — no text content available)* |
| 7 | Lead Scoring | Score Row (15 criteria), AI formula scoring, hybrid approach |
| 8 | Lead Routing | Weighted round robin, rep tables, Salesforce sync |
| 9 | Personalization & Outreach | Inbound email formula, AI snippets, CRM lookup before outreach |
| 10 | Export & Ongoing Refresh | CRM push, sequencer enrollment, Slack alerts, Last Enrichment Date |

## Key Contributions

### New Pages Created
- [[speed-to-lead]] — the 5-minute metric and Clay-first routing philosophy
- [[lead-scoring]] — Score Row vs. AI formula scoring, hybrid approach, seniority/tech/industry dimensions
- [[lead-routing]] — weighted round robin mechanics, rep table as source of truth
- [[clay-webhooks]] — real-time signal capture, 50K submission limit, setup workflow
- [[inbound-automation-pipeline]] — full end-to-end pattern from form fill to CRM

### Existing Pages Referenced
- [[fete-framework]] — FETE applied to inbound (Find → Enrich → Transform → Export)
- [[jigsaw-framework]] — corner-pieces-first enrichment strategy for inbound leads
- [[ai-formulas]] — custom scoring, industry classification, title parsing
- [[clay-normalization-tools]] — free data cleanup in the Transform stage
- [[crm-export-dedup]] — deduplication and clean export to CRM
- [[ai-snippets]] — personalization snippet approach for outreach copy

## Key Concepts

- **Speed-to-lead metric** — after 5 minutes, qualifying odds drop 80%. Responding within 5 min = 100x more likely to connect vs. 1 hour.
- **Short form philosophy** — only ask name + email. Adding 2 fields (3→5) cuts completion nearly in half. Clay enriches everything else.
- **Clay-first routing** — send signals into Clay before CRM. Enrich instantly, then push finished leads to CRM. Eliminates sync delays.
- **Score Row native scoring** — up to 15 criteria, auto-generates score + reasoning. Start here, add AI formula fallback for edge cases.
- **Weighted round robin** — Clay's native routing action. Rep table with weights (2,2,1 → 40%/40%/20%). Default weight = 1 for even distribution.
- **Enrichment decision tree** — native enrichments first (fast, reliable) → AI formulas if data is in table → Claygent for last-mile niche data. Cheapest/fastest first.
- **Inbound email formula** — Line 1: personalized insight from enrichments. Line 2: connect insight to the problem you solve. Line 3: clear CTA.
- **Computational thinking for GTM** — treating GTM workflows as engineering problems with clear inputs, processing logic, and outputs.

## Real-World Examples

- **Anthropic's 3x enrichment coverage** — had Claude classify companies into Anthropic's custom industry categories instead of using standard SIC/NAICS codes. Result: 3x more companies correctly categorized, because custom categories mapped to their actual sales segments.

## Relationship to Other Sources

This course applies the foundational frameworks from [[clay-101-gtm-automation]] (FETE, Jigsaw) to a specific domain: inbound lead processing. Where Clay 101 teaches the building blocks, Automated Inbound shows how to assemble them into a complete pipeline.

Connects to several existing knowledge areas:
- **Normalization tools** referenced in both Clay 101 and CRM Enrichment courses — this course uses them in the Transform stage
- **CRM export and dedup** patterns from the CRM Enrichment lifecycle — this course applies them as the final export stage
- **AI formulas and Claygent** — this course adds the enrichment decision tree (native → AI formula → Claygent) as a framework for choosing the right tool

The [[inbound-automation-pipeline]] pattern synthesizes all of this into a single reusable architecture.
