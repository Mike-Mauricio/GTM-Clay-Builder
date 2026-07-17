---
title: Clay Table Alerts
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: [[best-practices-getting-started]]
tags: [table-management, automation, monitoring]
---

# Clay Table Alerts

Automated monitoring for Clay tables. Alerts fire when error rates spike, row counts exceed limits, or data stops flowing — so you catch pipeline issues before they compound. Enterprise feature. No credit cost.

## Overview

Table alerts are **opt-in** and configured **per table**. You choose which alert types to enable and set thresholds for each. Alerts appear in-app and can be pushed to email and Slack.

This is the monitoring layer for production workflows. Once you've moved a table from testing to always-on (see [[experiment-before-scale]]), alerts tell you when something breaks without requiring manual table checks.

## Three Alert Types

### Column Failure Rate

Fires when a column's error rate exceeds a configured threshold.

- **Default threshold:** 75%
- **What it catches:** Broken API keys, enrichment provider outages, malformed input data, Claygent prompt failures
- **Column muting:** You can mute non-critical columns to focus alerts on what matters. By default, all columns are enabled for alerting.

**Muting columns:**
- Right-click a column header > "Mute Alerts for Column"
- Use the Column Selector for bulk enable/disable (recommended)
- New columns are automatically enabled for alerting when added

**Best practice:** Mute upstream columns where occasional errors are expected (e.g., web scraping columns that hit dead URLs). Enable alerting only on critical downstream columns — the ones that feed your CRM export or [[clay-sequencer]] delivery.

### Row Count Limit

Fires when your table's row count exceeds a configured threshold.

- **Default threshold:** 45,000 rows
- **What it catches:** Runaway imports, webhook floods, tables approaching Clay's row limits
- **Why it matters:** Tables near their row limit may start dropping new data. For passthrough tables (see [[clay-table-management]]), this signals the auto-delete cycle isn't keeping pace with inbound volume.

### Data Inactivity

Fires when a table with recurring data activity (signals, scheduled sources, or scheduled runs) stops receiving new data for a configured period.

- **Default threshold:** 1 day
- **What it catches:** Broken source connections, expired API tokens, CRM sync failures, signal providers going dark
- **Scope:** Only applies to tables that were actively receiving recurring data. Won't fire on static tables that never had scheduled activity.

## Configuration

1. Navigate to your table
2. Click the warning icon in the bottom-right corner
3. Click "Configure alerts" or the gear icon
4. Toggle "Enable alerts" ON
5. Enable and configure each alert type individually
6. Set thresholds appropriate for your workflow
7. Click Save

Alert rules apply to all users on the table — they're table-level settings, not user-level.

## Viewing and Managing Alerts

### Alert Feed

Active alerts show as a numbered warning icon in the bottom-right corner. The number represents unresolved grouped alerts (not individual alert instances).

**Grouped alerts:** Alerts of the same type and column are grouped together. Each group shows:
- Column name and error type
- Count of unresolved instances (e.g., "12 unresolved logs")
- Most recent timestamp
- Threshold that was exceeded
- Most recent error cause

Click any grouped alert to see the full history — every time that alert fired, what the threshold was, and what error occurred. Clicking an alert also scrolls to and highlights the relevant column in your table.

### Resolution

- **Mark as resolved** — Clears an individual grouped alert. Resolved alerts are grayed out.
- **Mark all resolved** — Clears everything at once.
- **Mark as unresolved** — Only unmarks the most recent alert within a group. Historical logs stay resolved.
- **Hide resolved alerts** — Toggle to show only active issues.

Resolving an alert doesn't fix the underlying issue. If the condition persists, a new alert will fire.

## External Notifications

### Email

Subscribe via the bell icon in the Table Alerts panel. Three frequency options:
- **Immediately** (default) — email on every alert
- **Daily digest** — one email per day with all alerts from that table
- **Weekly digest** — weekly summary

Sent to your Clay account email address.

### Slack

Requires workspace-level Slack connection (admin access needed):
1. Go to Workspace Settings > connect Slack
2. Return to Table Alerts panel > "Connect Channel"
3. Select the target Slack channel
4. Choose notification frequency (same three options as email)

## Cost

Table alerts consume **zero credits**. It's a monitoring feature with no enrichment or action cost.

## When to Use

- Any table in production that processes data automatically
- Tables with [[clay-webhooks]] sources where inbound data quality varies
- Scheduled source tables where you need to know if the source stops refreshing
- High-value tables where a broken enrichment column means missed leads or bad data in your CRM
- Passthrough tables where you need to monitor throughput

## Related

- [[clay-table-management]] — Core table settings including auto-run and passthrough
- [[scheduled-operations]] — Scheduled sources and columns that data inactivity alerts monitor
- [[clay-audiences]] — Always-on workflows that also benefit from monitoring
- [[credit-optimization]] — Alerts help catch runaway enrichments before they drain credits
- [[clay-webhooks]] — Common source type where alerts catch data quality issues
