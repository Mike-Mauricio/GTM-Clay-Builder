---
title: Clay Table Management
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: [[best-practices-getting-started]]
tags: [table-management, automation]
---

# Clay Table Management

Core settings that control how Clay tables behave — deduplication, auto-run logic, passthrough processing, versioning, and structural metadata. These settings determine the difference between a table that burns credits and one that runs like a production system.

## Auto-Dedupe

Continuously monitors a specified column for duplicate values. When duplicates are detected, Clay retains the **oldest row** and deletes the rest.

**Constraints:**
- Blank cells are excluded from dedup checks
- Cells with 200+ characters are excluded
- You choose which column to monitor (typically email, domain, or LinkedIn URL)

**When to use:** Any table receiving ongoing data from [[clay-webhooks]], scheduled sources, or CRM imports where duplicates are likely. Essential for inbound tables where the same lead may submit a form multiple times.

## Auto-Run Hierarchy

Auto-run is a two-level system — a table-level master switch and column-level individual controls. Understanding this hierarchy is critical for [[credit-optimization]].

### Table-Level (Master Switch)

The parent control that gates all automatic enrichment on the table.

- **ON (default):** Enrichments run automatically when rows are added or edited
- **OFF:** Nothing runs automatically — you must click cells manually

When enabled, you can also toggle **"Keep existing results"** — this prevents auto-run from overwriting cells that already have data. Only errored, empty, or new cells will run. This is the recommended default for production tables to avoid wasting credits re-running successful enrichments.

### Column-Level (Individual Control)

Each enrichment column has its own auto-run toggle, but it **only works when table-level auto-run is ON**.

The hierarchy:

| Table-Level | Column-Level | Result |
|---|---|---|
| OFF | ON or OFF | Nothing runs (master switch overrides) |
| ON | OFF | That specific column skipped |
| ON | ON | Column runs automatically |

### Conditional Runs ("Only run if")

Add boolean gating logic so an enrichment only fires when a formula evaluates to true. This is where [[conditional-runs]] and [[credit-optimization]] intersect.

**Common conditions:**
- `LinkedIn URL is not empty` — gate LinkedIn enrichments behind URL availability
- `Company Size > 50` — only enrich companies that match your ICP
- `Email is empty` — only find email when it's missing (avoids re-running)
- `Industry = "Technology"` — restrict to target verticals

Set up via Edit Column > Run Settings > "Only run if". You can write the formula manually or use Clay's AI helper.

### "Update Existing Rows" Toggle

Controls behavior when a scheduled source re-imports data. Two modes:

- **ON ("All"):** Re-runs enrichments on all rows each scheduled run. Use for data hygiene and backfills. Higher credit cost. Turn off "Keep existing results" if using this mode, otherwise existing data won't actually update.
- **OFF ("Net New"):** Only enriches newly added rows. Skips existing records. Lower credit cost — the default for most production workflows.

## Common Scenarios

**Full automation** — Table ON, all columns ON, no conditions. Every new row triggers every enrichment. Simple but expensive. Only appropriate for low-volume, high-value tables.

**Selective automation** — Table ON, only critical columns ON (e.g., email finding), others OFF. New rows get email enrichment automatically; other enrichments run manually or via conditional triggers.

**Manual control (testing mode)** — Table OFF. Column settings are irrelevant. Must click cells to run anything. This is where you should be when building and iterating. See [[experiment-before-scale]].

**Conditional execution** — Table ON, columns ON, with "Only run if" conditions. Rows that meet criteria get enriched; rows that don't are skipped. The most credit-efficient production setup.

## Best Practices: Building vs. Production

### Building/Testing Phase
1. Turn table-level auto-run **OFF**
2. Add 5-10 sample rows
3. Manually click cells to test enrichments one at a time
4. Validate results, refine prompts and configurations
5. Turn auto-run ON only when the workflow is proven

This follows the [[experiment-before-scale]] principle — Tables are labs, [[clay-audiences]] are production.

### Production Phase
1. Turn table-level auto-run **ON**
2. Enable "Keep existing results" to prevent accidental overwrites
3. Configure column-level toggles strategically — not everything needs to auto-run
4. Use [[conditional-runs]] extensively for cost control
5. Monitor credit usage

## Auto-Delete / Passthrough Tables (Enterprise)

Passthrough tables bypass Clay's standard row limits by automatically processing and forwarding data, then deleting the original rows. This enables **unlimited throughput** for high-volume pipelines.

**How it works:**
1. Data arrives via [[clay-webhooks]] (webhook source required — CSVs don't work)
2. Clay runs all configured enrichments
3. After a 60-second review interval, Clay checks for rows ready to pass through
4. Criteria: table exceeds 5,000 rows AND all enrichments are complete
5. Completed rows are pushed to the destination (Snowflake, HubSpot, Google Sheets, etc.)
6. Original rows are deleted after confirmed successful transfer

**Use case:** High-volume inbound processing, event-driven pipelines, real-time lead routing where you need to process thousands of records without hitting row limits.

**Limitations:** Enterprise only. Webhook source required. 5,000-row threshold before passthrough kicks in (adjustable via support).

## Table Graph Visualization

View Graph renders a visual map of all enrichments and their dependencies within a table. Useful for understanding complex tables with many chained enrichments, debugging column dependency issues, and onboarding teammates to existing workflows.

Access via the table settings dropdown > "View Graph."

## Other Table Settings

**Duplicate table:** Copies the table structure (sources and column configurations) but NOT the data. Useful for creating template tables or testing variations of a workflow.

**Rename / Description:** Basic metadata. Use descriptions to document what a table does, especially in shared workspaces.

**Change log (History):** Tracks structural changes — who modified settings, columns, or enrichments, and when. Includes AI-generated summaries of changes.

Change log retention by plan:
| Plan | Retention |
|---|---|
| Free / Trial | Not enabled |
| Launch / Growth | 30 days |
| Enterprise | 180 days |

## Related

- [[conditional-runs]] — Deep dive on boolean gating logic
- [[credit-optimization]] — Broader strategies for managing credit spend
- [[experiment-before-scale]] — The Tables-as-labs philosophy
- [[clay-audiences]] — Always-on alternative to scheduled table workflows
- [[clay-webhooks]] — Required source for passthrough tables
- [[scheduled-operations]] — Scheduled sources and columns for recurring automation
- [[clay-table-alerts]] — Automated monitoring for production tables
