---
category: reference
last-verified: 2026-07-13
---

# Where Clay Fits in the GTM Stack

## Clay's Role

Clay is the **data enrichment and orchestration layer** for GTM operations. It sits between your lead sources (where you find prospects) and your action tools (where you engage them).

```
Lead Sources → Clay (enrich + score + route) → Action Tools
```

Clay is not a CRM, not an outbound tool, and not a marketing platform. It's the intelligence layer that makes all of those tools work better by ensuring the data going into them is enriched, scored, and routed correctly.

## Common Stack Positions

| Layer | Tools | Clay's Relationship |
|-------|-------|-------------------|
| **Lead Sources** | LinkedIn Sales Navigator, Apollo, ZoomInfo, conferences, inbound forms | Clay ingests leads from these sources and enriches them |
| **Enrichment** | Clay (native), BuiltWith, Clearbit, Firecrawl, custom APIs | Clay orchestrates multiple enrichment providers in waterfalls |
| **Scoring & Routing** | Clay (formulas + Claygent) | Clay scores and segments — this is where the intelligence lives |
| **CRM** | Attio, HubSpot, Salesforce, Pipedrive | Clay pushes enriched, scored records to your CRM |
| **Outbound** | Instantly, Smartlead, Apollo, LinkedIn | Clay feeds personalized data to outbound tools |
| **Automation** | n8n, Zapier, Make | Clay triggers workflows or receives data via webhooks and APIs |
| **Messaging** | Slack, email | Clay can push notifications and approvals to human-in-the-loop channels |

## Key Integration Patterns

- **Clay → CRM**: Push enriched records with scores and segments. CRM is the system of record; Clay is the data warehouse.
- **Clay → Outbound**: Export personalized message drafts and contact data to sequencing tools.
- **Webhook → Clay**: Trigger Clay enrichment from form submissions, CRM events, or automation workflows.
- **Clay → Slack**: Post enrichment results or high-priority leads for human review before action.
- **Clay ↔ n8n**: Bidirectional — n8n triggers Clay via webhook, Clay pushes results back via HTTP API.
