---
title: TAM Sourcing Pipeline
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[tam-sourcing-course]]"
tags:
  - pattern
  - tam
  - pipeline
  - scoring
  - tiered-routing
  - systems-thinking
  - roi
---

# TAM Sourcing Pipeline

TAM sourcing is a continuous revenue engine, not a one-time list pull. The pipeline treats your Total Addressable Market as a living system that discovers, qualifies, routes, and activates accounts on an ongoing basis — then measures what works and feeds results back into the process.

## Architecture

```
Define ICP → Source Companies → Enrich → Score/Classify → Segment → Route → Activate → Measure → Refine
     ↑                                                                                          |
     └──────────────────────────────── Feedback Loop ───────────────────────────────────────────┘
```

## Step 1: Define ICP

Start with a pain-first approach using [[icp-definition]]. Your ICP definition should cover three dimensions:

1. **Firmographic** — Industry, employee count, revenue range, geography, growth stage
2. **Technographic** — Current tech stack, tools in use, integration needs, platform maturity
3. **Behavioral** — Hiring patterns, funding activity, content signals, competitive moves

The ICP is not static. It refines as pipeline data reveals which segments actually convert.

## Step 2: Source Companies

Layer multiple sourcing channels to maximize coverage:

- **[[clay-find-companies]]** — Broad firmographic sourcing across standard B2B databases
- **[[openmart]]** — Purpose-built for SMB and local business discovery (see [[smb-tam-sourcing]])
- **[[clay-google-maps]]** — Global coverage for location-based businesses
- **[[clay-company-lookalikes]]** — Find companies similar to your best customers
- **[[clay-ai-icp-search]]** — AI-generated company lists based on natural language ICP descriptions
- **[[apify]]** — Niche directory and platform scrapers for verticals that standard databases miss

No single source covers the full TAM. The goal is overlapping coverage with deduplication downstream.

## Step 3: Enrich

Three enrichment layers, each serving a different purpose:

**Standard data via [[waterfall-enrichment]]:**
Chain multiple providers with cheapest-first fallthrough logic for company basics — headcount, revenue, industry, domain, social profiles.

**Custom research via [[claygent]]:**
- Technographic intelligence (e.g., HG Insights integration) to map current tech stacks
- Automated content monitoring — scrape pricing pages, team pages, and blog posts for real-time signals
- Competitive positioning research from public sources

**Market context via [[perplexity-enrichment]]:**
Industry trends, recent news, market positioning, and competitive landscape for each account.

Gate expensive enrichments behind initial qualification. Run cheap/free enrichments first, then only spend credits on records that pass basic filters.

## Step 4: Score and Classify

Build multi-factor scoring models with weighted dimensions:

| Dimension | Weight | Signals |
|-----------|--------|---------|
| Competitive position | 30% | Current vendor, stack fragmentation, consolidation readiness |
| Technology fit | 25% | Stack compatibility, integration complexity, platform maturity |
| Growth rate | 20% | Headcount change, revenue trajectory, market expansion |
| Recent funding | 15% | Round size, stage, investor quality, runway |
| Executive changes | 10% | New CRO/CTO/VP hires, leadership turnover |

Use Clay's Score Row or AI formulas to compute composite scores. Signal convergence matters more than any single indicator — a company hitting 3 moderate signals often outperforms one hitting a single strong signal.

See [[lead-scoring]] for detailed scoring frameworks.

## Step 5: Tiered Account Routing

Automatically route accounts based on composite scores:

**Tier 1 (Score 80-100):** Personalized outreach from senior reps with custom research packages. These accounts get individual attention — tailored messaging, executive-level contact strategies, and account plans before first touch.

**Tier 2 (Score 60-79):** Standard sequences with targeted messaging. Segmented by use case or vertical, with personalization at the template level rather than per-account.

**Tier 3 (Score below 60):** Broader marketing campaigns and nurture tracks. These accounts enter automated sequences and get re-scored periodically as new signals emerge.

AI-powered tier classification (Enterprise / Mid-Market / SMB) further informs sales approach and expected deal size. A mid-market account in Tier 1 gets different treatment than an enterprise account in Tier 1.

