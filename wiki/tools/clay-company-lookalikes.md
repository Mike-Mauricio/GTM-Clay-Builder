---
title: Clay Company Lookalikes
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, find, lookalikes, expansion, prospecting]
---

# Clay Company Lookalikes

Clay's native action for finding companies similar to a given target. Input a company name or domain, receive 10 lookalike companies matched on attributes like industry, size, hiring trends, revenue, growth signals, and technology usage.

Replaced the sunset Ocean.io integration — now a native Clay capability.

## How It Works

### Simple Lookup
1. Drop a company name into a Clay table
2. Add "Find Company Lookalikes" enrichment
3. Receive 10 similar companies per input
4. Each lookalike includes: company name, domain, matching attributes

### Matching Attributes

Lookalikes are matched on:
- Industry / vertical
- Company size (headcount)
- Hiring trends and velocity
- Revenue range
- Growth signals
- Technology usage / tech stack

## Automated Expansion Pattern

The real power is in the [[lookalike-automation]] — triggering lookalike discovery from CRM events:

```
CRM closed-won trigger → Add to Clay → Find Lookalikes → Write to new table → Vet with Claygent → Route to outreach/scoring
```

Every closed-won deal generates 10 new prospects automatically. See [[lookalike-automation]] for the full pattern.

## When to Use

| Scenario | Use Lookalikes? |
|----------|----------------|
| Just won a deal, want more like them | Yes — trigger on closed-won |
| Building initial TAM from scratch | Maybe — better to use [[clay-find-companies]] with filters |
| Expanding into an adjacent market segment | Yes — input a company in the new segment |
| Competitor is winning deals you want | Yes — input the competitor's customers |

## See Also

- [[lookalike-automation]] — the automated closed-won workflow
- [[clay-find-companies]] — alternative for filter-based discovery
- [[clay-ai-icp-search]] — alternative for AI-driven ICP discovery
- [[claygent]] — for vetting lookalike results (competitor checks, etc.)
