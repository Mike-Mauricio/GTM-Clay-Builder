---
title: "Audiences, Workbooks, and Tables Explained [Audiences]"
source: "https://university.clay.com/lessons/audiences-workbooks-and-tables-explained"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Audiences

Learn how RevOps teams use Clay Audiences to build a unified data layer so you can sync your CRM, create dynamic segments, and activate your data at enterprise scale.

Progress

<iframe src="https://www.loom.com/embed/4b0bae0d618a43a5905726c340b5021f?hide_owner=true&amp;hide_share=true&amp;hide_title=true&amp;hideEmbedTopBar=true" frameborder="0" allowfullscreen=""></iframe>

About this lesson

00:00

## Audiences, Workbooks, and Tables Explained

Here's a question almost everyone hits: when do I use an Audience, and when do I use a Workbook or a Table? The confusion is understandable, because the enrich action inside an Audience shows the same familiar table view you see in a Workbook. But because Audiences operate at a completely different scale, what you use them for is different too.

## 🧭 The Quick Answer

Match the job to the surface. This table is the decision matrix in short form:

| Need | Build where | Why |
| --- | --- | --- |
| Segment millions of CRM records | Audiences | Scale, dynamic filters, source of truth |
| Enrich a segment and store the results durably | Audiences → Bulk Enrichment | Avoids re-enrichment and keeps your GTM data centralized |
| Build a multi-step workflow, then filter and search rows | Audiences → Bulk Enrich → Table | Tables are the orchestration primitive today; Bulk Enrich is the bridge |
| Take a final outbound or CRM action | Audiences | Simple actions can stay in Audiences; complex ones go through Tables |
| Keep Salesforce updated over time | Export Sync | Ongoing writeback belongs in a sync, not a one-off Workbook export |

The single constraint behind most of this: a Clay **Table caps at 50,000 rows**. Anything larger, including any "millions of records" segmentation, belongs in an Audience.

## 🔬 Audiences Are Production, Tables Are the Laboratory

The cleanest way to hold the difference in your head:

- **Audiences are for scale and for the source of truth.** Segment millions of records, store permanent information (firmographic, demographic, or custom research you already know works) with a bulk enrichment, take simple final actions like sending to a sequencer or Slack, and keep your CRM current through an export sync. Static, reliable fields like **domain**, **location**, and **lookalike group** are perfect to enrich at the Audience level.
- **Tables are your testing ground.** This is where you iterate, form a hypothesis, and test it, especially for multi-step flows with lots of conditional runs orchestrating actions across columns. You rarely want to do that experimentation at 50,000-row scale.

**Experiment in a Table, then graduate to scale in an Audience.** Once you've figured out your data structure, you shouldn't need to wire columns together with conditional runs. You should be able to segment at the company or people level and run one enrichment. Done right, moving to scale makes things simpler, not more complex.

## 🔁 Connecting the Two

Your Audiences and your Tables share one unified data layer, so data flows both ways. Open the **tools** menu in a Table and search "audience" to find **four audience enrichments**: you can pull in audience data the same way you pull from a CRM, update audience records, and upsert into an Audience.

### Table → Audience (Upsert)

When you've tested something in a Table and you're confident in it, push it back to your Audience.

1. **Open tools and choose the upsert into Audiences enrichment**, then pick the Companies (or People) audience.
2. **Set your lookup fields** to match on **domain** and/or **LinkedIn URL**, so you don't create duplicates.
3. **Map the fields to update**, for example name and industry.
4. **Save and run a small batch first** (10 rows) to confirm it works before running the whole table.

The matched records land in your Audience. Filter the Audience and you'll find the rows you just sent, with their fields populated.

### Audience → Table (Send to Table)

Going the other way lets you pull a slice of an Audience into a Table for more experimental work.

1. **In the Audience segment, open Enrichments and add a bulk enrich.** You can run any enrichment here first, for example an AI function that summarizes each company record.
2. **Add a Send to Table action.**
3. **Pick an existing Table or create a new one.** Creating a new Table is the more common choice when moving from an Audience to a Table.
4. **Map which results to send**, keep **update existing rows** and **auto-extract new columns** on, and **run 10 rows** as a test before deploying to the full audience (here, roughly 7,000 companies).

Your audience data appears in the Table, ready to work on.

## ⚠️ Two Things That Trip People Up

- **Send to Table does not send all visible data by default.** You have to select which row data goes across, a deliberate choice for the sake of speed and complexity. Don't assume everything you see came along.
- **Always test on a small batch first.** Both directions are best run on 10 rows before you commit the full audience. The small run is your safety check.

Put it together and the default rules are simple:

- Data you know is secure, stable, and reliable: run it in the Audience.
- An experiment, a hypothesis, a Claygent scrape you're unsure about, or a multi-column conditional flow: test it in a Table first, then deploy it back.

## 🚀 What's Next

You now know which surface fits which job: Audiences for scale and the source of truth, Tables for experimentation and multi-step orchestration, and the upsert and send-to-table bridges that connect them.

Next, put it into practice with the use-case lessons, where these same moves power [CRM enrichment](https://university.clay.com/lessons/use-case-1-crm-enrichment), [TAM sourcing](https://university.clay.com/lessons/use-case-2-tam-sourcing), [signal-based plays](https://university.clay.com/lessons/use-case-3-signal-based-plays), and [AI outbound](https://university.clay.com/lessons/use-case-4-ai-outbound) at full audience scale.