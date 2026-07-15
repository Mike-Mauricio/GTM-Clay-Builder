---
title: "Your Inbound Enrichment Stack [Automated Inbound]"
source: "https://university.clay.com/lessons/your-enrichment-stack-inbound-automation"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Automated Inbound

Learn how to automatically enrich, score, and follow-up with inbound leads with Clay's inbound automation engine for lightning-fast speed-to-lead.

Progress

![](https://www.youtube.com/watch?v=bWly54DRu84)

About this lesson

00:00

## Your Inbound Enrichment Stack

## 🔎 Smart Inbound Lead Enrichment: From Basic Info to Sales Intelligence

Today, we're diving into the enrichment step of your inbound engine—the process that transforms basic lead information into comprehensive prospect intelligence.

Enrichment is the difference between knowing a lead's name and knowing whether that lead is worthy of a rep's full attention right now.

In this lesson, we’ll break down how to enrich smarter and efficiently, showing you how to think creatively strategically about what really matters for your team.

## 📄 Why Shorter Forms Win in Inbound

The unique thing about inbound is that you get to decide how much to ask customers upfront. Spoiler alert: less is more.

While more fields allow you to collect more customer data, the longer the form, the higher the friction is for leads. [Research shows that just adding two extra form fields - from 3 to 5 - slashes average completing rates by nearly one half.](https://capturly.com/blog/design-effective-forms-to-increase-conversion-rates/)

Before Clay, there was an inescapable trade-off between form length and lead quality. Shorter forms led to better conversions but left reps scrambling to manually research basic information on leads just to qualify them. With longer lead forms, companies sought to pre-qualify leads in an attempt to minimize manual research. It’s why so many B2B software demo forms still ask questions like “What is your company size?”

With Clay, you don’t need to ask those questions anymore. You can have the best of both worlds: short forms that maximize conversions and minimize speed to lead, without sacrificing the data you need for context-rich follow-up.

In a post-Clay world, your inbound forms really only need to ask for one or two critical pieces of info:

1. **Name**
2. **Email address or LinkedIn profile URL**

From just those data points, we can easily enrich our way to personal info like job title, years of experience, educational background, as well as company data like headcount, industry, description, tech stack, and anything else you might want to learn about.

It’s same Jigsaw framework we discussed in Clay 101: we always want to start with those corner pieces before filling in the center.

## 🧠 Thinking Strategically about Inbound Enrichment

Another key difference between enriching inbound leads versus outbound is how you prioritize what data to gather.

With outbound, you often want a broad, complete picture of potential prospects in order to identify new targets. With inbound, that script flips: you’re working backwards from bare minimum data points, figuring out just how much data you need to confidently score and prioritize leads while maximizing speed to lead.

To put it simply, it’s not about collecting every possible data point— it’s about doubling down on the essential signals that tell you whether or not a lead is worth immediate action. With Clay, you can get incredibly creative about what firmographic, demographic, and behavioral traits represent best fit custom data signals for your company.

If you don’t know where to start, you can start by asking: *What traits and behaviors do we see consistently in our best customers?*

At Clay, we know that some key data points for our own segmentation and scoring strategy are company size, which determines which internal team at Clay handles the lead, the lead’s seniority and title, which helps us know whether we’re speaking with a key decision maker, and industry - we tend to sell well to software companies because they usually have RevOps and marketing leaders who are comfortable working with tools like Clay and more open to experimentation.

By defining these key must-have signals, we make sure that our enrichment process is focused and directly tied to our revenue motion.

## 🚿 Waterfall Enrichments: Company Enrichment

Once you’ve enriched a lead with a company identifier, the Enrich Company enrichment automatically finds detailed firmographic info that can help you assess ICP fit and spot buyer intent.

### 📬 Open Jobs

Beyond broad firmographics, Clay allows you to fill in far more context. One thing reps might want to do is to find a company’s headcount growth in sales and marketing as well as any open jobs in that function. This helps offer a snapshot of the current scale of their GTM org, how mature their sales motion is, and whether they’re in the process of scaling their outbound or revenue operations. A company that’s doubled its sales team within the past year is far more likely to invest in new tools to keep up with that growth.

Finding open jobs is super straightforward:

Go to Actions, Enrichments, then “Find Active Job Openings.” The only required input is a company identifier, namely the company LinkedIn URL or domain. From there, you can put in any criteria you want, i.e. the keywords sales and marketing because that’s what we’re interested in here.

### 📈 Headcount Growth

Headcount growth is a little more involved but entirely manageable once you have the right approach. If you click on Add Enrichment and search headcount, Clay has a pre-built enrichment that let’s you find company headcount by criteria. If we want to find growth over a set period, formulas become very useful. In this example, the first step would be to find the current headcount on the sales and marketing team. Then, you can create another column with the exact same enrichment and just change the “Maximum number of months since start date of current role” to reflect the time frame you want to track change over. The last step is to create one more column, this time a formula. If you want to find the percentage change, you can just type that in here, mapping to the numerical output generated in the two previous columns.

### 👩🏻💻 Tech Usage

Another enrichment that might be super useful is finding out whether your lead’s company currently uses a specific tech tool. If it’s something your product integrates with or one that your existing customers tend to use frequently, that lead could be a great fit.

We recommend using HG Insights’ Verify Product Usage enrichment here. You can either use your own account or Clay’s, then map the company domain as an input. After that, you can type in the specific products or product attributes you’re looking for and then run the enrichment. With HG Insights, you can go beyond just “Salesforce” and get very granula into specific Salesforce tools, i.e. CRM, Marketing Cloud, Sales Cloud, etc.

### 🎨 Claygent: Creative enrichments

Using Claygent, you can fill in company data even further. The sky’s the limit! Some examples of company enrichments we’ve seen done in Clay:

- Check SOC-II compliance status
- Monitor for pricing changes or new pricing tiers
- Track news on product feature launches
- Find the topic of their most recent blog posts
- Track customer review sentiment across platforms

## 🌲The Clay decision tree: When to Use Native Enrichments vs. AI & Claygent

Figuring out when to use native enrichments versus AI formulas or Claygent comes down to the type of data you’re looking for.

Native enrichments in Clay are a quick and reliable way to capture standard variables like firmographic or demographic attributes, such as company size, location, or headcount.

If you want to combine columns or extract specific insights from existing data in your table, considering using an AI formula.

If native enrichments and formulas aren’t able to find what you’re looking for, Claygent is great for when you’re dealing with nuanced, specific, or varied data points and sources. Think of things like:

- Industry classifications: Often times, industry category descriptions aren’t nearly granular enough to capture what a company actually does. For example, Nike is categorized as “Retail,” rather than “Apparel” or “Athletic Wear.” Claygent can help scrape web sources to classify companies based on specific language in their descriptions or online mentions.
- Job Titles: Titles might not accurately describe what a person actually does or their role seniority, potentially leading to inaccurate lead scoring and routing.
- Data that exists in niche data sources like specific website pages, blogs, or social media

A good rule of thumb is to start by trying to find your data point using Clay’s existing native enrichment providers. If you can’t find what you’re looking for, that’s when you should turn to Claygent to find that last-mile data and extract precise, highly tailored insights.

Enrichments start by solidifying the corners and building the edges of your puzzle. Claygent goes even further by allowing you to fill in valuable context around your leads that goes far beyond basic firmographics.

Enrichment isn’t just about collecting as much data as possible. It’s about thinking creatively about traits and signals to figure out unique ways to spot your best customers and engage them with the maximum context, driving GTM alpha.

## 🎉 Congrats!

That’s a wrap on enrichments for inbound leads! You now know how to leverage Clay’s enrichments and Claygent to fill in the narrative around your inbound leads, finding data that might or might not exist in traditional databases.

In the next lesson, we’ll go over the next step of the process, which you might recall from Clay 101, is transformation. We’ll show you how to clean and normalize data for efficient, effective scoring and routing.

Next up