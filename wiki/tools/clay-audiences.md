---
title: Clay Audiences
type: tool
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[audiences-course]]"
tags:
  - clay-feature
  - audiences
  - unified-data-layer
  - scale
  - crm-sync
  - revops
---

# Clay Audiences

## What It Is

The unified, self-maintaining data layer in Clay. One always-current home for all sales data that enriches itself, keeps lists live, and turns signals into actions.

Audiences break past the 50,000-row table limit to handle millions of records — the course demonstrates examples with 17.5M+ records running at the same speed as a small table. Where [[clay-functions|Tables]] are the lab for experimenting with workflows, Audiences are the production layer where data lives permanently.

## Three Problems It Solves

1. **CRM decay is immediate.** The moment data lands in your CRM, it starts going stale. Job titles change, companies rebrand, headcounts shift. Static imports rot from day one.
2. **Signals happen in real time but your CRM finds out too late.** A champion changes jobs, a target company raises a round, a competitor gets displaced — by the time your CRM reflects it, the window has closed.
3. **Bigger database = worse maintenance burden.** More records means more reimporting, more enriching, more deduplicating. The maintenance cost scales linearly with database size, and eventually nobody does it.

## Four Core Capabilities

1. **Auto-enriches and cleans gaps as they appear.** No manual enrichment jobs. New records get enriched on arrival. Gaps get filled as enrichment providers are added.
2. **Self-updating.** Audiences are saved, live filters that stay current. People drop in and out of segments automatically as their data changes. No reimporting.
3. **Signals become triggers.** A signal fires and the corresponding action follows automatically — alert to Slack, push to sequencer, update CRM field. No human in the middle unless you want one.
4. **Works at scale.** Millions of records at the same speed as thousands. The architecture doesn't degrade with volume.

## SEA Framework: Segment, Enrich, Act

Every Audiences play follows three steps. This is the Audiences counterpart to [[fetc-framework|FETE]] in Tables.

### Segment
Slice your full database with dynamic filters. Audiences are live filters — the segment updates automatically as records change. You define the criteria once and the membership maintains itself.

### Enrich
Add data via signals and bulk enrichments. Always test on 10 rows first before running at scale. Set [[credit-optimization|credit limits]] per enrichment as a hard cap with notification.

### Act
Export to ad platforms, push to a [[clay-sequencer|sequencer]], alert via Slack, or auto-sync back to CRM. The action layer is where enriched data turns into pipeline.

## Audiences vs Tables

| | Tables | Audiences |
|---|---|---|
| **Best for** | One-off, one-time workflows | Always-on workflows |
| **Role** | How you *work on* data (lab) | Where data *lives* (production) |
| **Scale** | Up to 50,000 rows | Millions of records |
| **Connections** | Built per workflow | Continuously synced to CRM/warehouse |

> "Experiment in a Table, then graduate to scale in an Audience."

This maps directly to the [[experiment-before-scale]] pattern: Tables are where you prototype enrichment logic, test formulas, validate Claygent prompts. Once a workflow is proven, you promote it to an Audience where it runs continuously at full scale.

## Connecting Audiences and Tables

The two layers are designed to work together, not replace each other.

### Table to Audience
**Upsert** — match on domain or LinkedIn URL, map fields from table columns to audience fields. Always test with 10 rows first before running the full batch. Upsert means: update if the record exists, insert if it doesn't.

### Audience to Table
**Send to Table** — create a new table from audience records or append to an existing one. Select which fields go across. Useful for pulling a segment into a table for experimental enrichment work.

### Four Audience Enrichments from Tables
When working in a Table, you can access four audience-level enrichments:
1. Pull audience data into the table
2. Update existing audience records from table data
3. Upsert records into an audience
4. Check if a record exists in an audience

## Setting Up: Data Sources

### Salesforce
Four object toggles: Accounts, Contacts, Leads, Opportunities. Turn all four on. Imports are batched to stay light on API limits. After the first full import, all subsequent syncs are incremental — only changed records get pulled.

### Other Sources
- **Snowflake** — connect via SQL queries for warehouse-native data
- **HubSpot** — native integration, similar toggle-based setup
- **Gong** — pull call data and engagement signals
- **BigQuery** — SQL-based connection for analytics warehouse data
- **CSV** — manual upload for one-time imports or supplementary data

### Import Sync vs Record Matching
- **Import sync** = live connection. Data flows continuously from the source into Clay.
- **Record matching** = merge the same person/company from multiple sources using a unique key (e.g., domain, LinkedIn URL). Recommended when multiple data sources feed into the same audience to prevent duplicate records.

## Overwrite Rules

Per-field controls that determine what happens when Clay and your CRM disagree:

