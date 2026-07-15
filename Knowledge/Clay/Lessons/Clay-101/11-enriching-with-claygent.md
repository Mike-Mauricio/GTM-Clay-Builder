---
title: "Enriching with Claygent [Clay 101: GTM Automation]"
source: "https://university.clay.com/lessons/enriching-with-claygent"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=Aa8CyIH9jSY)

About this lesson

00:00

## Enriching with Claygent

Welcome to our lesson on Claygent, Clay's AI web scraper! Claygent is one of the most powerful tools in Clay for enrichment because it can pull real-time, dynamic context directly from the web.

Unlike traditional enrichment providers that return static database results, Claygent acts like a virtual research assistant that browses websites, reads pages, and returns insights at scale. This makes it perfect for solving what we call the "last mile data problem."

In this lesson, we'll show you how to use Claygent to enrich both companies and people with data that you simply can't find anywhere else.

## 🔍 Understanding the Last Mile Data Problem

With Clay waterfalls, you already have a huge advantage when it comes to enrichment. When you're intelligently gathering data from 120+ providers instead of a few pieced together sources, data coverage goes up to 80-95%.

But even with the perfect waterfall setup—with every provider firing—you'll still run into a last mile data problem.

Last-mile data is the custom data that's important to your ICP and process, but too niche for a data provider to collect. For example:

- Whether a local dentist offers Invisalign
- If a founder spoke at a panel last month
- What a company's website says about pricing or features

No wonder the average SDR spends 80% of their time on data entry and manual research.

With Claygent, you can automate this last step of research and focus on what really matters—connecting with prospects.

## 📋 Requirements for Claygent Enrichment

Before you can start enriching with Claygent, here's what you need:

For Company Enrichment, you'll need:

- A company domain
- You'll also want: Linkedin company profile URL, category tags, or segments (optional but helpful)

For People Enrichment, you'll need:

- A Linkedin profile URL
- And you'll also want first and last name as fallback, and company name and title to add context to your prompts (again, optional but helpful)

## 🏢 Step-by-Step: Enriching Company Data with Claygent

Let's walk through enriching company data with Claygent using a simple example:

- Start with a table that includes company domains. Click "Add column" then select "Claygent" from the enrichment options.
- Now you'll write your prompt. You can write your own or click "Help me" to use the Meta prompter for faster, better prompts.
- Let's say we want to know if companies offer a free trial. Here's an example prompt: "Visit this company's homepage. Does it offer a free trial? Return 'Yes' if they mention free trial, demo, or trial period. Return 'No' if no trial is mentioned."
- Map your domain field in the "URL" input so Claygent knows which websites to visit.
- Choose the appropriate Claygent model. Use 1-credit for simple questions, 2-credit for moderate complexity, and 3-credit for complex analysis.
- Click Save and run Claygent. Start with 10 rows to test your prompt before scaling to your full dataset.
- Review the results. You can optionally add confidence or reasoning columns to understand how Claygent reached its conclusions.

Common company enrichment use cases include:

- Is this company B2B or B2C?
- Do they offer integrations with specific tools?
- What's their primary value proposition?
- Do they mention specific technologies on their website?

## 💡 Tips for Using Claygent

Here are some tips for using Claygent:

First, you should use Claygent when the data doesn't exist in databases, when you need real-time context, or when you're looking for highly specific, nuanced information.

Second, for writing effective prompts, use second person language like "Visit this person's website and..." Provide fallback logic like "If they haven't posted recently, summarize their About section." And add token-saving instructions like "Keep output under 50 words."

Finally, choose your model based on complexity. Simple yes/no questions work well with 1-credit models, while complex analysis requiring multiple data points might need 3-credit models.

## 🎯 Conclusion

That's a wrap on enriching with Claygent! You now know how to use Clay's AI web scraper to find company and people data that doesn't exist in traditional databases.

Claygent is your tool for creating GTM alpha through unique data that your competitors simply can't access. Whether you're finding niche company attributes or personal insights for outreach, Claygent bridges the last mile between standard enrichment and truly personalized intelligence.

In our next lesson, we'll move into the Transform phase of FETE, where we'll show you how to clean, format, and structure all the data you've gathered for maximum impact.

Let's keep going.

Next up