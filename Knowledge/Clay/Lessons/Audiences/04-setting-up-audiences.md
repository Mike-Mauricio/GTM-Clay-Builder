---
title: "Setting Up Audiences: Add and Export Data [Audiences]"
source: "https://university.clay.com/lessons/setting-up-audiences"
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

![](https://www.youtube.com/watch?v=WtL0BVV3STA)

About this lesson

00:00

## Setting Up Audiences: Add and Export Data

To get any value out of Audiences, your data has to live in it first.

This lesson connects your CRM and other sources to Audiences, maps your fields, and sets how data flows in and back out. It's mostly a series of decisions you make once that shape everything downstream, in two directions: pulling data in, and writing it back out.

## 📥 Get Your Data In First

Everything here happens in one place. In Audiences, click **Add Data**, and Clay takes you to **Settings → Sources / Destinations**, where your imports and exports live side by side. You'll come back to this page often.

## ✅ Before You Start

Three things to have ready before you connect a source:

- **A Clay workspace with Audiences enabled.**
- **Salesforce admin credentials** to authorize the connection.
- **The objects you want to work with:** Accounts, Contacts, Leads, and Opportunities.

## 🔗 Connecting Salesforce: Four Object Toggles

When you connect Salesforce, you'll see four toggles, all off on a fresh account. Here's what each one brings in:

- **Accounts:** all of your Salesforce accounts.
- **Contacts:** your converted leads, someone who's qualified into an actual contact, not somebody you're still chasing.
- **Leads:** your Salesforce leads.
- **Opportunities:** the deals you're pursuing at a company, tracked separately by buying motion. Leads and contacts map one-to-one, but opportunities and accounts are many-to-one: if you were selling to Google, you might have separate opportunities for Google Cloud, Google Platform, and Google Education, all tied back to the same account. Importing opportunities gives you that fidelity into your funnel.

**Turn all four on.** The more data you bring in, the more your enrichments, rep tools, and agents can do. The only real reason to hold back is compliance. Volume isn't the concern: imports are batched, thousands of records at a time, so they barely touch your Salesforce API limit.

## 🔁 Import Sync vs. Import Record Matching

Two settings sound alike but do different things.

- **Import sync** is the on switch: it turns the import on and keeps a live connection between Clay and Salesforce.
- **Import record matching** merges the *same* record coming from two different sources. Say a person is a contact in Salesforce and also shows up in Snowflake carrying product-usage data (they're a user, they hit the paywall, they're an admin). Record matching combines those into one record. You pick a unique key to match on, such as **domain**, and Clay uses it to know they're the same person.

Record matching is optional but highly recommended, especially once you have more than one source feeding in, because it preserves the sanctity of your data wherever duplicates would otherwise appear.

## 🗺️ Field Mapping

Field mapping is where you choose which Salesforce fields come into Clay.

One nuance to know up front: **Leads and Opportunities are import-only for now.** You can decide which fields to bring in, but to push them back out you go through a bulk enrich rather than a direct export.

## 🛡️ Overwrite Rules

When Clay and Salesforce both hold a value for the same field, overwrite rules decide who wins. You get three options:

- **Always Overwrite:** Clay's data takes precedence.
- **Never Overwrite:** your Salesforce values are protected.
- **Fill Blank Fields Only:** Clay only writes into fields that are empty in Salesforce.

Start with **Never** or **Fill Blank Fields Only**. Always Overwrite can replace CRM data your team has carefully maintained, so start conservative and loosen up once you trust Clay's data quality. If a setting confuses you, test it on a couple of records, watch how it behaves, then move forward.

## 🗄️ Archiving Records

Need to pull records out of an audience without deleting them? Click the **triple-dot menu** on an audience segment and **archive** the records: they'll stop showing up in your audiences. **Unarchive** them anytime to bring them back.

## 📤 Sending Data Back to Salesforce

That covers pulling data in. The other direction is writing it back.

- **Export sync** sends data from Clay back to Salesforce, merging it into your existing records.
- **Create new Salesforce records** writes Clay-built records (from a table, a CSV, anywhere) back to Salesforce even if they didn't exist there before. It works through a Salesforce field mapped to the **Clay ID**, so Clay always knows what it's already written and doesn't create duplicates.

In the demo, export sync stays off so we don't push test data into a real CRM. Turning it on is a single toggle.

## ⚙️ Configuring Sync

Your first sync brings everything in. After that, **syncs are incremental: Clay only processes the records that changed since last time**, in batches of a few thousand. If you're a big Salesforce org, expect that first sync to take a while; after that it's quick, and duplicate matching happens automatically.

This is the real reason to use the native connection. A standard Clay table import hits Salesforce with full API calls on every sync. The Audiences connection only processes changes, so it's far lighter on your API limit. If your Salesforce admin has ever flagged API usage, this architecture is the fix.

## 🔌 Other Sources

Salesforce is the main event, but Audiences connects to other sources the same way:

- **Snowflake:** pick a database, then a schema, then a warehouse, then query it directly with **SQL**. The results show up as Audiences data you can map in. If you're not comfortable writing the query, your data team can help.
- **HubSpot, Gong, BigQuery:** native integrations, set up with the same rules on screen.
- **CSV:** name the source, upload your file, preview it, and confirm.

## 🔎 Adding Net-New People and Companies

Your CRM and warehouse set the foundation, but you'll also want to add net-new people and companies on top, to expand your TAM and go after more accounts. This works just like search already does in Clay, with one big upgrade: Audiences dedupes the results against your existing data automatically.

1. **Run a search.** From Find People or Find Companies, describe what you want in plain language, for example "New York based software companies with 51 to 200 employees." Sculptor turns that prompt into a deterministic, editable filter, so you stay in control. It may overshoot a boundary, pulling in a 201-employee company on a "51 to 200" search, so just remove what you don't want.
2. **Refine until the universe is right.** Adjust the filters and watch the count update. After re-adding a New York location filter, the example lands at **2,792 companies**.
3. **Save it to your audience.** Click **Continue** and choose where the results go: a new workbook and table, an existing table, or, most importantly, your **companies audience**. Saving to the audience automatically **excludes results already in it**.
4. **Let Audiences dedupe.** Before anything moves, the results sit in a draft while Audiences cleans, sorts, and matches them against your existing audience, so you never push duplicate records.

## 🚀 What's Next

Your sources are connected, your fields are mapped, your import and export rules are set, and you can pull net-new people and companies in on top, with Audiences deduping them against what you already have. Data is flowing into Audiences and back out to your CRM.

Next, we'll step back to what Audiences actually is and the framework for thinking about it, before we start actioning your data with enrichments.

Related resources

http://university.clay.com/docs/audiences

Next up