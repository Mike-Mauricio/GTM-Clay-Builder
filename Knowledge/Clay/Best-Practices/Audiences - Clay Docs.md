---
title: "Audiences - Clay Docs"
source: "https://university.clay.com/docs/audiences"
author:
published:
created: 2026-07-14
description: "Build dynamic segments across millions of records, run automated enrichment and signal workflows at scale, and sync results."
tags:
  - "clippings"
---
Overview

Clay Audiences is the unified data layer for your workspace. It combines your CRM, data warehouse, and third-party enrichments into one persistent profile per contact and account, updated in real time.  
Use it to build dynamic segments across millions of records, run automated enrichment and signal workflows at scale, and sync results back to your CRM without managing dozens of separate tables.

**Note (plans & limits):**
- Available on all paid plans at no additional charge — you only pay for the credits and actions you use.
- **Growth:** sync up to 250,000 CRM/data warehouse records with a daily refresh.
- **Launch:** import from Clay's people and companies database and CSV only.
- **Enterprise:** sync up to 25 million CRM/data warehouse records with a 15-minute refresh.

**Setting up Audiences follows four steps:**

1. **Import your data** — connect Salesforce, HubSpot, Snowflake, BigQuery, or import from CSV or Clay's people and companies database.
2. **Create audiences** — build dynamic segments using filters to target the right contacts and accounts.
3. **Enrich and monitor** — run bulk enrichments and signals that write data permanently back to each record.
4. **Write back to your CRM** — sync enriched data and segment membership back to Salesforce or HubSpot.

## Navigating Audiences

Audiences has two main views for managing your data and segments.

**The Audiences page** is the home for all your segments. It replaces hunting through the sidebar list.

- Three tabs: segments **you** created, segments **others in your workspace** created, and **Drafts**.
- Each row shows record count, creator, and inline actions to add an enrichment or automation.
- Create new audiences directly from this page.
- Click into any audience to open the table view, where `Enrich` and `Send` are available.

**Note:** Clicking `Add Data` from anywhere in Audiences routes to `Settings → Sources / Destinations`, where all import and export configurations are managed in one place.

**The Data Hub** is the control center for the data inside your audiences. It has four tabs:

- **Overview** — record, field, enrichment, and signal counts with quick-add shortcuts.
- **Fields** — a list of all fields with fill-rate indicators. Click any field for a side panel showing fill rate, total records covered, source (Salesforce vs. enriched in Clay), cost, type, field description, export status, and associated enrichments.
- **Enrichments** — a central list of every enrichment across your audiences, showing cost vs. budget, run status, and which audiences and fields each enrichment covers. From here you can point a single enrichment at multiple audiences at once.
- **Signals** — the same layout as Enrichments. Add a signal and assign it to multiple audiences from one place.

## Importing your data

To add a data source, click `Add Data` from any view in Audiences. This routes to `Settings → Sources / Destinations`.

**Note:** Connecting a CRM or data warehouse source requires workspace admin access. CSV and Clay table imports are available to all workspace members.

You can import data from:

- Salesforce
- HubSpot
- Snowflake
- BigQuery
- CSV
- Clay's people and companies database

### Importing from Salesforce

**Note:** Setup must be completed separately for each of the four Salesforce objects: `Accounts`, `Contacts`, `Leads`, and `Opportunities`. Work through each tab in turn.

1. Click `Add data` → `Add Source` → select your `Salesforce integration`.
	- If you don't see a Salesforce integration listed, contact your Growth Strategist.
2. You'll see four tabs at the top: `Accounts`, `Contacts`, `Leads`, and `Opportunities`. Start with `Accounts`.
3. Under **Import data from Accounts**, enable `Import sync` to continuously pull Accounts data into Clay Audiences. Imports run incrementally every 15 minutes, with a full sync once a week.
4. (Optional) Enable `Import activities` to also import tasks and events associated with your accounts.  
	- Tasks and Events are automatically linked to the corresponding account records and appear in each account's detail view.
		- Common use cases: track customer touchpoints, identify engaged accounts, filter audiences by recent activity.
