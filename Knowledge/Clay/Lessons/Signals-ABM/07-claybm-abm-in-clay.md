---
title: "ClayBM: ABM in Clay [Signals & ABM]"
source: "https://university.clay.com/lessons/claybm-abm-in-clay-signals-abm"
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

![](https://www.youtube.com/watch?v=xzr23l9Ilcg)

About this lesson

00:00

## ClayBM: ABM in Clay

## Introduction to ABM in Clay

Today, we're diving into Account-Based Marketing (ABM) in Clay—where we take everything you've learned about signals and audiences and apply it to your most valuable accounts.

This is where Clay really shines: helping you deeply penetrate high-value accounts with precision targeting and real-time intelligence. ABM isn't just another prospecting strategy but a fundamental shift in how you approach your market.

## 🐟 What Makes ABM Different

Account-Based Marketing is fundamentally about precision over volume. Instead of casting a wide net hoping to catch anything, ABM is like spear fishing. You identify which fish you want, study their behavior, and strike with precision.

This means targeting 100 to 2,000 accounts maximum, with a few thousand total contacts per year. Compare that to traditional prospecting where you might contact thousands of prospects daily. For high-value accounts, generic messaging doesn't just fail—it actively damages relationships before they even begin.

## 🧠 Clay as Your ABM Central Nervous System

Clay serves as the unified data layer that makes modern ABM possible. Think of it as the central nervous system connecting your first-party data, enrichment providers, intent signals, and CRM. It's where all your account intelligence comes together in one place.

Modern ABM requires accurate, real-time data at two levels:

At the company level, you need to understand how priorities are shifting. Is the company expanding? Did they raise funding? Are they posting jobs that signal new initiatives? These signals tell you when accounts are ready to engage.

At the people level, you need to identify the right person to reach at the right moment. Did someone new join the buying committee? Did your champion move roles? Understanding personnel changes prevents outreach from falling into a black hole.

## 🔄 The Unified ABM Motion

The ABM motion in Clay ties together demand generation, sales development, expansion, and customer success. Instead of operating in silos, ABM creates a unified approach to penetrate your most valuable prospects.

You start with real-time data monitoring—tracking job changes, company news, and intent signals. Then you progress accounts through defined stages based on engagement. You orchestrate multi-channel touchpoints including ads, events, personalized content, and direct outreach. Finally, you maintain human-in-the-loop execution where ops teams continuously improve automation based on results.

## 📊 The Three Core ABM Stages

Understanding how accounts move through your ABM funnel is critical. Each stage requires different data, messaging, and tactics.

### Stage 1: Aware

Accounts enter through social media connections, social engagement, website visits, event attendance, or investor introductions. At this stage, they know you exist but haven't shown meaningful interest yet.

Your tactics include social media auto-connect sequences, paid advertising, personalized landing pages, warm introductions, and event invitations. The goal is building awareness and establishing initial relationships.

### Stage 2: Interested

Accounts move here when they create a workspace, visit pricing pages, send positive replies, or attend high-intent events. This is where curiosity transforms into genuine interest.

Tactics shift to retargeting ads, signal-based outbound sequences, webinars, and case studies. You're now nurturing active interest and demonstrating value specific to their situation.

### Stage 3: Evaluating

This stage is triggered by contact sales form submissions or discovery meetings. The account is actively considering whether to buy, and every interaction matters.

Tactics become executive dinners, referrals, multi-threading across the organization, and pre-call research briefs. You're removing friction and building conviction across multiple stakeholders.

## 🤝 Converting Accounts to Aware Stage

Systematic relationship building is key to getting accounts into your ABM motion.

- For events and dinners, filter your target list by location and contact grade, then auto-send invites to relevant events. Geography-based targeting ensures you can meet prospects face-to-face when they're ready.
- For warm introductions, upload your executives' social media connections, cross-reference with target accounts, and identify mutual connections who can make introductions. Warm intros convert at dramatically higher rates than cold outreach.
- Social media auto-connect works well when triggered by engagement. Set up workflows that send connection requests when prospects engage with content or visit landing pages—they're already showing interest.
- Clay excels at social listening. Monitor relevant keywords and get alerts when prospects post about topics related to your solution. This gives you perfect conversation starters grounded in their actual priorities.

## 💡 Moving Accounts to Interested Stage

Moving accounts from aware to interested requires deeper intelligence and personalization.

- Use Claygent to scrape company websites, recent news, and SEC filings to identify their top three business and technology priorities. Then create personalized landing pages that reference these specific priorities. Generic messaging won't cut it at this stage.
- Track product signals if they're using your product. Monitor feature usage and trigger personalized help offers when they hit milestones. This positions you as helpful rather than pushy.
- Web intent tracking becomes critical. Monitor not just page visits, but time on site and multiple visits that indicate growing interest. Someone spending 8 minutes on your pricing page is telling you something important.

## 🎯 Deploying High-Touch Tactics in Evaluating Stage

The evaluating stage is where you deploy your highest-touch tactics to close deals.

- Auto-generate pre-call research briefs that include company summaries, recent funding information, potential partnership ideas, and relevant news. This arms your sales team with conversation starters that demonstrate you've done your homework. First impressions matter enormously at this stage.
- Multi-threading becomes essential. Use conversation intelligence tools like Gong to identify stakeholders mentioned in calls, then reach both economic buyers and end users. Single-threaded deals are fragile.
- Track new hires joining target accounts mid-evaluation. When key personas join during your sales process, trigger immediate outreach to bring them up to speed. Don't let personnel changes derail your momentum.

## 🏗️ The Three-Table ABM Architecture

Here's how this works in practice with a three-table ABM workflow. This is the architecture we use at Clay to manage our ABM motion, and you can replicate it for your accounts.

**Table 1: Named Account List of Contacts**

Import contacts from your CRM on a scheduled basis. Key columns include name, normalized social mediaURL, current ABM stage, and contact grade. This serves as your source of truth for account progression and ensures everyone is working from the same data.

**Table 2: Brand Mentions Tracking**

Use the Find Post Audiences action to pull mentions of your domain—at Clay we monitor [clay.com](http://clay.com/), but you can search for mentions of relevant keywords like your product category. Set this to run daily within a defined timeframe.

Then classify posts with AI to determine if someone built something with your product, mentioned a competitor, or showed buying intent. Enrich the poster's profile, normalize their social mediaURL, and check if their company domain matches accounts in your CRM. Score the engagement level to prioritize follow-up.

**Table 3: Lookup and Stage Updates**

Pull the current ABM stage from Table 1, lookup the social media URL from Table 2, and if you find a match that meets your criteria, automatically update the stage and write changes back to your CRM.

This creates a closed-loop system where social signals automatically advance your ABM stages, ensuring no engagement goes unnoticed. Your team gets real-time alerts about account activity, but they make the strategic decisions about how to engage.

Next up