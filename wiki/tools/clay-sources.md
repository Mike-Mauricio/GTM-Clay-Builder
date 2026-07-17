---
title: Clay Sources
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[best-practices-getting-started]]"]
tags: [tool, sources, import, csv, crm, limits, data-ingestion]
---

# Clay Sources

Sources are the foundation of every Clay table — they determine how data flows in. Every table starts with a source: CSV import, CRM connection, webhook, list builder, or signal feed. Sources are your gateway to organizing and managing data in Clay.

## Adding Sources

**New table:**
1. Click `+ Add` at the bottom of a workbook
2. Search for and select a data source (Salesforce, Find People, etc.)
3. Configure settings, review preview, click `Import to new table`

**Existing table:**
1. In a table, click `Tools` > `Import`
2. Search for and select your desired source
3. Configure settings, review preview, click `Import`

**CSV import:**
- New table: `+ Add` > `Import from CSV` > select file > `Complete import`
- Existing table: `Tools` > `Import` > `Import from CSV` > map columns > `Add to table`

## Row Limits

Clay tables have a **50,000-row limit** across all plans. This applies to all source types.

| Source | Row Limit |
|--------|----------|
| Salesforce Reports | 2,000 (API restriction) |
| Salesforce List Views | 50,000 |
| All other sources | 50,000 |

When you hit the limit, Clay imports up to the cap and stops automatically. No error message is displayed.

### Solutions for Large Datasets

- **Split by filters or date ranges** — create multiple tables with non-overlapping criteria
- **Auto-delete** (Enterprise) — enables unlimited row processing by deleting rows after they pass through the pipeline
- **Bulk enrichment** (Enterprise) — process millions of records outside the table row limit

## Source Behavior

### Editing Sources

**Editing a source after it's been run does not retroactively update the table.** Even if the source preview shows updated filters, the table won't refresh until you re-run the step. To apply updated filters:
- Delete and re-run the source step, or
- Duplicate the table with the updated source

### Modifying & Deleting

- **Modify:** Click source column title > Sources > source name > Edit source
- **Delete:** Click source column title > Sources > source name > Delete source

### Scheduled Sources

Sources can be scheduled to run automatically, keeping data up to date without manual intervention. This is one of Clay's most powerful features for maintaining always-on workflows. Works particularly well with [[clay-audiences]] for persistent pipelines.

## Enrichment Recipes (Enterprise)

Recipes are pre-built, reusable combinations of enrichments you can save and apply across tables. Enterprise only.

**Create a recipe:**
1. Hold `Ctrl`/`Cmd` and select the columns to include
2. Right-click > `Create Recipe`
3. Name, describe, and define inputs
4. Save

**Use a recipe:**
1. `Add enrichment` > top menu > `Recipes`
2. Select the recipe
3. Map inputs, save, and run

Recipes save time when you have standard enrichment sequences (e.g., email waterfall + verification + scoring) that you run on every new table.

## See Also

- [[clay-webhooks]] — real-time data ingestion via webhooks (alternative to scheduled sources)
- [[clay-audiences]] — persistent data layer that uses sources for always-on workflows
- [[clay-hubspot-integration]] — CRM as a source for import and enrichment
- [[clay-salesforce-integration]] — Salesforce-specific source considerations
- [[fete-framework]] — sources as the "Find" step in Find-Enrich-Transform-Export
