---
title: Clay x Salesforce Integration
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[crm-enrichment]]"]
tags: [clay-feature, crm, salesforce, integration, export, soql]
---

# Clay x Salesforce Integration

Native integration between Clay and Salesforce for importing, enriching, and writing back CRM data. More complex than [[clay-hubspot-integration]] due to Salesforce's enterprise architecture, but includes unique features like Upsert, SOQL, and Lead Conversion.

## Import Setup

1. Click **Import → Salesforce** in Clay
2. Authenticate with your Salesforce instance
3. Import from a **list** (preferred) or **static report** (capped at 2,000 records)
4. Map fields carefully — Salesforce allows extensive customization

**Key difference from HubSpot:** Not all Salesforce objects show in the cell details view by default. Use a Lookup action with the CRM ID to fetch full record details, then "Add as column" for specific fields.

## Sandbox Testing

**Always test in a Salesforce sandbox first.** This is the most important best practice for Salesforce automation.

Setup: Settings → Connections → Salesforce test environment → authenticate with sandbox instance.

Test all Create/Update/Upsert workflows in sandbox before deploying to production. This prevents accidental data corruption in your live CRM.

## Action Types

### Lookup (Read-Only)
Same as HubSpot — pull data from Salesforce into Clay without modifications.

### Create / Update (Write)
Same principles as HubSpot — always use Lookup first, apply [[conditional-runs]] for safe updates.

### Upsert (Salesforce-Only)
Combines Create and Update in one intelligent operation:
- If a record with the specified **external ID** exists → updates it
- If no record exists → creates a new one

Requires an external ID field configured in Salesforce. Eliminates the need for separate Lookup + conditional Create/Update logic.

### Convert Lead (Salesforce-Only)
Automates Salesforce lead management:
1. Lead record converts to a Contact
2. New Account created (or associated with existing match)
3. Optional Opportunity created

Valuable for inbound workflows where qualified leads need to move into the standard Account/Contact structure automatically.

## SOQL Queries

Salesforce Object Query Language for complex data retrieval. Especially useful for one-to-many relationships:

- All opportunities for a specific account
- All activities related to a contact
- Custom object data related to standard objects

Example: Pull account records with related opportunities and activities for multiple domains to identify duplicate "primary" accounts.

**Tip:** Use Claude to generate SOQL queries from plain English descriptions instead of learning SOQL syntax from scratch.

## See Also

- [[clay-hubspot-integration]] — HubSpot equivalent (simpler setup)
- [[crm-enrichment-lifecycle]] — the full import → enrich → action → refresh cycle
- [[crm-export-dedup]] — Lookup-then-Create dedup pattern
- [[conditional-runs]] — Boolean gating for CRM writes