| Rule | Behavior | When to Use |
|---|---|---|
| **Always Overwrite** | Clay wins. CRM value gets replaced. | Fields you trust Clay to maintain (e.g., enrichment-derived data) |
| **Never Overwrite** | CRM values are protected. Clay doesn't touch them. | Fields with human-curated data (e.g., account owner, custom notes) |
| **Fill Blank Fields Only** | Clay writes only if the CRM field is empty. | Safe default. Fills gaps without overwriting existing work. |

**Start with Never Overwrite or Fill Blank Fields Only.** Always Overwrite can replace carefully maintained CRM data — use it deliberately, not as a default.

## Export Sync

Sends data from Clay back to Salesforce (or other connected CRMs), merging into existing records rather than creating duplicates. Key behaviors:

- **Create new Salesforce records** via Clay ID mapping — prevents duplicates by checking for existing matches before creating
- **Continuous sync** runs on 24-hour cycles, keeping CRM data current without manual exports
- **Field mapping** controls which Clay fields write to which CRM fields

## Data Hub

The health monitor for your CRM data. Shows the fill rate for every field across the entire audience — a single dashboard that reveals exactly where your data has gaps.

**Example:** Data Hub might show that email is only 9% filled across your audience. That immediately tells you where to focus enrichment spend.

### Signals Tab
Manage all signals centrally from Data Hub. See which signals are active, their trigger rates, and the actions attached to each. This is the control plane for [[clay-signals|signal-based workflows]].

## Net-New People and Companies

Search Clay's database using Sculptor — natural language queries that translate into deterministic filters. Save results directly to an audience with automatic deduplication against existing records.

**Draft mode** is the safety check: review the net-new records before committing them to the audience. This prevents accidentally adding low-quality or irrelevant records at scale.

## Credit Management

Audiences have built-in [[credit-optimization]] mechanisms:

- **Cross-audience dedup** — overlapping records are never enriched twice. If the same person exists in multiple audiences, the enrichment runs once and the result is shared. Auto-dedup happens at the audience layer.
- **Credit spend limits** — set a hard cap per enrichment with notification when the limit is reached. Prevents runaway spend on bulk enrichments.
- **Data Hub targeting** — use fill rates to target enrichment spend precisely at gaps rather than re-enriching fields that are already populated.

## Four Core Use Cases

### 1. CRM Enrichment
Import CRM data into Clay. Use Data Hub to identify gaps. Run bulk enrichments targeting those gaps. Map enriched fields back to CRM. Set up continuous enrichment on scheduled runs. Enable export sync to keep Salesforce current.

> "CRM is the destination, not the pipeline."

The CRM stores the final, enriched version. Clay is where the enrichment and maintenance happens.

### 2. TAM Sourcing
Build ICP filters using Sculptor's natural language interface. Review results in draft mode before committing. Commit to audience with auto-enrichment. Sync net-new accounts to CRM. Set up dynamic territory routing so new accounts flow to the right reps automatically.

See [[tam-sourcing-pipeline]] for the detailed pattern.

### 3. Signal-Based Plays
Add a signal (e.g., champion job change) to an audience. The signal follows the person, not the list — if someone leaves the audience and re-enters, the signal still tracks them. When a signal fires, Clay auto-creates a filtered audience of triggered records. Enrich the signal results and act on them.

See [[signal-based-prospecting]] for the detailed pattern.

### 4. AI Outbound
Signal fires as trigger. Auto-enrich the triggered records with context for personalization. Hand off to [[clay-sequencer|sequencer]] (Clay Sequencer, SmartLead, Instantly, Outreach, Salesloft). AI generates personalized messaging using enriched context. Field mapping is optional for action-only runs where you just need to trigger the sequence.

Add a review step for human-in-the-loop quality control before messages send.

See [[personalized-outbound-pipeline]] for the detailed pattern.

## Who It's For

- **RevOps teams** buried in data maintenance — reimporting, deduplicating, enriching, syncing. Audiences automate the entire maintenance layer.
- **Teams with large CRM databases** past the point of manual management. When you have 100K+ records, manual enrichment jobs and CSV imports don't scale. Audiences handle it continuously.

## See Also

- [[experiment-before-scale]] — the philosophy behind Tables as lab, Audiences as production
- [[crm-enrichment-lifecycle]] — full CRM enrichment pattern at audience scale
- [[clay-hubspot-integration]] — HubSpot-specific audience setup
- [[clay-salesforce-integration]] — Salesforce-specific audience setup
- [[clay-signals]] — signal configuration and management
- [[signal-based-prospecting]] — signal-triggered outbound pattern
- [[tam-sourcing-pipeline]] — net-new account sourcing at scale
- [[personalized-outbound-pipeline]] — AI outbound with audience triggers
- [[credit-optimization]] — credit management strategies across audiences
- [[clay-functions]] — formula and enrichment building blocks used within audiences