5. (Optional) Click `Edit` next to `Import record matching` to combine account records from multiple sources. See **Configuring import record matching** for setup details.
6. Under **Export Accounts data**, leave `Export sync` and `Create new Salesforce records` off for now.
7. Under **Accounts field mapping**, map Clay Companies fields to Salesforce Account fields.
	- Use `Auto-map` to automatically match fields, or configure each mapping manually.
		- The `Scheduled export rule` column controls whether Clay writes each field back to Salesforce. The default is `Never write` — Clay enriches the field in your Audience but won't push it to Salesforce until you update the rule.
		- Click `Preview` to review your mapping before saving.
8. Click the `Contacts` tab. Under **Import data from Contacts**, enable `Import sync`.
9. (Optional) Click `Edit` next to `Import record matching` to combine contact records from multiple sources.
10. Under **Export Contacts data**, leave `Export sync` and `Create new Salesforce records` off for now.
11. Under **Contacts field mapping**, map Clay People fields to Salesforce Contact fields. Add any fields you frequently use or want to segment by.
12. Click the `Leads` tab. Under **Import data from Leads**, enable `Import sync`.
13. Under **Leads field mapping**, add any Lead fields you want to filter or segment by — common fields include `Lead Status`, `Lead Source`, `Title`, and `Company`.
	- **Automatic Lead-to-Contact merging:** When a Salesforce Lead is converted into a Contact in Salesforce, Clay automatically merges the Lead and Contact records into a single person record in your Audiences. This happens under the hood and is not user-configurable — data from both the Lead and Contact is combined and preserved.
		- **Cross-source matching:** Lead records are also deduplicated against Contact records from other sources using LinkedIn URL and email. See **Configuring import record matching** for details.
		- Duplicates across Salesforce Leads, Contacts, and other sources count as one person in your Audiences.
14. Click the `Opportunities` tab. Under **Import data from Opportunities**, enable `Import sync`.
15. Under **Opportunities field mapping**, add any Opportunity fields you want to filter or segment by — common fields include `Stage`, `Amount`, `Close Date`, and `Owner`.
	- Opportunity data is associated with your Companies records and becomes available as a filter in your Companies audience.
16. Click `Save and review`, then `Confirm`.

**Why the native connection matters:** Standard Clay table imports run full API calls on every sync. The Audiences connection uses incremental syncs — only changed records are processed after the initial import — which means far fewer API calls. If your Salesforce admin has raised API limit concerns, this is the fix.

### Importing from HubSpot

**Note:** Setup must be completed separately for People, Companies, and Deals. Complete steps for `People` first, then repeat for `Companies`, then `Deals`.

1. Click `Add data` → `Add Source` → select your `HubSpot integration`.
	- If you don't see a HubSpot integration listed, contact your Growth Strategist.
2. Select `People` at the top of the sync panel.
3. Enable the `Import` toggle.
4. Add any HubSpot Contact fields you frequently use or want to segment by.
5. Name the corresponding Clay fields.
6. Select `Companies` at the top and repeat for accounts.
7. Select `Deals` at the top of the sync panel.
8. Enable the `Import` toggle.
9. Add any Deal fields you want to filter or segment by — common fields include `Deal Stage`, `Amount`, `Close Date`, `Deal Owner`, and `Deal Type`.
	- Deal data is associated with your Companies records and becomes available as a filter in your Companies audience.
10. Name the corresponding Clay fields.
11. Click `Save and review`, then `Confirm`.

**Scheduled export rule** — each field in the field mapping has a `Scheduled export rule` that controls whether Clay writes that field's value back to HubSpot. The default is `Never write`, which means Clay enriches the field in your Audience but won't push it to HubSpot until you update the rule. We recommend leaving fields on `Never write` until you've validated Clay's data quality, to avoid overwriting actively maintained CRM data.

