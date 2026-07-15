---
title: Operations Log
---

# Clay GTM Engineer — Log

Chronological record of all operations. Append-only.

---

## [2026-07-13] create | Knowledge Graph Initialized
Initialized the Clay GTM Engineer Knowledge Graph. Created directory structure, schema (CLAUDE.md), index, and log. Wiki is empty — ready for first source ingest.
- Structure: raw/ (6 subcategories), wiki/ (6 subcategories), Knowledge/ (Clay + GTM-Engineering), Playbooks/ (5 slots), Examples/ (3 categories)
- Schema defines 4 operations: ingest, query, lint, synthesize
- Also functions as an AI context pack with session modes: brainstorm, design, build, learn

## [2026-07-13] ingest | Clay 101: GTM Automation (17 lessons)
Ingested the complete Clay 101 GTM Automation course from Clay University (university.clay.com). First major source ingest — establishes the foundational knowledge layer.
- **Source:** 17 lesson files (Markdown, clipped from Clay University)
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Clay-101/` (01 through 17, renamed to clean slugs) AND synthesized into wiki pages
- **Wiki pages created:** 18 total — 6 concepts, 7 tools, 4 patterns, 1 source summary
- **Concepts:** fete-framework, jigsaw-framework, gtm-alpha, waterfall-enrichment, credit-optimization, conditional-runs
- **Tools:** claygent, ai-formulas, clay-normalization-tools, clay-find-companies, clay-find-people, clay-email-waterfall, clay-google-maps
- **Patterns:** experiment-before-scale, crm-export-dedup, company-enrichment-pipeline, people-enrichment-pipeline
- **Source:** clay-101-gtm-automation
- **Cross-references:** All pages wikilinked to related concepts, tools, and patterns. Source page includes full lesson index table.
- **Raw cleanup:** Removed original files from `raw/Clay 101 - GTM Automation/`

## [2026-07-13] ingest | Limitless Research (7 lessons)
Ingested the Limitless Research course from Clay University. Intermediate course focused on Clay's web scraping and research toolkit. Builds on Clay 101 foundations.
- **Source:** 7 lesson files (Markdown, clipped from Clay University). 2 are repeats from Clay 101 (Claygent overview, Prompt Engineering).
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Limitless-Research/` (01 through 07) AND synthesized into wiki pages
- **Wiki pages created:** 7 new — 1 concept, 4 tools, 1 pattern, 1 source summary
- **Wiki pages updated:** 1 — claygent (added model selection, preset templates, hierarchy positioning)
- **New concept:** scraping-hierarchy (5-tool decision framework)
- **New tools:** clay-native-scraper, zenrows, apify, clay-chrome-extension
- **New pattern:** prompt-engineering-at-scale
- **Source:** limitless-research
- **Cross-references:** All new pages linked to scraping-hierarchy and existing concepts. Claygent page updated with Limitless Research additions.
- **Running totals:** 26 wiki pages, 2 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Limitless Research/`

## [2026-07-13] ingest | AI-Powered GTM Automation (19 lessons)
Ingested the AI-Powered GTM Automation course from Clay University. Advanced course introducing FETC framework, Claygent Builder, new enrichment integrations, and AI-powered content creation. Largest ingest to date.
- **Source:** 19 lesson files (Markdown, clipped from Clay University). Some lessons recap prior content; net-new content flagged in source page.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/AI-Powered-GTM/` (01 through 19) AND synthesized into wiki pages
- **Wiki pages created:** 14 new — 3 concepts, 8 tools, 2 patterns, 1 source summary
- **Wiki pages updated:** 3 — fete-framework (FETC evolution reference), credit-optimization (BYOK stats, Helium/Argon, Metaprompter, Builder testing), claygent (Helium/Argon models, Builder reference)
- **New concepts:** fetc-framework, ai-snippets, deterministic-vs-generative
- **New tools:** claygent-builder, perplexity-enrichment, oakie-ai, twain, analyze-image, clay-company-lookalikes, clay-ai-icp-search, metaprompter
- **New patterns:** personalized-outbound-pipeline, lookalike-automation
- **Source:** ai-powered-gtm-automation
- **Cross-references:** All new pages wikilinked to existing concepts and tools. FETE page now references FETC evolution. Credit optimization page expanded with advanced strategies.
- **Running totals:** 39 wiki pages, 3 source courses ingested
- **Raw cleanup:** Removed original files from `raw/AI Powered GTM Automation/`

