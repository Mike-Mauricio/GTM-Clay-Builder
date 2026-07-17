---
title: Scheduled Operations
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: [[best-practices-getting-started]]
tags: [table-management, automation, scheduling]
---

# Scheduled Operations

Clay's three mechanisms for keeping table data current over time: **scheduled sources** (refresh where data comes from), **scheduled columns** (re-run enrichments), and **table versions** (structural change tracking with restore capability). These are the table-level automation tools — for always-on, persistent workflows, see [[clay-audiences]].

## Scheduled Sources

Automatically re-import data from any source (Find People, Find Jobs, Salesforce, HubSpot, etc.) on a recurring schedule. This keeps your table's input data fresh without manual re-pulls.

### Setup

**For new sources:**
1. After adding a source, a modal appears with scheduling options
2. Under "Run this source," select "On a schedule"
3. Choose frequency
4. Click "Update Source Schedule"

**For existing sources:**
1. Click the source column title > Sources > select your source
2. Under "Run this source," select "On a schedule"
3. Choose frequency and save

### "Update Existing Rows" Toggle

This toggle determines what happens when the scheduled source runs:

- **ON:** Existing rows are updated with any new information from the source. Use for data hygiene — keeping CRM-sourced records current as fields change in the CRM. Higher credit usage because re-imported rows trigger downstream enrichments.
- **OFF:** Only net-new rows are added. Existing records are untouched. Lower credit cost. The default for most use cases.

**Important interaction with auto-run:** If "Update Existing Rows" is ON and you want enrichments to re-run on updated rows, turn OFF the "Keep existing results" option in table auto-run settings. Otherwise, existing enrichment results won't refresh even though the source data changed. See [[clay-table-management]] for the full auto-run hierarchy.

### Common Use Cases

- **CRM sync:** Pull new leads from HubSpot/Salesforce daily, enrich net-new records automatically
- **Job board monitoring:** Refresh job postings weekly to catch new openings at target accounts
- **Contact discovery:** Re-run Find People monthly to catch new hires at target companies
- **Signal refresh:** Keep [[clay-signals]] data current by re-pulling source data on a schedule

## Scheduled Columns

Automatically re-run specific enrichment columns — or all columns in a table — on a recurring schedule. This keeps enrichment data current as the underlying reality changes (company headcount shifts, funding rounds close, tech stacks evolve).

### Setup

1. In a table, click the gear icon in the bottom-right corner
2. Under "Run Settings," select "Re-run columns on a schedule"
3. Choose frequency
4. Choose scope: "All columns" (entire table) or "Only selected columns"

### When to Use

- **Company data freshness:** Re-enrich headcount, funding, and tech stack quarterly
- **Contact validation:** Re-verify emails monthly to catch bounces before they hit your [[clay-sequencer]]
- **Score recalculation:** Re-run [[lead-scoring]] formulas after enrichment data refreshes
- **Competitive monitoring:** Re-scrape competitor pages weekly for pricing or feature changes

### Credit Implications

Scheduled column runs consume credits every time they fire. Be deliberate:
- Schedule only columns that need freshness (not static data like founding year)
- Use "Only selected columns" to avoid re-running expensive enrichments that don't change often
- Combine with [[conditional-runs]] — the "Only run if" condition is still respected during scheduled runs
- Follow [[credit-optimization]] principles: gate expensive enrichments, cheapest first

## Table Versions

Structural change tracking that lets you snapshot and restore table configurations. This is your safety net when making changes to production tables.

### What Gets Versioned

Table versions capture **structure and configuration only**:
- Column configurations and settings
- View configurations
- Active filters and sorts
- Table-level run settings

**Cell data is NOT versioned.** If row data is overwritten or deleted, versioning cannot recover it. This is structural insurance, not a data backup.

### Automatic Snapshots

Clay automatically creates a version snapshot after approximately 15 minutes of inactivity on a table. Every editing session produces a recoverable checkpoint without manual action.

### Manual Snapshots

Create before major structural changes — column restructuring, view reorganization, testing new enrichment configurations.

1. Click "History" in the bottom-right corner
2. Select "Save configuration version"
3. Add a title/description (optional but recommended)
4. Click "Create"

### Restoring a Version

1. Click "History" > "All configuration versions"
2. Select the target version to preview it (read-only)
3. Click "Restore Configuration" to see a summary of changes
4. Confirm with "Restore this version"

**Safety net:** Restoring automatically creates a new snapshot of your current configuration first, so you can always undo the restore.

**What changes on restore:**
- Columns added after the snapshot are removed
- Column settings revert to snapshot state (applies to new rows only — re-run manually for existing rows)
- Deleted columns are restored with original configurations and any data that existed at deletion
- Sorts, filters, and table settings revert
- Workspace location and permissions are NOT affected

### Retention by Plan

| Plan | Version History |
|---|---|
| Free / Trial | Not enabled |
| Growth / Launch | 30 days |
| Enterprise | 180 days |

## Plan-Based Limits

Both scheduled sources and scheduled columns have plan-based limits on the total number of tables that can use scheduling. The exact limits vary by plan tier. Check your Clay workspace settings for your current allocation.

## Scheduled Operations vs. Audiences

Scheduled operations (sources + columns) add time-based automation to regular Clay tables. They're appropriate for:
- Periodic refreshes (daily, weekly, monthly)
- Batch-oriented workflows
- Tables where you want manual control between scheduled runs

[[clay-audiences]] are the always-on alternative — they continuously process data as it enters, with no scheduling required. Audiences are better for:
- Real-time or near-real-time processing
- Persistent, production-grade pipelines
- Workflows that need to run indefinitely without manual intervention

The progression: build and test in Tables (auto-run OFF), add scheduling when the workflow is proven, promote to Audiences when it needs to run always-on. See [[experiment-before-scale]].

## Related

- [[clay-table-management]] — Auto-run hierarchy and passthrough tables
- [[clay-table-alerts]] — Monitoring for scheduled workflows (data inactivity alerts)
- [[clay-audiences]] — Always-on alternative to scheduled table workflows
- [[conditional-runs]] — Boolean gating respected during scheduled runs
- [[credit-optimization]] — Managing credit spend for recurring enrichments
- [[experiment-before-scale]] — The build-test-scale progression