### Importing from Snowflake

<iframe src="https://www.loom.com/embed/c67215bf8ecc4050893bd51344ebf290" frameborder="0" allowfullscreen=""></iframe>
1. Click `Add data` → `Import from Snowflake`.
2. Pick a database → schema → warehouse, then write a SQL query directly. Click `Test` to preview results before continuing.
3. Confirm the preview looks correct, then click `Continue`.
4. Define the `Unique Identifier`:
	- For People: `email` or `user_id`.
		- For Companies: `company_id` or `domain`.
5. (Optional) Configure a `Timestamp Field` for incremental syncing:
	- With a timestamp: syncs run every 15 minutes and only import new or changed records.
		- Without a timestamp: the full query reruns every 12 hours.
6. Map your Snowflake columns to Audience fields.
7. Review and click `Confirm` — Clay begins importing immediately.
8. Monitor the import. If records don't appear immediately, refresh the page to see the latest count.

### Importing from BigQuery

BigQuery is available as a native Audiences import source. The setup follows the same pattern as Snowflake: select your database, schema, and warehouse, then query directly with SQL. Results appear as Audiences data you can map in.

### Importing from CSV

1. Click `Add data` → `Add Source` → `CSV`.
2. Name the source and upload your file.
3. Preview the data to confirm it looks correct.
4. Click `Confirm` — records begin importing immediately.

### Sending data from Clay table

You can also send contacts from any existing Clay table directly to your Audience:

1. Open any table with contacts you want to save to your Audience.
2. Click `Continue` at the bottom of the table.
3. Select `Save to People` or `Save to Companies` depending on the record type.

Records saved from tables are automatically deduplicated and merged with your existing audience data.

### Entity resolution and deduplication

Clay matches records using LinkedIn URL and email to:

- **Cross-source deduplication** — merge the same person from multiple sources.
- **Whitespace detection** — exclude CRM records when importing from CPJ/People Search.

Deduplication across sources is automatic. Within Salesforce, it uses Salesforce IDs — org duplicates carry over as-is. Native within-source deduplication is coming.

Records need a high-confidence identifier to match. Auto-enrichment adds `LinkedIn URL` and `CPJ ID` at no cost to improve matching.

### Configuring import record matching

When you import a new data source into Audiences — for example, a Snowflake table after already importing from Salesforce — import record matching lets Clay combine records from multiple sources when they represent the same person or company. It works by checking whether a shared alias field (such as email or domain) matches exactly across sources, and merging the records if it does.

Import record matching is optional and configured per object, directly within the import settings for each source.

**Example:** If you're importing from both Snowflake and Salesforce, setting `domain` as your alias field ensures that a single company row in your Audiences reflects data from both sources — rather than creating two separate records for the same company.

To configure import record matching:

1. In the import settings panel for any object, find `Import record matching` and click `Edit`.
2. Under `When`, choose the alias field to match on — for example, `Email` or `LinkedIn URL` for people records, or `Domain` for company records.
3. Under `In`, map that alias to the corresponding field in each connected source.
4. Save your settings. Clay will merge records where the alias values match exactly, combining their data into a single record.

**Best practice:** Configure import record matching when adding each new source to prevent duplicate records from accumulating. Email is the most reliable alias field for people records; domain works well for company records.

### Import record matching vs. automatic deduplication

Clay does **automatic deduplication** in the background using **LinkedIn URL + email** — no setup required.

**Import record matching** is the configurable layer: you choose the **alias field** Clay should use to join a *new* source’s records to your existing Audiences records.

**Use it whenever you add a new source** to prevent duplicates from accumulating.

### Unique identifier vs. alias field (Snowflake + BigQuery)

When setting up a Snowflake or BigQuery import, you’ll define a `Unique Identifier` — a field that is **unique and non-null within that source** (e.g., `email` for people; `domain` / `work_email_domain` for companies). Clay uses it to decide whether an incoming row should **create** a new record or **update** an existing one *for that source*.

