---
title: "Guide: Ways to save Clay credits"
source: "https://university.clay.com/docs/clay-credit-conservation"
author:
published:
created: 2026-07-14
description: "Make the most out of your Clay credits."
tags:
  - "clippings"
---
Overview

Clay credits are valuable resources that help you save both time by automating manual work and money on go-to-market resources. By optimizing how you use credits, you can ensure your workflows remain efficient while delivering the results you need growth. This guide outlines a few best practices to help you get the most out of your credits.

## Pause enrichments for new entries by turning off auto-update

**How does this save credits?**

Auto-update allows Clay to enrich any new rows added to your table automatically. While this can be helpful when your table is set up for a fully automated workflow, it can also result in unnecessary credit usage if rows are added by mistake or before you’re ready.

The best practice here is to **turn off auto-update** while building your table. Once your setup is finalized, you can turn it back on when you’re ready to launch and start enriching new entries.

**How do you implement this?**

To turn off auto-update for a column, go to **Run Settings** and toggle off the Auto-Update button.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f0082e_674e814edd898a9e4c23a583_67182796c58ecf6a84a49a9d_67180d01969ef81c792b7b63_CleanShot%252525202024-10-21%25252520at%2525252023.33.36%252525402x.avif)

You can also “turn off” an entire table from auto-updating by clicking the three little dots next to your table name, then click on “Auto-Update Columns”.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4568542415e81f0083a_674e814edd898a9e4c23a586_67182796c58ecf6a84a49aa3_67180d17b684eeb70008cf4e_CleanShot%252525202024-10-21%25252520at%2525252023.32.50%252525402x.avif)

## Leveraging your API Keys

**How does this save credits?**

If you are on a paid plan and have credits with other data providers, Clay allows you to integrate your own API keys, giving you the flexibility to use those resources directly within your workflows.

**How do you use your own API key?**

You can access adding your API key two ways:

1. Profile picture > Settings > Navigation Bar
2. Go to your profile picture in the top right corner, navigate to Settings, and head over to the Connections section. From there, you can add your API keys to the Clay panel.
3. Enrichment Panel > Account > Add Account
4. When setting up an enrichment that accepts an API key, you can add an account linked to your API key. By default, Clay’s API key will be selected, but if you want to use your own, simply switch to your account by selecting **Add Account**.

Some common API keys you can swap out:

- **OpenAI API keys**
- **Anthropic**
- **Apollo** (*Make sure to use the correct API key for the specific service you are integrating)*
- **Email Providers** (e.g., Findymail, Prospeo)
- **Email Verifiers** (e.g., Debounce, NeverBounce)
![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f00828_674e814edd898a9e4c23a58c_67182796c58ecf6a84a49a93_67180d666ad244cd09467c9e_CleanShot%252525202024-10-21%25252520at%2525252023.36.50%252525402x.avif)

You can add your own API keys when you select the account your enrichment runs on (Paid Feature)

## Qualify leads before enriching

**How does this help conserve credits?**

By adjusting the order of enrichments, you can save credits by enriching only the leads that meet specific criteria. If you have leads that can be disqualified early in the process, filtering them out ensures that only qualified contacts are enriched, preventing unnecessary credit usage.

**How do you implement this?**

You can set up **conditional runs** or use **AI formulas** to filter rows based on specific criteria (e.g., location, company size, or industry) to enrich only the contacts that are most relevant to your criteria.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f0082b_674e814edd898a9e4c23a5ad_67182796c58ecf6a84a49aa0_67180f3d602119d53cca96c2_CleanShot%252525202024-10-21%25252520at%2525252023.40.12%252525402x.avif)

Here is an example of a way to use AI formulas to filter out leads

## Test out your data

**How does this save credits?**

When using a new integration, it’s best to start by testing a small sample—about 10 rows—before running the entire column. This allows you to identify and fix any errors in advance (ex. import errors, column filter error)

For AI enrichments, prompts may need several iterations to get right, so testing and refining your prompts before running the full enrichment will help ensure better results.

**How do you implement this?**

Before running an enrichment, you can test it on 10 rows or apply it to the entire column. This gives you flexibility in troubleshooting and improving your setup before committing fully.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f00837_674e814edd898a9e4c23a5a4_67182796c58ecf6a84a49a9a_671825f00da5388030b99334_CleanShot%252525202024-10-21%25252520at%2525252023.29.42%252525402x.avif)

## Conditional runs

**How does this save credits?**

Conditional formulas help you conserve credits by ensuring that enrichments only run when specific conditions are met. Instead of enriching every row, you can create rules that limit enrichments to only the most relevant rows, such as leads that meet certain criteria. This prevents unnecessary enrichments on disqualified or low-priority leads, allowing you to use credits more efficiently.

**How do you implement this?**

There are two ways to implement conditional runs:

**Method #1: Conditional Runs**

1. Go to the **Run Settings** of any enrichment column.
2. In the **“Only run if”** box, add your conditional formula to specify when the enrichment should run.
3. **Tip:** Use the **“Use AI”** button to input plain language instructions, making it easier to define your conditions without needing complex formulas.
![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f00831_674e814edd898a9e4c23a5a1_67182796c58ecf6a84a49a97_67182609898b1c3a97094d2a_CleanShot%252525202024-10-21%25252520at%2525252023.30.49%252525402x.avif)

**Method #2: Filter Existing Rows**

You can also conditionally run columns through filtering rows.

Filtered views only enriches the rows you're viewing so this can be used as a way to run enrichments conditionally

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/6920f4558542415e81f00834_674e814edd898a9e4c23a589_67182795c58ecf6a84a49a87_67182615ea07206bf07a513f_CleanShot%252525202024-10-22%25252520at%2525252011.09.01%252525402x.avif)

## Look up existing data to avoid duplicate enrichments

If you’ve already enriched contacts in another table or your CRM, you can use **Lookup** columns to pull that existing data, saving credits by avoiding duplicate enrichments. Before running a new enrichment, check if the data already exists in your CRM or another Clay table. If it does, use a Lookup column to pull the data into your current table.

**How do you implement this?**

1) Pull Data from Your CRM  

<iframe src="https://www.loom.com/embed/f8c011b41b154913bd925d17ea025b6e?sid=809d1b7f-d22b-4bc9-a555-7857c563d82d" frameborder="0" allowfullscreen=""></iframe>

  
2) Leverage Data from Other Tables  

<iframe src="https://www.loom.com/embed/ec99734367fb486db763c0d0400468d5?sid=1d0d6724-9080-457c-bb58-e81ff1757cc2" frameborder="0" allowfullscreen=""></iframe>