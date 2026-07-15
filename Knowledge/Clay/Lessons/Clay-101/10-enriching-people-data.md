---
title: "Enriching People Data [Clay 101: GTM Automation]"
source: "https://university.clay.com/lessons/enriching-people-data"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=VPqOcSkto1o)

About this lesson

00:00

## Enriching People Data

We're continuing with enrichments! In our last lesson, you used waterfalls to enrich companies. In this lesson, we'll cover enriching people.

Having the right contact information is critical when reaching out to potential customers. If you don't have correct emails and phone numbers, it doesn't matter how good your messages are—the message will never reach them!

## 📋 What You Should Have to Start Enriching People

Here's what you should have:

- A people list with LinkedIn profile URLs and names. If you followed our previous lesson on Finding People, you should already have this.
- Understanding of the relationship between company and people data. Remember how we linked your company and people tables? That connection is crucial for effective enrichment.
- A clear plan for your outreach strategy. Are you doing cold email? LinkedIn outreach? Multi-channel campaigns? Your strategy should guide which enrichments you prioritize.

## 📧 Understanding Email Validation

Before we dive into email enrichment, let's talk about validation.

Clay's email waterfall doesn't just find people’s emails—it validates them as well.

By default, we use ZeroBounce, a best-in-class validation service, but you have the flexibility to choose a different provider if you prefer. For example, if you know a different provider validates best for your specific industry, go ahead and use that provider.

Clay considers catch-all emails valid by default, but you can toggle on the "Only mark 'Safe to Send' emails as valid" setting to exclude catch-all emails if you're concerned about deliverability.

The validation process ensures you're not just getting email addresses—you're getting email addresses that will actually reach your prospects.

## 🛠️ Step-by-Step: Enriching People with Email Waterfalls

Let's walk through enriching people with email waterfalls:

- First, open the Enrichment Panel by clicking the "Add enrichment" button, then search for "Work Email" in the list of available enrichments.
- Next, you'll configure your email waterfall. You'll see a pre-arranged order of email providers optimized for coverage. You can add or reorder email providers as desired to maximize data coverage. The great thing about Clay is that if a provider doesn't return an email, you get your data credits refunded automatically.
- Now you'll select your input columns. The primary input required is the Company Domain. Ideally, you should also include Personal Social Profile URLs—this significantly improves accuracy. If those aren't available, you can use fallback combinations like Full Name + Company Name or Full Name + Personal Email.
- Next, choose your validation settings. Clay defaults to ZeroBounce for validation, but you can select another validator if preferred. You'll also need to decide how to handle catch-all emails. By default, catch-all emails are treated as valid, but you can toggle to treat them as invalid if you want to be more conservative about deliverability.
- As always, start by testing on small batches. Run a test on 10 rows first to review results before scaling. Click "Save & Run (10 Rows)" to initiate the process.
- Once the enrichment process starts, Clay dynamically moves through the waterfall. If a provider finds a valid email, the process stops for that contact. If no email is found, data credits are refunded and Clay moves to the next provider until an email is found or all providers are exhausted.

Note that validation columns are hidden by default, but you can open the Columns Panel and unhide these columns to inspect detailed validation steps and understand exactly how each email was validated.

## 📊 What Else Can You Enrich Beyond Email?

While email addresses are most important and common, Clay can also help you find many other useful pieces of contact information:

- You can easily add phone numbers for multi-channel outreach campaigns.
- Social profiles like Twitter, Facebook, and Instagram can provide additional context for personalization.
- GitHub URLs are valuable if you're targeting developers or technical teams.
- Work experience and education history can help you understand someone's background and craft more relevant messaging.

The key is to think about which additional data points will actually help you create more personalized, relevant outreach.

## 🚀 Advanced People Enrichment Strategies

As you get more sophisticated with people enrichment, you can explore advanced strategies:

- Like multi-threading outreach by finding multiple contacts within the same organization.
- You can build relationship maps to understand who reports to whom and how different contacts are connected. You can enrich based on behavioral data like website visits or content engagement.
- You can also use enriched data to create detailed buyer personas that help you segment your outreach and messaging strategies.

We'll cover these techniques in more advanced Clay courses.

## ✅ Conclusion

You've learned how to find validated email addresses and other useful information about people that will help you reach out to them more effectively.

In our next lesson, we'll dive deep into Claygent—Clay's AI web scraper that can find unique insights about companies and people that don't exist anywhere else. For example, with Claygent you can capture custom enrichment data across the web, like recent social media activity, published articles, conference appearances, or community involvement.

Let's jump in.

Next up