## [2026-07-14] ingest | Automated Outbound (15 lessons)
Ingested the Automated Outbound course from Clay University. Outbound activation course focused on delivery tools — sequencing, omnichannel, and AI video. Heavy recap of prior courses (7 of 15 lessons), but 4 genuinely new tool integrations.
- **Source:** 15 lesson files (Markdown, clipped from Clay University). 7 full recaps, 4 partial, 4 genuinely new.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Automated-Outbound/` (01 through 15) AND synthesized into wiki pages
- **Wiki pages created:** 5 new — 4 tools, 1 source summary
- **Wiki pages updated:** 2 — personalized-outbound-pipeline (added sequencer options, video tools, multi-step variable convention), ai-snippets (added chain-of-context construction sequence, subject line rules)
- **New tools:** clay-sequencer (major — native end-to-end sequencing with Clean Variables, Spintax, reply management, Slack approvals, Global Inbox), la-growth-machine (omnichannel), sendspark (AI video), tavus (AI video replicas)
- **Source:** automated-outbound
- **Cross-references:** All new tool pages linked to personalized-outbound-pipeline and existing activation concepts. Outbound pipeline pattern now covers full delivery landscape.
- **Running totals:** 44 wiki pages, 4 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Automated Outbound/`

## [2026-07-14] ingest | CRM Enrichment (7 lessons)
Ingested the CRM Enrichment course from Clay University. Covers the complete CRM enrichment lifecycle — importing, enriching, taking action, and keeping data fresh — plus platform-specific guides for HubSpot and Salesforce.
- **Source:** 7 lesson files (Markdown, clipped from Clay University). All net-new content — no overlap with prior courses.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/CRM-Enrichment/` (01 through 07) AND synthesized into wiki pages
- **Wiki pages created:** 4 new — 2 tools, 1 pattern, 1 source summary
- **Wiki pages updated:** 2 — crm-export-dedup (added lifecycle context, CRM integration references), conditional-runs (added CRM update conditional patterns for preventing overwrites)
- **New tools:** clay-hubspot-integration (import, Lookup, Create, Update, conditional logic), clay-salesforce-integration (sandbox testing, SOQL, Upsert, Lead Conversion)
- **New pattern:** crm-enrichment-lifecycle (full import → enrich → action → refresh cycle with field architecture and data freshness automation)
- **Source:** crm-enrichment
- **Cross-references:** All new pages linked to existing enrichment concepts and CRM patterns. Lifecycle pattern connects to fete-framework, waterfall-enrichment, conditional-runs.
- **Running totals:** 48 wiki pages, 5 source courses ingested
- **Raw cleanup:** Removed original files from `raw/CRM Enrichment/`

## [2026-07-14] ingest | Signals & ABM (7 lessons)
Ingested the Signals & ABM course from Clay University. Introduces real-time signal detection, custom signal building, signal orchestration (stacking, velocity, scoring), and account-based marketing with a 3-stage funnel and 3-table architecture.
- **Source:** 7 lesson files (Markdown, clipped from Clay University). All net-new content — signals and ABM are entirely new topic areas.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Signals-ABM/` (01 through 07) AND synthesized into wiki pages
- **Wiki pages created:** 7 new — 2 concepts, 2 tools, 2 patterns, 1 source summary
- **Wiki pages updated:** 1 — gtm-alpha (added custom signals as source of GTM alpha, real-world examples, signal orchestration reference)
- **New concepts:** clay-signals (4 signal categories, default vs custom, timing problem, prioritization matrix), signal-orchestration (signal stacking, sequential/parallel/hybrid processing, weight assignment, velocity, scoring systems)
- **New tools:** adyntel (competitive ad intelligence), versium (email hashes for ad platform matching)
- **New patterns:** signal-based-prospecting (signal → enrich → qualify → route → act pipeline), abm-architecture (3-stage ABM funnel + 3-table Clay architecture + ad intelligence layer)
- **Source:** signals-and-abm
- **Cross-references:** All new pages linked to existing concepts. Signal pages cross-reference gtm-alpha, conditional-runs, personalized-outbound-pipeline. ABM pattern connects to clay-signals, versium, adyntel.
- **Running totals:** 55 wiki pages, 6 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Signals & ABM/`

## [2026-07-14] ingest | Automated Inbound (10 lessons)
Ingested the Automated Inbound course from Clay University. Covers the full inbound automation lifecycle — lead capture via webhooks, enrichment strategy (short forms + Clay enriches), scoring, routing, personalized messaging, and export. Introduces speed-to-lead as the critical inbound metric.
- **Source:** 10 lesson files (Markdown, clipped from Clay University). Lesson 6 (Deep Dive: Web Intent) is video-only with no text content. Lesson 4 (Transform) and Lesson 9 (Export) are acknowledged recaps of prior courses.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Automated-Inbound/` (01 through 10) AND synthesized into wiki pages
- **Wiki pages created:** 6 new — 3 concepts, 1 tool, 1 pattern, 1 source summary
- **Wiki pages updated:** 0 (references existing pages extensively: fete-framework, jigsaw-framework, ai-formulas, normalization-tools, crm-export-dedup, ai-snippets)
- **New concepts:** speed-to-lead (5-min stat, Clay-first routing, speed + intelligence = GTM alpha), lead-scoring (Score Row + AI formula, seniority/tech/industry dimensions, Anthropic 3x example), lead-routing (weighted round robin, rep table, Salesforce sync)
- **New tool:** clay-webhooks (real-time lead capture from any source, 50K limit, Typeform native integration)
- **New pattern:** inbound-automation-pipeline (full 7-stage inbound cycle: sources → enrich → transform → score → route → personalize → export, short form philosophy, enrichment decision tree)
- **Source:** automated-inbound
- **Cross-references:** All new pages linked to FETE/Jigsaw foundations, enrichment concepts, CRM export patterns. Inbound pipeline connects to signal-based-prospecting and crm-enrichment-lifecycle.
- **Running totals:** 61 wiki pages, 7 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Automated Inbound/`

## [2026-07-14] ingest | TAM Sourcing (7 lessons)
Ingested the TAM Sourcing course from Clay University. Covers systematic TAM mapping, ICP definition (pain-first approach, 3 dimensions), TAM sourcing workflows with systems thinking, advanced techniques (tiered scoring, AI classification), third-party scrapers (Apify deep-dive), SMB sourcing (OpenMart), and TAM activation with ROI measurement.
- **Source:** 7 lesson files (Markdown, clipped from Clay University). All net-new content — TAM sourcing and ICP definition are entirely new topic areas.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/TAM-Sourcing/` (01 through 07) AND synthesized into wiki pages
- **Wiki pages created:** 6 new — 2 concepts, 1 tool, 2 patterns, 1 source summary
- **Wiki pages updated:** 2 — apify (expanded with 2,000+ actor library, setup process, TAM sourcing workflows, GTM alpha Instagram/Similarweb example), clay-google-maps (added OpenMart comparison table, TAM/SMB sourcing context)
- **New concepts:** tam-sourcing (TAM vs ICP, CPJ dataset, systems vs workflow thinking, quality control), icp-definition (pain-first approach, Problem Severity × Frequency matrix, 3 ICP dimensions, 6Sense multi-variant example, validation checkpoints, reverse engineering from closed-won)
- **New tool:** openmart (SMB/local business discovery with unlimited results, semantic search, multi-source data, USA/CA/AU/NZ coverage)
- **New patterns:** tam-sourcing-pipeline (full TAM system with tiered account routing, multi-factor scoring, ROI measurement, Lightspeed 30x case study), smb-tam-sourcing (SMB-specific workflow with OpenMart/Google Maps, review sentiment analysis, digital maturity assessment)
- **Source:** tam-sourcing-course
- **Cross-references:** All new pages linked to existing Find tools, scraping hierarchy, signals, and enrichment concepts. Apify page significantly expanded with TAM sourcing examples. Google Maps now cross-references OpenMart.
- **Running totals:** 67 wiki pages, 8 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Automated Inbound/` and `raw/TAM Sourcing/`

## [2026-07-14] ingest | Audiences (9 lessons)
Ingested the Audiences course from Clay University. Introduces Clay's unified data layer — Audiences — which breaks the 50K-row table limit to handle millions of records with always-on enrichment, CRM sync, and signal-driven actions. The SEA framework (Segment, Enrich, Act) is the Audiences counterpart to FETE in Tables.
- **Source:** 9 lesson files (Markdown, clipped from Clay University). Major new feature — entirely new topic area. Four use case lessons apply Audiences to previously covered patterns (CRM enrichment, TAM sourcing, signals, outbound).
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Audiences/` (01 through 09) AND synthesized into wiki pages
- **Wiki pages created:** 2 new — 1 tool, 1 source summary
- **Wiki pages updated:** 2 — credit-optimization (Audiences-scale credit management: Data Hub, enrichment reuse, spend limits), experiment-before-scale (Tables as labs / Audiences as production)
- **New tool:** clay-audiences (unified data layer, SEA framework, Data Hub, overwrite rules, record matching, export sync, continuous enrichment, 4 use cases at scale)
- **Source:** audiences-course
- **Key concepts:** SEA framework, Audiences vs Tables (production vs lab), Data Hub fill rates, overwrite rules (Always/Never/Fill Blank), record matching, export sync, continuous enrichment, net-new search with auto-dedup, signal follows the person, field mapping optional
- **Cross-references:** Links to crm-enrichment-lifecycle, tam-sourcing-pipeline, signal-based-prospecting, personalized-outbound-pipeline, credit-optimization, experiment-before-scale, clay-functions.
- **Running totals:** 69 wiki pages, 9 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Audiences/`

## [2026-07-14] ingest | Functions (8 lessons)
Ingested the Functions course from Clay University. Introduces Clay Functions — reusable, shared workflows that run in the background and return results to the calling table. Define once, call from any table, edits auto-propagate everywhere. Includes governance patterns and MCP external calling.
- **Source:** 8 lesson files (Markdown, clipped from Clay University). Major new feature — entirely new topic area. Three use case lessons cover enrichment functions, copywriting functions, and signal detection functions.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Functions/` (01 through 08) AND synthesized into wiki pages
- **Wiki pages created:** 2 new — 1 tool, 1 source summary
- **Wiki pages updated:** 2 — credit-optimization (Function governance: conditional checkbox, GDPR gating, credit visibility), experiment-before-scale (test in table then save as function)
- **New tool:** clay-functions (reusable callable workflows, functions vs templates, 4 usage signals, 3 use case categories, governance patterns, scaling/library management, MCP external calling)
- **Source:** functions-course
- **Key concepts:** Functions vs templates (call vs copy), auto-propagating updates, conditional checkbox for cost control, GDPR compliance gating, function library management, naming convention ("Workflow type + outputs + version"), internal catalog, mini-table background execution, functions callable via MCP from Claude/OpenAI/Glean
- **Real-world examples:** Firmographic enrichment (12 providers, 3 waterfalls), company hierarchy mapping (AI agent synthesis), email copywriting with first-party data (3 message variants), job change detection (11 email + 12 LinkedIn backup providers)
- **Cross-references:** Links to clay-audiences, claygent-builder, credit-optimization, waterfall-enrichment, experiment-before-scale, ai-snippets.
- **Running totals:** 71 wiki pages, 10 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Functions/`

## [2026-07-14] ingest | Clay MCP for Reps (6 lessons)
Ingested the Clay MCP for Reps course from Clay University. Introduces Clay's MCP integration — using Clay directly inside AI chat tools (Claude, ChatGPT, Copilot, Codex, Glean) for conversational prospecting. Full motion in one conversation: research → list → enrich → draft → send.
- **Source:** 6 lesson files (Markdown, clipped from Clay University). All net-new content — MCP is an entirely new feature.
- **Disposition:** Moved verbatim to `Knowledge/Clay/Lessons/Clay-MCP/` (01 through 06) AND synthesized into wiki pages
- **Wiki pages created:** 2 new — 1 tool, 1 source summary
- **Wiki pages updated:** 1 — clay-functions (added Managed vs Custom Functions distinction with comparison table, expanded MCP section with platform list)
- **New tool:** clay-mcp (conversational prospecting via MCP — setup per platform, search → filter → enrich credit pattern, Managed/Custom Functions, Business Context, first-party data via Audiences, Claude email widget, individual briefs)
- **Source:** clay-mcp-course
- **Key concepts:** Conversational prospecting, Search → Filter → Enrich credit pattern, Managed Functions (Clay-built, auto-invoked) vs Custom Functions (ops-built, by name), Business Context setting, "use Clay" prompt tip, generative email widget (Claude), first-party data blending (CRM + Gong + Audiences in one conversation)
- **Cross-references:** Links to clay-functions, clay-audiences, personalized-outbound-pipeline, speed-to-lead, credit-optimization. Functions page now covers both table-based and MCP-based calling.
- **Running totals:** 74 wiki pages, 11 source courses ingested
- **Raw cleanup:** Removed original files from `raw/Clay MCP/`
