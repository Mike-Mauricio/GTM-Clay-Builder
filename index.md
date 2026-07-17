---
title: Knowledge Graph Index
updated: 2026-07-14
total_pages: 90
---

# Clay GTM Engineer — Index

**Total pages:** 90 | **Last updated:** 2026-07-14

---

## Concepts

- [[ai-snippets]] — Modular content composition: generate subject/intro/body/PS independently, chain-of-context assembly
- [[clay-ai-architecture]] — Unified AI feature overview: 9 AI features, model catalog, pricing, data privacy (SOC 2, ISO 27001)
- [[clay-signals]] — Real-time buying intent detection: 4 categories (intent/growth/change/distress), default vs custom
- [[conditional-runs]] — Boolean gating to skip enrichments on unqualified rows
- [[conditional-statements]] — In-formula IF/THEN/ELSE logic for routing and classification (distinct from conditional runs)
- [[credit-optimization]] — Strategies for managing Clay credit spend (Actions vs Data Credits, BYOK, Audiences, Functions)
- [[deterministic-vs-generative]] — Two AI transformation modes: rule-based (free) vs. reasoning (costs credits)
- [[dynamic-column-references]] — Slash command (/) for referencing columns in formulas, prompts, and message drafts
- [[email-verification]] — Five verification statuses (Valid, Invalid, Catch-all, Unknown, Role-based) and deliverability impact
- [[fetc-framework]] — Find, Enrich, Transform, Create — FETE evolution for AI-powered deliverable workflows
- [[fete-framework]] — Find, Enrich, Transform, Export — the foundational Clay workflow pattern
- [[gtm-alpha]] — Competitive advantage through unique enrichment data combinations and custom signals
- [[icp-definition]] — Ideal Customer Profile: pain-first approach, 3 dimensions, Problem Severity × Frequency matrix
- [[jigsaw-framework]] — Corner pieces → edges → fill — the data layering strategy
- [[lead-routing]] — Standard and weighted round robin distribution, rep tables, territory-based routing
- [[lead-scoring]] — Score Row + AI formula scoring: seniority, tech stack, industry classification
- [[scheduled-operations]] — Scheduled sources, scheduled columns, and table versions for automated data freshness
- [[scraping-hierarchy]] — 5-tool decision framework: Claygent → Zenrows → Apify → Native Scraper → Chrome Extension
- [[signal-orchestration]] — Signal stacking: sequential/parallel/hybrid processing, weight assignment, velocity, scoring
- [[speed-to-lead]] — The critical inbound metric: 5-min response = 100x more connections, Clay-first routing
- [[tam-sourcing]] — Systematic market mapping with real-time data, TAM vs ICP, CPJ dataset, systems thinking
- [[waterfall-enrichment]] — Multi-provider enrichment chains, cheapest-first ordering

## Tools

- [[adyntel]] — Competitive ad intelligence: see competitors' active ads, creative, copy, and CTAs
- [[ai-formulas]] — Zero-credit AI transformations for in-table data (extract, calculate, classify)
- [[analyze-image]] — Multimodal enrichment: extract data from images/screenshots (logos, badges, visual signals)
- [[apify]] — Marketplace of 2,000+ platform-specific scrapers (Reddit, Instagram, Yelp, directories, TAM sourcing)
- [[clay-ads]] — Native ad audience sync to LinkedIn, Meta, Google Ads with compliance best practices
- [[clay-ai-icp-search]] — AI-powered ICP generation: input your domain, get a target company list
- [[clay-api-cli]] — Clay's developer platform: REST API, CLI, Agent Plugin, three programmatic approaches
- [[clay-audiences]] — Unified data layer: millions of records, SEA framework, Data Hub, CRM sync, always-on workflows
- [[clay-chrome-extension]] — Browser-based visual scraping with auto-detect and custom recipes
- [[clay-company-lookalikes]] — Find 10 similar companies from a target (replaces sunset Ocean.io)
- [[clay-email-waterfall]] — Multi-provider email finding with ZeroBounce validation and catch-all handling
- [[clay-find-companies]] — Native company discovery from 100+ providers with filters
- [[clay-find-people]] — Contact discovery at target companies with persona filters and linked tables
- [[clay-functions]] — Reusable workflows: define once, call from any table, Managed + Custom via MCP
- [[clay-google-maps]] — Local/SMB business discovery via Google Maps (up to 1,000 results, global coverage)
- [[clay-http-api]] — HTTP API enrichment action: two modes (enrichment/source), pagination, JWT auth
- [[clay-hubspot-integration]] — Native HubSpot integration: import, Lookup, Create, Update with conditional logic
- [[clay-mcp]] — Conversational prospecting: use Clay inside Claude, ChatGPT, Copilot via MCP
- [[clay-native-scraper]] — Built-in low-cost scraper for static pages (emails, phones, links, body text)
- [[clay-normalization-tools]] — Credit-free deterministic cleaners (company names, phones, locations, whitespace)
- [[clay-salesforce-integration]] — Native Salesforce integration: sandbox, SOQL, Upsert, Lead Conversion
- [[clay-sequencer]] — Native email sequencer: send, track, reply management, Spintax, Clean Variables
- [[clay-sources]] — Foundation of every Clay table: CSV import, 50K row limit, scheduled sources, saved searches
- [[clay-table-alerts]] — Enterprise monitoring: column error rates, row count limits, data inactivity alerts
- [[clay-table-management]] — Auto-dedupe, auto-run hierarchy, passthrough tables, table graph, production settings
- [[clay-webhooks]] — Real-time lead capture from any source via webhooks (Typeform, Zoom, Intercom, 50K limit)
- [[claygent]] — AI web scraper for last-mile data (Neon/Helium/Argon models, Builder, 1-3 credit tiers)
- [[claygent-builder]] — Centralized agent management: build with Sculptor, test free, deploy across tables
- [[find-ai]] — UseFind.ai natural language people/company search (1 credit per result)
- [[la-growth-machine]] — Omnichannel sequencing: email + Twitter + social in one campaign (LGM)
- [[metaprompter]] — "Help me" prompt improvement tool — better prompts before spending credits
- [[oakie-ai]] — SEC filing enrichment (10-K, 10-Q) for public company insights via stock ticker
- [[openmart]] — SMB/local business discovery: unlimited results, semantic search, multi-source (USA/CA/AU/NZ)
- [[perplexity-enrichment]] — Web research with source citations — trends, competitive intel, market context
- [[sendspark]] — AI personalized video generation with name/company/background overlays
- [[tavus]] — AI video replicas: deepfake-style personalized videos with your digital twin
- [[twain]] — Multi-step email sequence generation with structured components (subject, intro, body, CTA, PS)
- [[versium]] — Email hash provider for ad platform audience matching (Meta, Google Ads)
- [[zeliq]] — Phone and email finding/verification with strong EMEA coverage
- [[zenrows]] — Anti-bot bypass scraping for protected sites (Crunchbase, G2, etc.)

