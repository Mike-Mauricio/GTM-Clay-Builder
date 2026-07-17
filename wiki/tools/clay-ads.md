---
title: Clay Ads
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [tool, ads, meta, linkedin, google-ads, audience-sync, compliance, abm]
---

# Clay Ads

Clay's native ad audience sync feature. Build contact and account lists from your CRM or data warehouse, enrich for better match rates, and sync to LinkedIn, Meta, and Google Ads. Designed compliance-first — lists must originate from first-party data sources.

## Supported Platforms

- **LinkedIn** — Contact and account audiences. Created within 48 hours of sync.
- **Meta (Facebook)** — Contact audiences. Created within 24 hours of sync.
- **Google Ads** — Contact audiences. Clay-provided data is filtered out on sync (Google prohibits third-party sourced data).

## How It Works

1. Go to `Ads` in the left sidebar and click `New Ad Sync`
2. Select a source: CRM (Salesforce, HubSpot), data warehouse (Snowflake), or CSV
3. Connect your ad platform account (LinkedIn Campaign Manager or Meta Business Manager)
4. Map columns — critical combinations for match rates:
   - **Contacts:** Hashed email + first name + last name
   - **Accounts:** Company name + company website
5. Review audience insights and estimated match rate
6. Send audience to the selected platform

Once synced, audiences update automatically as Clay table data changes. New rows matching criteria are added; rows that no longer match are removed.

## Boosting Match Rates

Personal emails dramatically improve match rates because most users register on social platforms with personal addresses. Clay provides a `Hashed Email for Ads` waterfall within the Ads surface that finds and hashes personal emails automatically.

Typical match rates:
- **Meta:** ~40-60%+ with personal emails
- **LinkedIn:** Up to ~95% with personal emails

Hashed emails use SHA-256 one-way encryption — ad platforms match contacts without seeing raw addresses. See [[versium]] for the underlying email hash provider.

## Key Use Cases

- **Target high-intent prospects** synced from CRM pipeline stages
- **Re-target leads** based on website activity or engagement signals
- **Exclusion lists** — prevent ads to existing customers, employees, or open opportunities
- **Job change targeting** — executives who recently changed roles or got promoted
- **TAM expansion** — target leads not yet in your CRM

## Compliance

### Regional Rules

- **US contacts:** Can be sourced from Clay's data or first-party data
- **Non-US contacts (especially EU/GDPR):** Must come from first-party data only (CRM, data warehouse, CSV with consent)
- **Google Ads:** Clay-provided data is automatically filtered out on sync. Plan Google audiences around first-party data only.

### Built-In Controls

Clay automatically applies targeting controls based on contact location and data source. These run behind the scenes on every audience build — no manual configuration needed.

### Best Practices

- **Collect and store consent in your own systems.** Non-US audiences require first-party data with captured consent.
- **Keep opt-outs current.** Sync opt-out status into Audiences and filter from Ad Sync segments. Clay runs full replacement syncs every 2 days.
- **Cannot build from other Clay tables.** Within the Ads surface, you cannot pull from other Clay tables or use Clay's contact search. This is a structural guardrail.
- Workspace admins can disable 3rd party enrichment entirely within the Ads surface.

### Opt-Out Handling

Opt-outs are managed at the source level (CRM/data warehouse or opt-out field in Clay Ads table). Full replacement syncs mean removals are reflected in the ad platform within 2 days.

## Pricing & Limits

- Available on **Growth** (1 ads platform sync) and **Enterprise** (unlimited audiences) plans
- Each record exported/synced = 1 action. Data credits apply for enrichments used to build the audience.
- 50,000 row limit per Ads table. For larger audiences, create multiple Ads tables and attach multiple audiences to campaigns.
- Ads tables are intentionally narrow — pull in a list, boost match rate, sync out. All other enrichment work lives in separate tables.

## Meta System User Token

For production workflows, use a system user token instead of OAuth. System user tokens provide indefinite access without 60-day manual renewal.

Setup: Meta Business Settings > System Users > create Admin user > assign app + ad account with Full Control > generate token with `ads_management` permission and `Never expire` policy.

## See Also

- [[versium]] — email hash provider for ad audience matching
- [[clay-audiences]] — persistent data layer that feeds ad syncs
- [[abm-architecture]] — ABM ad campaigns as part of multi-stage strategy
- [[conditional-runs]] — filtering contacts before ad push