## Step 6: Activate

**CRM integration with strategic field mapping:**
Translate raw enrichment data into actionable insights. Don't push raw data — push intelligence. Example: instead of "Uses Okta, CrowdStrike, Splunk, Carbon Black," push "High consolidation opportunity — fragmented security stack across 4+ vendors."

**Slack summaries for sales enablement:**
Real-time contextual intelligence delivered where reps already work. Each alert includes AI-generated talking points and recommended next steps.

**Automated sequence enrollment:**
Tier-based routing triggers the right outreach cadence automatically. Tier 1 accounts get flagged for manual review before activation; Tier 2 and 3 enroll directly.

## Step 7: Measure ROI

Track four categories of pipeline health:

- **Coverage rate** — Accounts in CRM / Total TAM x 100. Are you reaching enough of the market?
- **Penetration rate** — ICP match % across your customer base. Are you winning the right accounts?
- **Pipeline quality by segment** — Conversion velocity, sales effort per deal, close rates by tier. Which segments produce the best pipeline?
- **Revenue attribution by segment** — LTV, retention, expansion revenue by tier and segment. Which segments produce the best customers?

## TAM Freshness

Your TAM decays the moment you build it. Maintain freshness with automated refresh workflows:

- **Daily:** Monitor for funding rounds, executive changes, competitive shifts
- **Weekly:** Re-score existing accounts as new enrichment data arrives
- **Monthly:** Full TAM refresh — re-source, re-enrich, re-classify

Change detection triggers Slack alerts for high-priority signals: new funding, CRO hires, product launches, competitive losses. These alerts re-route accounts through the scoring pipeline in real time.

## 4-Step Universal Framework

This framework applies beyond prospecting to any data-driven GTM workflow:

1. **Define data inputs** — Identify multiple sources with fallback mechanisms. Never rely on a single source.
2. **Design data processing** — Layer enrichment, AI classification, and scoring. Each step should add signal, not just data.
3. **Build intelligence layer** — Qualification rules, AI enhancement, and feedback loops that improve over time.
4. **Design output integration** — CRM flow, outreach triggers, and performance measurement. Every output should be actionable.

## Real-World Examples

### Lightspeed Restaurant System

A restaurant POS company built a full TAM pipeline using Clay:

1. **Source:** [[clay-google-maps]] + [[openmart]] for restaurant discovery across target markets
2. **Enrich:** [[claygent]] estimated annual revenue from public signals (menu prices, review volume, location data)
3. **Classify:** AI formulas categorized cuisine type, service model, and price tier
4. **Score:** Multi-factor ICP scoring weighted toward revenue potential, growth signals, and tech readiness
5. **Activate:** CRM records created with auto-triggered outreach sequences

**Result:** 30x prospecting capacity (from 20-30 accounts/week manually to 200+/day automated), with significantly improved conversion rates because every account arrived pre-qualified with context.

### SaaS Platform Consolidation

A security platform targeting companies ready to consolidate fragmented tool stacks:

1. **Source:** Companies using specific technology combinations indicating consolidation readiness
2. **Enrich:** Technographic data + intent signals + growth indicators via [[waterfall-enrichment]] and [[claygent]]
3. **Score:** "Integration Complexity Score" and "Expansion Potential" computed from stack analysis
4. **Activate:** Auto-create Salesforce records with computed scores and intelligence summaries
5. **Alert:** Slack notifications with actionable intelligence for the sales team

The key insight: sourcing criteria were defined by the problem (consolidation readiness), not by firmographics alone.

## Related

- [[tam-sourcing]] — Core concept
- [[icp-definition]] — Defining your Ideal Customer Profile
- [[smb-tam-sourcing]] — Specialized pipeline for local/SMB businesses
- [[lead-scoring]] — Scoring frameworks and models
- [[signal-based-prospecting]] — Using signals to trigger outreach
- [[crm-enrichment-lifecycle]] — Keeping CRM data fresh post-activation
- [[experiment-before-scale]] — Test in Tables before promoting to Audiences