## Patterns

- [[abm-architecture]] — 3-stage ABM (aware/interested/evaluating) + 3-table Clay architecture
- [[company-enrichment-pipeline]] — Full Find→Enrich→Transform→Export pattern for company data
- [[crm-enrichment-lifecycle]] — Complete CRM cycle: import → enrich → action → refresh with data freshness automation
- [[crm-export-dedup]] — Two-step CRM export: lookup existing contacts, conditionally create net-new
- [[experiment-before-scale]] — Test 10 → 50 → full dataset; Tables as labs, Audiences as production
- [[inbound-automation-pipeline]] — Full inbound cycle: sources → enrich → score → route → personalize → export
- [[lookalike-automation]] — Closed-won CRM trigger → 10 lookalikes → vet → route to outreach
- [[people-enrichment-pipeline]] — Full pipeline for contacts: find people → email waterfall → enrich → export
- [[personalized-outbound-pipeline]] — Enrichment → AI Snippets → assembly → delivery via sequencer/video
- [[prompt-engineering-at-scale]] — 4-principle framework for Clay AI prompts (context, steps, format, Neon multi-column)
- [[signal-based-prospecting]] — Signal detection → enrichment → qualification → routing → action pipeline
- [[smb-tam-sourcing]] — SMB-specific workflow: OpenMart/Google Maps discovery, review analysis, digital maturity scoring
- [[tam-sourcing-pipeline]] — Full TAM system: ICP → source → enrich → score → tier → activate → measure ROI

## Comparisons

- [[personal-email-provider-benchmark]] — 5 personal email providers tested against 2,354 confirmed-valid contacts (43% accuracy)
- [[phone-provider-benchmark]] — 10 mobile phone providers tested across NAMER/EMEA/APAC with TitanX scoring (23% P1 rate)
- [[work-email-provider-benchmark]] — 12 work email providers tested across SMB and enterprise segments (deliverability, accuracy, cost)

## Sources

- [[ai-powered-gtm-automation]] — Clay Academy advanced course (19 lessons: FETC, Claygent Builder, AI Snippets, Twain, new enrichments)
- [[audiences-course]] — Clay Academy Audiences course (9 lessons: unified data layer, SEA framework, Data Hub, 4 use cases)
- [[automated-inbound]] — Clay Academy inbound course (10 lessons: speed-to-lead, scoring, routing, webhooks, inbound pipeline)
- [[automated-outbound]] — Clay Academy outbound course (15 lessons: Clay Sequencer, LGM, SendSpark, Tavus, delivery tools)
- [[best-practices-getting-started]] — Clay University reference docs (36 articles: platform docs, data benchmarks, best practices)
- [[clay-101-gtm-automation]] — Clay Academy foundational course (17 lessons covering FETE, Jigsaw, all core features)
- [[clay-mcp-course]] — Clay Academy MCP course (6 lessons: conversational prospecting, Managed/Custom Functions, Business Context)
- [[crm-enrichment]] — Clay Academy CRM course (7 lessons: HubSpot/Salesforce integration, data freshness, lifecycle)
- [[functions-course]] — Clay Academy Functions course (8 lessons: reusable workflows, governance, 3 use cases, MCP)
- [[limitless-research]] — Clay Academy intermediate course (7 lessons on web scraping toolkit and hierarchy)
- [[signals-and-abm]] — Clay Academy signals course (7 lessons: signal detection, orchestration, ABM architecture)
- [[tam-sourcing-course]] — Clay Academy TAM course (7 lessons: TAM sourcing, ICP definition, SMB, third-party scrapers)

## Synthesis

_No pages yet._
