---
title: CRM Export with Dedup
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[crm-enrichment]]"]
tags: [pattern, export, crm, deduplication, data-hygiene]
---

# CRM Export with Dedup

A two-step export pattern that prevents duplicate contacts in your CRM. Instead of blindly pushing all Clay records into the CRM, first check which contacts already exist, then conditionally create only net-new records.

## The Pattern

### Step 1: Lookup Existing Contacts
1. Add enrichment → CRM integrations → "Lookup Contact" (HubSpot, Salesforce, etc.)
2. Use **email** as the unique identifier (most reliable)
3. Run on 10 rows to test
4. Clay returns a Contact ID for matches, empty for non-matches

### Step 2: Conditional Create
1. Add enrichment → CRM integrations → "Create or Update Contact"
2. Map Clay fields to CRM fields (name, email, company, title, custom fields)
3. Set [[conditional-runs|conditional run]]: **"Only run if Contact ID is empty"** (no matching contact found)
4. Test on 10 rows
5. Review mapped data before scaling
6. Run on full dataset

## Why This Matters

| Without Dedup | With Dedup |
|--------------|------------|
| Duplicate contacts in CRM | Only net-new contacts created |
| Data conflicts (which record is canonical?) | Clean, single-source records |
| Sales team confusion | Clear, trustworthy CRM data |
| CRM cleanup projects downstream | Clean from the start |

## Optional: Domain Validation

For extra safety, use an [[ai-formulas|AI Formula]] to compare the email domain with the company domain:
- If `email_domain == company_domain` → higher confidence match
- If they differ → flag for manual review (might be a personal email or wrong company)

## Supported CRMs

- HubSpot
- Salesforce
- PipeDrive
- Close
- Copper
- Others via HTTP API

## Best Practices

1. **Always lookup before creating** — Never skip Step 1
2. **Email is the best unique identifier** — More reliable than name matching
3. **Test with small batches** — Run 10 rows of lookup, verify matches, then 10 rows of create
4. **Monitor exports** — Check CRM after each batch for accuracy
5. **Run periodic CRM cleanup** — Even with dedup, data quality degrades over time

## Broader Context

This pattern is one step within the full [[crm-enrichment-lifecycle]], which covers the complete import → enrich → action → refresh cycle. For CRM-specific integration details, see [[clay-hubspot-integration]] and [[clay-salesforce-integration]]. Salesforce's Upsert action can simplify this pattern by combining Create and Update in one operation.

## See Also

- [[conditional-runs]] — the mechanism that prevents duplicate creation
- [[clay-email-waterfall]] — emails used as unique identifiers must be validated
- [[fete-framework]] — CRM export is the final Export phase
- [[experiment-before-scale]] — always test CRM exports on small batches
- [[crm-enrichment-lifecycle]] — the full CRM enrichment cycle this pattern fits into
- [[clay-hubspot-integration]] — HubSpot Lookup/Create/Update actions
- [[clay-salesforce-integration]] — Salesforce Upsert simplifies dedup
