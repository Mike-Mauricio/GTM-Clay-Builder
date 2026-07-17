---
title: Credit Optimization
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[ai-powered-gtm-automation]]", "[[audiences-course]]", "[[functions-course]]", "[[best-practices-getting-started]]"]
tags: [credits, cost-management, best-practices, experimentation, byok, metaprompter, audiences, functions, actions, data-credits]
---

# Credit Optimization

Strategies for maximizing Clay's value while managing credit spend. Clay's usage-based model means every enrichment, [[claygent]] query, and provider lookup costs credits. Smart credit management is a design discipline, not an afterthought.

## Actions vs Data Credits

Clay tracks usage with **two separate metrics** — understanding the distinction is critical for cost planning:

| | Actions | Data Credits |
|---|---|---|
| **What it measures** | Platform usage capacity (orchestration) | Data marketplace purchases |
| **Cost per enrichment** | Always 1 action | Varies (0.5–10+ credits based on data type) |
| **Rollover** | No — resets each billing cycle | Yes — up to 2× monthly limit (monthly plans); 15% rollover (annual plans) |
| **Top-up** | Not available — must upgrade plan tier | One-time top-ups available (30% premium) |

**Actions** measure when Clay enriches, exports, or executes GTM work. Each record enriched or exported = 1 Action regardless of provider. Actions are consumed even when using your own API keys (BYOK), because Clay still does the orchestration.

**Data Credits** are spent to buy data from Clay's 150+ provider marketplace. Cost varies by data type — emails are cheap, phone numbers are expensive. Each fully enriched record typically costs **6–20 Data Credits** depending on enrichment types and BYOK usage.

### What Doesn't Cost Actions or Data Credits

- Importing data from CRM or warehouse
- Webhook imports
- Clay formulas, filters, and [[clay-normalization-tools|normalization]]
- [[ai-formulas]] (deterministic transforms)
- Sculptor queries
- CSV exports
- Send Table Data / Lookup Single Row operations
- Creating audiences (only the export counts)

### Plan-Level Capacity

| Plan | Actions/month | Data Credits/month |
|---|---|---|
| Launch | 15,000 | 2,500–10,000 |
| Growth | 40,000 | 6,000–100,000 |
| Enterprise | 100,000+ | 100,000+ |

### Workbook Credit Limits (Enterprise)

Admins can set per-workbook Data Credit spend limits to control usage at the workbook level. When the limit is reached, further Actions are blocked until the admin raises the cap.

## Zero-Credit Tools

These Clay features cost nothing — use them liberally:

| Tool | Purpose |
|------|---------|
| [[ai-formulas]] | Data transformation, extraction, calculation, classification |
| [[clay-normalization-tools]] | Company name cleanup, phone formatting, location normalization, whitespace removal |
| Table filters & views | Segmentation and organization |
| CSV export | One-time data download |

## Credit-Saving Strategies

### 1. R&D Budget (10-15% of monthly credits)
Allocate a fixed experimentation budget for testing new enrichments, messaging frameworks, and targeting signals. Frame credit spend as "buying insights" — even failed experiments teach you what doesn't work.

### 2. Test-Then-Scale
Never run enrichments on the full table first:
- **5-10 rows** → Validate the enrichment returns useful data
- **50 rows** → Confirm quality at moderate scale
- **Full dataset** → Scale with confidence

See [[experiment-before-scale]] for the complete pattern.

### 3. Cheapest-First Ordering
In [[waterfall-enrichment|waterfall enrichments]], always order providers by credit cost ascending. Credits are refunded on misses, so trying the cheapest option first costs nothing extra.

### 4. Conditional Runs
Use [[conditional-runs]] to gate expensive enrichments behind qualification. Only spend credits on records that pass initial filters (e.g., right industry, right headcount, has a valid domain).

