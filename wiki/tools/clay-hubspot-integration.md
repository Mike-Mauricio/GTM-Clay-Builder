---
title: Clay x HubSpot Integration
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[crm-enrichment]]"]
tags: [clay-feature, crm, hubspot, integration, export]
---

# Clay x HubSpot Integration

Native integration between Clay and HubSpot for importing, enriching, and writing back CRM data. Supports four object types: Companies, Contacts, Deals, and Leads.

## Import Setup

1. Click **Import → HubSpot** in Clay
2. Authenticate with your HubSpot account
3. Select object type (Company, Contact, Deal, Lead)
4. Choose which HubSpot list to pull from
5. Configure: include read-only properties, exclude empty columns

**Pro tip:** Filter data in HubSpot before importing to Clay. Create a filtered list (e.g., "Enterprise contacts only") to avoid spending credits on records you don't need.

## Action Types

### Lookup (Read-Only)
Pull data FROM HubSpot INTO Clay without changing anything in your CRM. Safe for experimentation — no risk to production data.

Use cases:
- Pull existing contact/company records for enrichment
- **Duplicate checking** — lookup by email or domain before creating new records
- Data verification — cross-reference Clay enrichments against CRM data

### Create (Write)
Add new contacts, companies, or deals to HubSpot from Clay. Always combine with Lookup first to prevent duplicates.

### Update (Write)
Modify existing HubSpot records with enriched data. Requires conditional logic to prevent accidental overwrites.

## Conditional Logic for Updates

Critical for safe CRM writes:

| Condition | Use When |
|-----------|----------|
| **Empty fields only** | Prevent overwriting existing data |
| **Recency validation** | Only update if new data is more recent |
| **Confidence threshold** | Only update if data quality meets minimum bar |
| **Source priority** | Only update if new source outranks existing source |

See [[conditional-runs]] for the broader gating pattern.

## Safe Experimentation

**Turn off auto-update** when building Create/Update workflows. Manually trigger on small batches (5-10 rows), verify results, then re-enable automation. See [[experiment-before-scale]].

## Typical Workflow Pattern

```
1. Enrich → gather data from external sources
2. Lookup → check if contact/company exists in HubSpot
3. Create → add net-new records (if Lookup returned nothing)
4. Update → update existing records (with conditional logic)
```

This pattern is the core of the [[crm-enrichment-lifecycle]].

## See Also

- [[clay-salesforce-integration]] — Salesforce equivalent (with Upsert, SOQL, sandbox)
- [[crm-enrichment-lifecycle]] — the full import → enrich → action → refresh cycle
- [[crm-export-dedup]] — the Lookup-then-Create dedup pattern
- [[conditional-runs]] — Boolean gating for enrichments and CRM writes
