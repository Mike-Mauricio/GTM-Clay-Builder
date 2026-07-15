---
title: "Transform Data Into Clear Classifications [AI-Powered GTM Automation]"
source: "https://university.clay.com/lessons/transform-data-into-clear-classifications"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=4iK8oCwVL0c)

About this lesson

00:00

## Transform Data Into Clear Classifications

Now that we've covered how to use **AI Formulas** for deterministic transformations, like calculations, cleanups, and structured edits to existing data, it's time to focus on **generative transformations** with **Use AI** or **Claygent** that help you turn messy, unstructured inputs into clean classifications.

## 🔍 Example: Categorizing Companies by Business Model and Industry

Let's say you scraped a list of companies. First, you want to automatically label each one based on their business model so you can segment your outreach strategy. Then, you also want to segment based on industry.

With **Claygent**, you can summarize the available data and assign the best-fit label without building rules or manual filters.

<iframe src="https://demo.arcade.software/vhFADEk8JeRIldFK1eme?embed&amp;embed_mobile=tab&amp;embed_desktop=inline&amp;show_copy_link=true" title="Transform Data Into Clear Classifications" frameborder="0" allowfullscreen=""></iframe>

## 📋 Implementation Process

Here's how you can implement this process in Clay:

**Step 1: Start with Company Information** Begin with basic company data like domain name, company name, or LinkedIn URL. Clay can use any of these to gather more information.

**Step 2: Use Basic AI Enrichment**

1. Go to "Enrich" and select "Enrich company with AI"
2. Choose which fields you want to add. For our example, we can add business model, and Claygent will populate your table with basic classifications like B2B vs B2C.
3. You can also enrich with description, industry focus, etc.

Now, what if we want more specific categorization?

**Step 3: Create Custom Classifications with Claygent**

- Open Claygent in your table
- Use the meta prompter to define your classification requirements
- Create a prompt that outlines your classification system

When creating your prompt, be sure to:

- Define your specific categories (e.g., 5-6 industry buckets)
- Provide clear descriptions for each category
- Include examples for each category

**Step 4: Run and Review**

1. Generate and run the enrichment
2. Review the classifications in your table
3. You can also add the confidence field to see how certain the AI is about each classification

This is a powerful way to generate structure from scattered information, without having to write your own classification logic.

## 🎯 When to Use Generative AI for Transformation

Remember, use generative AI when structure has to be created.

Use cases like this come up all the time:

- Grouping companies by **custom verticals**
- Assigning prospects to the right **persona bucket**
- Labeling inbound form submissions by **buyer intent**
- Or mapping companies to **internal go-to-market segments**

If the input is messy, inconsistent, or sourced from human language, then **generative AI** will get you there faster and more reliably than rules ever could.

## 💡 Sample Custom Classification Prompt

Here's an example of how you might structure a custom classification prompt:

*`You're an expert at categorizing companies into industries. Review the company's website and assign one single best-fitting category from the following options.      1. Fintech: Companies that use technology to improve or automate financial services and processes. This includes payment processing, banking software, investment platforms, and financial management tools.   Examples: Square, Stripe, Plaid      2. Marketing Tech: Companies that provide software and tools for digital marketing, advertising, customer engagement, and marketing analytics.   Examples: HubSpot, Mailchimp, Semrush      3. Cloud Computing: Companies that deliver computing services (including servers, storage, databases, networking) over the internet.   Examples: AWS, Microsoft Azure, Google Cloud      4. SaaS (Software as a Service): Companies that deliver software applications over the internet on a subscription basis, excluding those that fit specifically in other categories.   Examples: Salesforce, Zoom, Dropbox      5. Compliance: Companies that provide solutions for regulatory compliance, risk management, data privacy, and security standards adherence.   Examples: OneTrust, LogicGate, MetricStream      Please categorize based on the company's primary business focus, even if they operate across multiple categories.      Be thorough in your reasoning on why this category fits best.`*

## 🚀 Benefits of AI-Powered Classification

Using generative AI for classification offers several advantages:

1. **Consistency**: You get standardized labels even from varied inputs
2. **Speed**: No need to manually review and categorize each record
3. **Flexibility**: You can easily update your classification system as your needs evolve
4. **Nuance**: AI can consider complex factors beyond simple keyword matching

## 🔮 What's Coming Next

That completes our exploration of the Transform step in the FETC framework. Next, we're moving onto the last component: **Create.**

In the Create step, we'll show you how to leverage all the clean, structured data you've gathered and transformed to generate personalized content for your outreach campaigns.

Next up