---
title: "Enrich Images and Screenshots [AI-Powered GTM Automation]"
source: "https://university.clay.com/lessons/enrich-from-images-and-screenshots"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=kHc8snnSdL8)

About this lesson

00:00

## Enrich Images and Screenshots

We just covered using Perplexity to enrich your data. Now, let's look at how you can enrich from **images and screenshots**.

Anytime you know who your target accounts work with—or who they serve—you have a serious edge in outbound. With the Analyze Image enrichment, you can instantly pull brand logos from a company's homepage and turn that into actionable insights for outreach.

In other words, you can pull insights from any visual content on the web that would be hard to get through scraping or would require manual work.

## 🔍 When to Use Analyze Image Enrichment

You can use the Analyze Image enrichment when you need to:

- Pull **logos or icons** from a webpage
- Understand **brand associations** or customer lists
- Automate visual research that would normally require manual review

## 🛠️ Step-by-Step Process in Clay

Here's how you would do this in Clay with the Analyze Image enrichment:

1. **Start with a domain** - We'll use [clay.com](http://clay.com/) as an example. First, we'll use the Analyze Image enrichment.
2. **Configure the Analyze Image prompt** - Set it to say:*"Analyze and return a comma-separated list of the company names for every logo you see on the page, prioritized by getting all the logos on the page. Scroll to the bottom of the page and make sure you get all the logos. Return only the list."*
3. **Include the domain URL** - Make sure to add the domain URL in the configuration box.
4. **Run the enrichment** - After clicking Save, the enrichment will run and return a list of all logos found on the webpage. You can verify the results by comparing them to the original webpage.
5. **Convert to JSON format** - Next, add another enrichment and select AI. Set the prompt to:"Return this comma-separated list as a JSON list" and make sure to select JSON schema as the output format.
6. **Configure the schema** - Set up the schema to extract company logos properly.
7. **Write to a new table** - Once you have the JSON schema, click into the JSON result, select "Take action on list," and choose "Write each item to a new row in another table."
8. **Create a table for the logos** - Create a new table, select the list column, and specify the JSON conversion company logos field. After saving, you'll have a new table with all the companies listed.
9. **Extract domains** - Finally, use another Claygent prompt to extract the domain for each company. With these domains, you can then enrich the data further - looking up company news, information, or any other relevant research you need.

## 💎 Additional Use Cases

The Analyze Image enrichment is useful in many other scenarios:

- **Company research** - Scan a screenshot of a customer's homepage to understand what they do and how their site is designed
- **Hiring signals** - Check if a person's LinkedIn profile has a "Hiring" badge by analyzing a screenshot with AI
- **Technology detection** - Use a screenshot + AI image analysis to detect if a site has a live chat widget or other tools

## 🎮 Pro Tip: Get Page Screenshot

One last detail: Instead of using the domain directly, you can use the "Get Page Screenshot" enrichment, which takes a picture of a webpage based on the domain, and then use that to analyze that screenshot with the Analyze Image enrichment.

## 🌟 Why This Matters

Visual data enrichment gives you access to information that might otherwise:

1. Require manual research by your team
2. Be missed entirely in text-based scraping
3. Provide unique insights your competitors don't have

By automatically extracting visual information from websites, you can build a more complete picture of your target accounts and their ecosystem, leading to more effective and personalized outreach.

Next up