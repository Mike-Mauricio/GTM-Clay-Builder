---
title: FETC Framework
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [framework, clay-advanced, workflow-design, ai-powered]
---

# FETC Framework

**Find → Enrich → Transform → Create**

The evolution of [[fete-framework|FETE]] for AI-powered GTM workflows. Introduced in [[ai-powered-gtm-automation|AI-Powered GTM Automation]]. The key change: replacing "Export" with "Create" to reflect AI's ability to generate deliverables — not just move data between systems.

## What Changed from FETE

| Phase | FETE (Clay 101) | FETC (AI-Powered) |
|-------|-----------------|-------------------|
| Find | Database queries, manual filters | Signal-based discovery, [[clay-ai-icp-search|AI ICP generation]], [[clay-company-lookalikes|lookalikes]] |
| Enrich | Waterfall providers, basic Claygent | + [[perplexity-enrichment|Perplexity]], [[oakie-ai|Oakie AI]], [[analyze-image|image analysis]] |
| Transform | Normalization, basic AI Formulas | [[deterministic-vs-generative|Deterministic vs. generative]] distinction, custom classification |
| Export → Create | CSV, Google Sheets, CRM push | [[ai-snippets|AI Snippets]], [[twain|Twain sequences]], battle cards, personalized messaging |

## The Create Step

"Create" is the action layer — where enriched, transformed data becomes deliverables:

- **[[ai-snippets|AI Snippets]]** — Modular, sentence-level content (subject lines, intros, PS lines) assembled into complete messages
- **[[twain|Twain]]** — Full multi-step email sequences with structured components
- **Personalized messaging** — Dynamic tone and voice per persona type
- **Beyond copy** — Sales copilots, Google Slides, video/voice via ElevenLabs, geo-targeted campaigns, image generation

### The Distillation Philosophy

Create is about **distillation, not volume**. The goal is to boil enriched data down to what matters for each prospect — not to generate more content for the sake of it. Every AI-generated snippet should reflect a specific data point that earned its place through enrichment.

## FETE vs. FETC: When to Use Which

- **FETE** — When the goal is data movement (enrich a list, clean it, push to CRM). Export is the right frame.
- **FETC** — When the goal is content generation (personalized outbound, sequence creation, deliverable production). Create is the right frame.

Both frameworks share the same first three steps. The difference is only in what happens at the end.

## See Also

- [[fete-framework]] — the foundational version (Clay 101)
- [[ai-snippets]] — modular content creation approach
- [[twain]] — multi-step sequence generation
- [[claygent-builder]] — centralized agent management for Create workflows
- [[personalized-outbound-pipeline]] — end-to-end Create implementation
