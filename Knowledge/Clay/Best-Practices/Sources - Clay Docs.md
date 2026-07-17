---
title: "Sources - Clay Docs"
source: "https://university.clay.com/docs/sources"
author:
published:
created: 2026-07-14
description: "Every Clay table begins with a source. Sources are the foundation of how data gets into your tables."
tags:
  - "clippings"
---
Overview

Sources are the foundation of Clay and determine how data flows into your table—think of them as the roots of a tree feeding information into your database. Just like a tree needs strong roots to grow and thrive, every Clay table needs well-configured sources to function effectively.

Every Clay table starts with a source. You can import customer data from a CSV file, connect to your CRM system, or receive real-time updates through webhooks. Sources are your gateway to organizing and managing data in Clay.

## Adding sources to table

**Add to a new table:**

1. Click `+ Add` at the bottom of a workbook to create a new table.
2. Search for and select your desired data source (such as Salesforce or Find People).
3. Configure the source settings.
4. Review the preview and click `Import to new table`.

**Add to an existing table:**

1. In a table, click `Tools` → `Import`.
2. Search for and select your desired data source (such as Salesforce or Find People).
3. Configure the source settings.
4. Review the preview and click `Import`.

### Importing CSV

**To import a CSV file into a new table:**

1. Click `+ Add` at the bottom of a workbook to create a new table.
2. Click `Import from CSV` and select your file.
3. Click `Complete import`.

**To import to an existing table:**

1. In a table, click `Tools` → `Import`.
2. Click `Import from CSV` and select your file.
3. Select and map columns from your CSV to the Clay table.
4. Click `Add to table`.

## Modifying sources

1. In a table, click the source column title.
2. Click `Sources` and the name of the source.
3. Click `Edit source` and adjust the settings as needed.

## Deleting sources

1. In a table, click the source column title.
2. Click `Sources` and the name of the source.
3. Click `Delete source`.

## Scheduled sources

Scheduling source runs is one of the most powerful features, as it keeps your information automatically up to date. To learn more, check out [scheduled sources](https://www.clay.com/university/guide/scheduled-sources).

## FAQs

### Why doesn't my Clay table update when I change the source filters?

**Editing the source of a Clay table after it's been run won't retroactively update the results, because Clay doesn't reprocess previously generated data automatically.**

Even if the source preview shows the new filters, the table won't refresh until you re-run the step that generated the data. To see the updated results, either delete and re-run the step or duplicate the table with the updated source.

### What are the row limits for Clay tables and sources?

Clay tables have a **50,000-row limit** across all plans. This applies to all sources including CSV files, CRM systems, list builders, webhooks, and signals.

**Source-specific limits:**

- **Salesforce Reports**: 2,000 records (API restriction)
- **Salesforce List Views**: 50,000 records
- **All other sources**: 50,000 records

**What happens when you hit the limit?**

Clay imports records up to the limit and stops automatically. No error message is displayed.

**Solutions for large datasets:**

- Split your data using filters or date ranges into multiple tables
- Use [auto-delete](https://university.clay.com/docs/table-management-settings#auto-delete-passthrough-tables) (Enterprise plan) for unlimited rows
- Use [bulk enrichment](https://www.clay.com/university/guide/bulk-enrichment) (Enterprise plan) to process millions of records