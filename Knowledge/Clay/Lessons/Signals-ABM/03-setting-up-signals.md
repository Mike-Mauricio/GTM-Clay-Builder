---
title: "Setting Up Signals in Clay [Signals & ABM]"
source: "https://university.clay.com/lessons/setting-up-signals-in-clay"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### Signals & ABM

Master Signal Orchestration, Account-Based Marketing, and Intelligence-Driven Advertising to Build proactive GTM engines.

Progress

![](https://www.youtube.com/watch?v=04hIGswFeZY)

About this lesson

00:00

## Setting Up Signals in Clay

## Introduction

In our last lesson, we explored the different types of signals available in Clay and when to use each one. Now we're diving into the practical side: actually setting up your first signals.

By the end of this lesson, you'll know exactly how to configure signals, set up automatic enrichments, and troubleshoot the most common setup issues. Let's get your signals running so you can start capturing those high-intent moments in real-time.

## 👔 Setting Up Job Change Signals

Job changes convert exceptionally well because they represent major professional transitions that often include budget authority, strategic planning, and openness to new vendor relationships.

#### Configuration Steps

Select `Job Change` from your signal options. Choose your data source—CRM import, CSV upload, or existing Clay table containing the contacts you want to monitor.

#### Required Data Fields

- **Social Media Profile URLs**: Clay uses these to watch for job changes. If you don't have social media URLs in your data, use Clay's enrichment tools to find them before setting up the signal.
- **Company Domains or Company Social Media URLs**: This helps Clay distinguish between someone changing companies versus getting promoted at the same company.

#### Monitoring Scope

The quality of your job change signals depends on monitoring the right people. Focus on champions who've bought from you before, decision-makers at target accounts, or competitors' customers who might be open to switching when they change roles.

## 🆕 Setting Up New Hire Signals

New hire signals work exceptionally well for account-based prospecting, allowing you to engage new decision-makers before they've established vendor relationships.

#### Targeting Configuration

Select "New Hires" and set your targeting rules to focus on the right opportunities:

- **Company Size**: Define parameters like 50-500 employees for mid-market companies, or 1000+ for enterprise accounts, based on your ICP.
- **Job Title Keywords**: Add relevant titles like "CMO," "VP Marketing," or "CTO" based on who typically makes buying decisions for your solution.
- **Location Filters**: Set geographic boundaries matching your sales territory or service area. This prevents wasting resources on opportunities you can't effectively serve.
- **Time Window**: Set how recent hires should be. Find a good balance—recent enough to be relevant but not so narrow that you miss opportunities.

Provide company domains or social media company URLs for accounts you want to monitor. The more companies you include, the more potential signals you'll capture—but ensure they align with your ICP to maintain signal quality.

#### 🔄 Layering on Enrichments

Signals become truly powerful when you add automatic enrichments that transform raw alerts into actionable intelligence.

- **Contact Enrichments**: Find new email addresses and phone numbers so you can reach out immediately without manual research.
- **Company Enrichments**: Gather tech stack information, funding details, and employee counts to inform your messaging and qualification.
- **AI Research**: Analyze the company's website, recent news, and industry position to generate personalized talking points for your outreach.

## 📤 Operationalizing Signal Results

Clay offers several options for routing signal results to your team. Here are some examples:

- **Send to New Tables**: Generate a dedicated table for each signal type. This keeps different signal categories organized and makes it easy to track performance by signal type.
- **Add to Existing Tables**: Append results to tables you're already using.
- **Send to Slack**: Send automated alerts to Slack channels so that your reps can act on signals in real time
- **Webhooks**: Send data to other systems in real-time for advanced automation scenarios.
- **CRM Push**: Route results straight into Salesforce or HubSpot, creating records automatically with enriched data already populated.

## ⏰ Run Frequency

Run frequency depends on how time-sensitive your signals are and how quickly you can act on them.

**Daily Runs**: Ideal for job changes and critical account monitoring where timing matters significantly. Catching someone within days of a job change is far more valuable than reaching out months later.

**Weekly Runs**: Work well for market research and broader trend monitoring where immediate action isn't critical.

**Monthly Runs**: Suitable for industry analysis and long-term strategic intelligence gathering.

More frequent runs catch opportunities faster but consume more credits. Balance responsiveness with budget by matching frequency to your actual sales velocity.

## 📊 Dashboard Management

The Signals dashboard is your control center for monitoring and optimizing your signal systems.

#### Key Metrics

Track active signals across your organization, performance metrics including credits used and results generated, and run status to ensure signals are executing on schedule.

#### Ongoing Optimization

Signals are flexible and should evolve with your strategy. Click any signal name to edit targeting criteria, change enrichment selections, or update alert preferences.

You can pause signals without losing your configuration, which helps when adjusting strategy or managing credit consumption during budget planning.

#### Performance Tracking

Monitor signal effectiveness over time:

- **Credit Usage**: Understand the cost per signal relative to the value it generates
- **Result Quality**: Track how many results turn into actual opportunities
- **Optimization**: Adjust frequency or targeting based on conversion data

## 💡 Best Practices for Signal Success

Start small and grow strategically rather than launching dozens of signals at once.

#### Quality Over Quantity

One well-configured signal generating high-quality results beats five signals creating noise that your team ignores. Focus on the signals that directly support your highest-priority GTM motions.

#### Choose the Right Signal Type

- **Company Monitoring**: Best for account-based approaches where you're tracking specific target accounts for buying signals.
- **Contact Monitoring**: Ideal for relationship selling where champions and decision-maker movements create opportunities.

#### Create Standard Follow-Up Processes

The best signal is useless if nobody acts on it. Before launching signals, define:

- Who gets notified when signals trigger
- What actions they should take
- Expected response timing
- How to measure signal-to-opportunity conversion

Without clear processes, even perfect signals won't drive revenue.

## 🔧 Troubleshooting Common Issues

When signals aren't performing as expected, systematic troubleshooting helps identify and fix the root cause.

- **Signal Not Triggering**: Check required fields first—ensure you have clean social media URLs and complete company domains. Verify that targeting isn't too narrow; sometimes slightly broader parameters help establish baseline signal volume before optimizing.
- **False Positives**: If you're getting irrelevant results, tighten your filters by adding more qualifying conditions. Clay's AI can improve signal quality by learning from your feedback about which results are valuable.

Success comes from iteration and continuous improvement. Start with basic configurations, observe what works, and refine based on actual results. Signals become more valuable as you optimize them for your specific needs and market.

Next up