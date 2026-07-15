---
title: Lookalike Automation
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [pattern, automation, expansion, lookalikes, crm-triggered]
---

# Lookalike Automation

An automated expansion pattern where every closed-won CRM deal triggers discovery of 10 similar companies, creating a self-expanding pipeline. Uses [[clay-company-lookalikes]] with CRM integration to turn wins into new prospects automatically.

## Architecture

```
CRM Closed-Won → Clay Table → Find Lookalikes → Write to New Table → Vet → Route to Outreach
```

### Step 1: CRM Trigger
Configure Clay to receive closed-won deal notifications from your CRM (HubSpot, Salesforce, etc.). Each new win adds the company to a Clay table automatically.

### Step 2: Find Lookalikes
[[clay-company-lookalikes]] runs automatically on the new company:
- Input: company name and/or domain
- Output: 10 similar companies matched on industry, size, hiring, revenue, growth, tech stack

### Step 3: Write to New Table
Results flow into a dedicated "Lookalike Prospects" table via Clay's write-to-new-table action. This keeps lookalikes separate from the source deal table for independent enrichment and scoring.

### Step 4: Vet with Claygent
Before routing to outreach, vet lookalikes with [[claygent]]:
- **Competitor check** — "Is this company a competitor of ours?" (remove if yes)
- **Existing customer check** — Cross-reference with CRM to avoid targeting current customers
- **Qualification check** — Does the company meet minimum ICP criteria?

### Step 5: Route to Outreach
Qualified lookalikes flow into:
- Scoring pipeline (for prioritization)
- [[personalized-outbound-pipeline]] (for content generation)
- CRM via [[crm-export-dedup]] (for assignment to reps)

## The Math

| Metric | Value |
|--------|-------|
| Closed-won deals per month | 5 (example) |
| Lookalikes per deal | 10 |
| New prospects generated | 50/month |
| After vetting (~60% pass) | 30 qualified prospects/month |
| Annual pipeline expansion | 360 vetted prospects from wins alone |

This runs continuously with zero manual prospecting effort after setup.

## Key Design Decisions

1. **Separate tables for lookalikes** — Don't pollute the won-deals table. Lookalikes need their own enrichment and scoring pipeline.
2. **Vet before routing** — Competitors and existing customers will appear in lookalikes. Always filter before outreach.
3. **Use [[conditional-runs]]** — Only run expensive enrichments on lookalikes that pass vetting.

## See Also

- [[clay-company-lookalikes]] — the core lookalike discovery tool
- [[crm-export-dedup]] — for pushing vetted lookalikes to CRM
- [[claygent]] — for vetting and competitor checks
- [[company-enrichment-pipeline]] — for enriching the lookalike prospects
- [[personalized-outbound-pipeline]] — for generating outreach