This is different from **import record matching**, which uses an **alias field** to join records **across sources**.

## Creating an audience

After importing, create audiences to target the right contacts for each use case.

1. Click `People` or `Companies` in the left sidebar.
2. Click the `+` next to `My Audiences`.
3. Select `Criteria` and then add a `Filter` or `Filter group`.

You can filter on three data types simultaneously using AND/OR logic:

- **CRM fields** (mapped on import) — owner, deal stage, lead status, account type, custom fields.
- **Clay enrichment data** — firmographics, work email, phone, tech stack.
- **Clay signals** — job changes, funding, hiring spikes.

New audience-building features:

- **AI filters** — type your filter condition in plain language (e.g., "employee count less than 500") and Clay builds the filter automatically. AI can create individual filter conditions but not filter groups.
- **Filter groups** — combine multiple filter conditions with independent AND/OR operators. Each group has its own set of conditions and its own AND/OR toggle, and groups can be layered for complex segmentation logic.
- **Record detail view** — click into any record to step through your audience one record at a time and see which fields are filled vs. empty. A cleaner alternative to reading the full grid.
- **Archive records** — move records out of your active audience without deleting them. Archived records can be browsed and restored at any time. Useful for cleaning up a segment without losing historical data.

**Best practice:** Always filter your audience to the specific segment you want to enrich before running enrichments. This helps you:
- Control credit spend by enriching only relevant records
- Test enrichments on a small subset before scaling
- Avoid enriching duplicate or low-quality records
For example, filter to `Email Status = Valid` or `Company Size > 50` before enriching contact data.

## Enriching and monitoring

### Adding enrichments

**Best practice:** Define your audience filters *before* running Bulk Enrich to control credit spend. Unlike Clay tables — where filtering is required before enrichment runs — Audiences allows you to enrich your entire dataset if no segment is applied. Always filter to the segment you want to enrich, test on 10 rows, and review results before scaling to the full audience.

Bulk enrichments add contact data, firmographics, technographics, and more to your audience records at scale. They run on an audience and write results permanently back to All People — not just the segment you ran them from. This means any enriched field is immediately available as a filter in any other segment.

To add an enrichment:

1. Navigate to an audience and click `Enrich` → `Add bulk enrich`.
2. Add enrichment columns as you normally would (e.g., `Enrich Person` for LinkedIn URL, title, phone).
3. Select which audiences this enrichment should apply to. You can assign one enrichment to multiple audiences at once.
4. (Optional) Set a `credit budget` — configure a table-level credit cap before running. You can increase the cap incrementally as you validate output.
5. Test on a small batch first — click `Run on 10 rows` to verify output before running at scale.
6. Configure `Field mapping` to determine what writes back to Audiences.
	- Field mapping is enabled by default. Configure it to persist enriched results to your audience records — you can create a new Audience field on the spot during mapping if one doesn't exist.
		- You can disable field mapping if you want to use the enrichment to trigger an action (e.g., enroll in a sequencer) without writing data back to Audiences.
7. (Optional) Enable the `Continuous Enrichment` toggle so new records entering this segment are automatically enriched — typically within 15 minutes.
8. Click `Start Run`.

**Editing an enrichment after creation:** Click an enrichment in the Data Hub sidebar to open the read-only side panel, which shows its status and configuration summary. To change any settings, click `Edit enrichment` to open the full Bulk Enrich settings page.

**Send to Table row cap:** If your bulk enrichment's `Send table data` column targets a table with more than 50,000 rows, you'll see a warning. Enterprise customers can resolve this by enabling auto-deletion (see auto-delete docs) or adding an output column. Non-Enterprise customers should add an output column.

Additional enrichment options:

- **Quality gates** — set a threshold per audience that records must meet to proceed (e.g., "only continue if a valid work email was found"). Records that don't pass the threshold stay in the audience but don't trigger downstream actions.
- **Scheduled runs** — configure enrichments to run on a daily, monthly, or custom schedule for ongoing maintenance use cases.
- **Archived runs** — open any enrichment and click `Archived Run` to view and export data from previous enrichment runs. Useful for audit trails and recovering past output.