### 5. BYO API Keys (BYOK)
Bring your own OpenAI or Anthropic API keys for AI-powered enrichments. Reduces costs by up to **90%** compared to Clay's built-in AI credits. Per [[ai-powered-gtm-automation]], 90% of Clay users input their own API keys — this is the norm, not the exception. Also turn off table runs while actively building to avoid burning credits on incomplete configurations.

### 6. Sandbox Testing
Use Clay's Sandbox environment to test workflows without consuming production credits.

### 7. Linked Tables for Company Data
When enriching people, link back to the company table for shared data (industry, funding, tech stack). Enrich once at the company level, pull into every contact at that company — avoids paying per-person for company-level data.

### 8. Metaprompter for Better Prompts
Use Clay's Metaprompter ("Help me" button) to generate better [[claygent]] prompts. Better prompts = fewer retries = fewer wasted credits.

## Credit Tiers (Claygent)

| Model | Credits | Use Case |
|-------|---------|----------|
| Helium | 1 | Basic lookups, yes/no questions, simple extraction |
| Argon | 3 | Complex reasoning, multi-source synthesis, deep research |

Choose the cheapest tier that can handle the task. Don't default to Argon.

## Tool Selection Hierarchy

Before spending credits, check if a free tool can handle the job:

| Tool | Cost | Best For |
|------|------|----------|
| [[ai-formulas]] | Free | [[deterministic-vs-generative\|Deterministic]] transforms — extraction, calculation, formatting |
| Use AI (BYOK) | ~90% cheaper | Generative transforms with your own API key |
| [[claygent]] (Helium) | 1 credit | Simple web research, yes/no questions |
| [[claygent]] (Argon) | 3 credits | Complex reasoning, multi-source analysis |

### 9. [[metaprompter|Metaprompter]] for Better Prompts
Use Clay's [[metaprompter|Metaprompter]] ("Help me" button) to generate better prompts before spending credits. Better prompts = better results on the first try = fewer retries = fewer wasted credits.

### 10. Free Testing in [[claygent-builder|Claygent Builder]]
Testing inside Claygent Builder consumes zero credits. Iterate on agent configurations as many times as needed before deploying to tables.

## Audiences-Scale Credit Management

[[clay-audiences]] introduces credit strategies at enterprise scale:

- **Data Hub** — shows fill rate for every field across your entire audience. Target gaps precisely (e.g., "email only 9% filled") instead of enriching everything blindly.
- **Reuse enrichments across audiences** — point one enrichment at multiple audience segments. Overlapping records are auto-deduped at the audience layer — Clay never enriches the same record for the same field twice.
- **Per-enrichment credit spend limits** — set a hard cap on any bulk enrichment. Hit the limit → get notified → decide whether to continue. Prevents runaway spend at scale.
- **Continuous enrichment scheduling** — set daily/monthly/custom schedules for ongoing enrichment. Budget is predictable because you control frequency × segment size × cost per row.

## Function Governance Patterns

[[clay-functions]] provide built-in credit controls:

- **Conditional checkbox input** — expensive enrichments (e.g., phone lookups) only run when a checkbox is explicitly set to true. Prevents accidental expensive runs on 1,000 rows.
- **GDPR compliance gating** — conditional logic checks contact region before enrichment runs and stops workflow for restricted geography. Lives inside the function → runs every time for every caller → nobody can skip it.
- **Credit cost visibility** — credit costs don't show in the calling table (they live on the function view). Include costs in an internal catalog to prevent surprises. A function costing 4 credits/row × 10,000 rows = 40,000 credits.

## See Also

- [[experiment-before-scale]] — the testing workflow
- [[waterfall-enrichment]] — cheapest-first provider ordering
- [[conditional-runs]] — gating logic
- [[ai-formulas]] — zero-credit transformations
- [[claygent]] — credit-tiered AI scraping
- [[metaprompter]] — prompt improvement before spending credits
- [[claygent-builder]] — free testing environment
- [[deterministic-vs-generative]] — choosing free vs. paid tools
- [[clay-audiences]] — Audiences-scale credit controls
- [[clay-functions]] — Function governance patterns
