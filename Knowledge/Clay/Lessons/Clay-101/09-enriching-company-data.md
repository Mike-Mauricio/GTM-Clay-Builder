---
title: "Enriching Company Data [Clay 101: GTM Automation]"
source: "https://university.clay.com/lessons/enriching-company-data"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=iRO7PtE7ga4)

About this lesson

00:00

## Enriching Company Data

Company enrichment is where you add the context and depth that transforms basic company identifiers into actionable intelligence.

In this lesson, we'll show you how to enrich companies with key firmographic and technographic details using Clay's waterfall enrichment system.

## 📋 Before Getting Started with Enriching Companies

Here's what you should have:

- A company list with domain names and social media profile URLs. If you followed our previous lesson on Finding Companies, you should already have this.
- Understanding of the Jigsaw framework for enrichment strategy. Remember, these company identifiers are your "corner pieces" that enable all other enrichment.
- Finally, you should know your end goals for the data. Are you qualifying leads for outbound? Doing market research? Building account intelligence? Your goals will guide your enrichment strategy.

## 🌊 Understanding Clay's Waterfalls

A waterfall is Clay's data enrichment method. By using a waterfall, you can pull data from multiple providers, in a specific order. That way, you don't need to do multiple manual uploads, or run multiple lookups across different providers.

Before waterfalls, revenue teams had to manage a bunch of expensive subscriptions to multiple data providers, and manually filter results through spreadsheets. This was time-consuming, expensive, and often led to incomplete data.

Clay waterfalls automate this process! By using a waterfall, you'll be querying providers in a specific order—usually starting with the most cost-effective—until the required data is found.

Once Clay finds what it needs from one provider, it won't check the others. This helps save your credits and keeps things running smoothly.

Let's look at a specific example: enriching for funding stage. Here’s a hypothetical waterfall Clay might go through:

- Check IntelliSense first at 1 credit
- Then PitchBook at 3 credits
- Then DealRoom at 4 credits, and so on

As soon as one provider finds the funding stage data, the waterfall stops.

This approach helps you get the best balance of accuracy, completeness, and cost savings.

## 🛠️ Step-by-Step: Enriching Companies with Waterfalls

Let's walk through enriching companies with waterfalls using "funding stage" as our example:

- First, open the Enrichment Panel by clicking the "Add enrichment" button, then search for "Funding Stage" in the list of available enrichments.
- Next, you'll configure your waterfall. You'll see a pre-arranged order of providers, optimized for cost and coverage. Clay comes with these waterfalls pre-configured based on our experience with hundreds of thousands of enrichments.
- If you have specific preferences—for example, if you know a certain provider has better coverage for your ICP—you can reorder the providers accordingly. The key is optimizing for the right balance of cost versus coverage for your specific use case.
- Now you'll select the input column. The only required input for funding stage enrichment is Company Domain. If Clay hasn't automatically detected the correct column, manually select it from the dropdown list.
- Before running on your full dataset, always test on small batches. Click "Save & Run (10 Rows)" to start the enrichment process on just 10 rows first. This lets you verify the quality and accuracy before scaling.
- Once the enrichment process starts, Clay will move through the waterfall sequence dynamically. If IntelliSense finds funding stage data, it stops there. If IntelliSense fails, Clay moves to PitchBook and continues down the waterfall until it finds a valid result or exhausts all providers.
- After reviewing your test results and confirming they look good, you can scale to your full dataset.

## 🎯 Which Enrichment Is Most Valuable for Company Data?

It depends on which data points will help you achieve your goals.

Remember: more data isn't always better. You want to be strategic about which enrichments you run.

For firmographic data, consider enrichments like funding and investment details, revenue estimates, industry classification, and headquarters location. These help you understand the size, stage, and basic characteristics of your target companies.

For technographic data, look at tech stack enrichment, software usage detection, and integration points. This is particularly valuable if you're selling to technical teams or if your product integrates with specific tools.

For growth indicators, consider enrichments around hiring patterns, website traffic trends, and social media presence. These signals can help you identify companies that are scaling or facing specific challenges.

## 🚀 Advanced Strategies

As you get more comfortable with basic waterfall enrichments, you can explore more advanced strategies:

You can combine different data points to:

- Build a complete picture of each company
- Customize which data providers you want to use and in what order
- Set up conditional runs so enrichments only run when needed, helping you optimize your credits

We'll dive deeper into these advanced techniques in future lessons, but it's good to know they're available as you grow your Clay skills.

## ✅ Conclusion

That's a wrap on waterfall enrichment for companies! You now know how to use waterfalls to ensure your company lists have the best available data.

In our next lesson, we'll explore how to enrich people with validated work emails and other contact details, also using waterfall techniques.

This is where your outreach strategy really starts to come together.

Let's keep going.

Next up