**Using Audiences from a Clay table:**

Two Clay enrichments let you move data between a Clay table and your Audience directly.

- In any Clay table, click `Add enrichment` and search for:
- `Upsert Audiences Record` — pushes records from a table into your Audience, creating a new record or merging with an existing one. Use this to commit data from unsupported integrations, or to send a processed table's contacts into your Audience after an outreach workflow.
- `Lookup Audiences Record` — retrieves enrichment data stored in your Audience and pulls it into the table. Use it to reference enriched or signal data in a table workflow without making Salesforce API calls.

### Signals

Signals monitor your audience for key changes and write results permanently to each matching record so you can segment on them.

To add a signal to a segment:

1. Navigate to an audience and click `Enrich`.
2. Click `Signals` → select a signal type (e.g., `Job Change`).
3. Set the `look-back period` for the initial run: `3 months`, `6 months`, or `1 year`.
4. Set the `recurrence frequency` — how often it re-runs going forward.
5. Review the `cost preview per record` shown before the run begins.
6. Click `Save and Run`.

After you add a signal:

- Results write to a **dedicated signal column** on each matching record — stored permanently and globally (not scoped to this segment).
- Clay **automatically creates a companion segment** combining your original filters plus a filter for the new signal result — this is expected, not an error.
- Multiple signals each get their own column; the `Signal Summary` column aggregates all results. Click any row to see per-signal detail.
- Any other segment that filters on this signal type will also surface these results.
- Signals are also managed centrally in `Data Hub → Signals`; a single signal can apply to multiple audiences at once.

## Sending from Audiences

When you have a segment ready, click `Send` → `Create ad sync` to push it to an ad platform.

**Account-based advertising:** sync contact or company segments to LinkedIn, Meta, or Google Ads. Contacts and accounts who no longer qualify are automatically removed from the synced ad audience. See Clay Ads for setup and platform-specific guidance.

**For outbound sequencer and other non-ad workflows:** use `Bulk Enrich` with a sequencer action column, or use `Upsert Audiences Record` to commit qualifying contacts to a Clay table and then enroll them from there.

## Writing back to your CRM

Audiences supports bidirectional sync with Salesforce and HubSpot. Enriched data and segment changes write back automatically.

Map any Clay data or segment membership to CRM fields using the field mapping panel in `Settings → Sources / Destinations`. Examples:

- Personal email → Salesforce `Personal Email` field.
- Segment membership → CRM status, campaign enrollment, lead score, or owner assignment.

**Scheduled export rule** — each mapped field has a `Scheduled export rule` that controls whether and how Clay writes that field's value back to your CRM. The default is `Never write`. Update the rule for any field you want Clay to write back automatically.

**`Create new Salesforce records`** — when enabled, Clay creates new records in Salesforce for contacts that don't already exist there. When off, Clay only updates existing records.

Export sync behavior:

- Exports run every **24 hours**.
- The first export brings everything over; subsequent syncs are incremental — only changed records are processed.

### Salesforce API usage

Audiences uses Salesforce's Bulk API 2.0 for both import and export operations. This is separate from your standard REST API limits.

- **Import:** Uses ~50,000 records per API call. For a 5M-record CRM, this translates to approximately 100 Bulk API calls.
- **Export:** Uses ~10,000 records per batch. Initial exports consume more API calls, but subsequent incremental syncs only process changed records.

**Checking your API limits:** Navigate to `Setup → System Overview → API Usage` in Salesforce to view your remaining Bulk API requests. Most Enterprise Salesforce orgs have limits around 150 million records per day, making API usage a non-issue for the majority of customers.

**Learn more:** Have questions about Audiences? Check out the [Audiences FAQs and best practices](https://university.clay.com/docs/audiences-faqs-and-best-practices#faqs).