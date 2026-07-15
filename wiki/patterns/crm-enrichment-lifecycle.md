---
title: CRM Enrichment Lifecycle
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources: ["[[crm-enrichment]]"]
tags: [pattern, crm, enrichment, data-hygiene, automation, lifecycle]
---

# CRM Enrichment Lifecycle

The complete pattern for importing CRM data into Clay, enriching it, taking action, and keeping it fresh over time. This is one of Clay's most common and powerful applications for revenue teams.

## Architecture

```
Import → Enrich → Score/Qualify → Take Action → Push Back → Keep Fresh
     ↑                                                          |
     └──────────────── Automated Refresh Cycle ─────────────────┘
```

## Phase 1: CRM Field Architecture

Before importing, design your CRM fields to receive enriched data:

- **Simplicity** — Only create fields you'll actively use
- **Naming conventions** — Prefix Clay-enriched fields with "Clay_" for clarity
- **Controlled creation** — Standard protocol for requesting new fields
- **Logical grouping** — Group all Clay enrichment fields together in your CRM
- **Data type compatibility** — Ensure Clay output format matches CRM field type (dates, currencies, etc.)

## Phase 2: Import

Pull data from your CRM using native integrations:
- [[clay-hubspot-integration]] — Companies, Contacts, Deals, Leads
- [[clay-salesforce-integration]] — Contacts, Accounts, Leads, custom objects

**Filter first:** Create filtered lists in your CRM before importing. Don't spend credits enriching records outside your ICP.

## Phase 3: Enrich

Two primary use cases:

### New Inbound Leads
- Use email + LinkedIn URL as golden identifiers
- Extract company domain from email for company-level enrichment
- Apply [[waterfall-enrichment]] across multiple data providers

### Existing Contact Updates
- Run Lookup to identify existing CRM records
- Apply [[conditional-runs]] — only Create if Lookup returns nothing, only Update if conditions are met
- Avoid overwriting manually-maintained fields (notes, custom scores, relationship data)

### Company-Level Enrichment
- Score companies against ICP (industry, headcount, funding, tech stack)
- Detect expansion signals (headcount growth, funding, new job postings)
- Map subsidiaries to parent companies for enterprise account management

## Phase 4: Take Action

### Slack Notifications
Auto-generate AI summaries of enriched prospects → route to team Slack channels by territory, product line, or account tier.

### Signal-Based Sequence Enrollment
Use [[clay-signals]] to trigger personalized sequences based on business events (funding, hiring, tech changes) rather than arbitrary timing.

### Human-in-the-Loop
Build approval processes for high-value assignments. Let reps customize enterprise messaging. Enable overrides for edge cases. Automation is a **force multiplier**, not a replacement for strategic thinking.

## Phase 5: Push Back to CRM

Use Create/Update actions with conditional logic:
- [[clay-hubspot-integration]] — Lookup → conditional Create/Update
- [[clay-salesforce-integration]] — Upsert (simplified) or Lookup → conditional Create/Update

Always update the "Last enrichment date" field so contacts exit the refresh queue.

## Phase 6: Keep Fresh (Automated Refresh)

### Dynamic Refresh Lists
Create a dynamic list in your CRM filtered by: "Last enrichment date > 30 days ago." The list auto-updates as contacts age into the refresh window.

### Scheduled Imports
Configure Clay to auto-import from the dynamic list on a schedule (daily, weekly). Contacts flow through enrichment workflows and push updated data back.

### Segmented Refresh Cycles
- VIP prospects / active opportunities → monthly refresh
- Broader prospect database → quarterly refresh
- Layer additional triggers: job changes, promotions, high-priority flags

### Selective Data Refreshing
Not all fields need regular updates. Focus refresh on high-velocity fields (email, phone, title) rather than static data (education, founding date).

## The Self-Maintaining System

Once built, this system runs hands-off:
1. Dynamic list identifies stale contacts
2. Scheduled import pulls them into Clay
3. Enrichment workflows refresh data
4. Updates push back to CRM with current "Last enrichment date"
5. Contacts exit the refresh queue until next cycle

## See Also

- [[clay-hubspot-integration]] — HubSpot-specific actions
- [[clay-salesforce-integration]] — Salesforce-specific actions
- [[crm-export-dedup]] — the Lookup-then-Create dedup sub-pattern
- [[conditional-runs]] — Boolean gating for CRM writes
- [[waterfall-enrichment]] — multi-provider enrichment chains
- [[fete-framework]] — this lifecycle implements the full FETE cycle for CRM data
- [[experiment-before-scale]] — test workflows on small batches before scaling
