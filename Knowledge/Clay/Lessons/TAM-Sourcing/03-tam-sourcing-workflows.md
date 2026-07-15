---
title: "TAM Sourcing Workflows in Clay [TAM Sourcing]"
source: "https://university.clay.com/lessons/tam-sourcing-workflows-in-clay-tam-sourcing"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### TAM Sourcing

Learn how to systematically map your entire addressable market with Clay's real-time data and identify high-intent prospects ready to buy.

Progress

![](https://www.youtube.com/watch?v=XVjtiqpMxHY)

About this lesson

00:00

## TAM Sourcing Workflows in Clay

## ⚙️ TAM Sourcing: From Workflows to Revenue Engines

## Introduction

In our last lesson, we discussed how Clay's data foundation and search capabilities help you quickly find companies in your ICP.

Now, we're moving from theory to practice, showing you how to construct end-to-end systems that consistently identify, qualify, and route high-value prospects at scale.

This shift from one-time workflows to repeatable systems represents a fundamental change in how you approach prospecting. Instead of manually building lists repeatedly, you're architecting intelligent engines that run continuously and improve over time.

## 🔧 The Three Core Components of TAM Sourcing Systems

### Data Inputs: Where Prospects Come From

Your data inputs represent all the sources feeding your prospecting system. These might include existing CRM data, third-party databases, intent signals from web activity, or Clay's SMB discovery tools like OpenMart.

The key is thinking about input diversity and reliability. What happens when your primary source doesn't have complete coverage? How do you ensure data freshness? Building robust systems requires planning for multiple input sources and implementing fallback mechanisms.

### Data Processing: Turning Raw Data Into Intelligence

Data processing includes all the transformation and enrichment steps that turn basic company information into actionable prospect intelligence. This encompasses enrichment waterfalls that gather comprehensive data, AI classification that segments prospects intelligently, ICP scoring that prioritizes opportunities, and quality validation that ensures reliability.

This is where the magic happens: where raw company names become deeply understood prospects with clear qualification status and prioritization scores.

### Output Integration: Flowing Into Sales Systems

Output integration ensures qualified prospects flow seamlessly into your sales systems where they can drive revenue. This includes CRM integration, automated outreach sequence enrollment, and sales team routing based on territory or expertise.

Great GTM engineers think about how these three components work together as an interconnected system rather than isolated steps.

## 💡 Workflow Thinking vs. Systems Thinking

Understanding this distinction is crucial for building TAM sourcing capabilities that scale and improve over time rather than requiring constant manual intervention.

### Workflow Thinking: One-Time Execution

Workflow thinking approaches prospecting as discrete tasks: Find 100 prospects and send them to your CRM. Build a table, run some enrichments, export a CSV. This approach works for immediate needs but isn’t set up to scale or improve over time.

### Systems Thinking: Continuous Operation

Systems thinking focuses on building auto-updating mechanisms that consistently identify, qualify, and route high-value prospects at scale without manual intervention. These systems run on schedules, learn from outcomes, and adapt to changing market conditions.

Instead of "I need to find prospects today," systems thinking asks "How do I build a system that continuously identifies optimal prospects and improves its targeting over time?"

This mindset shift transforms prospecting from a recurring task into a strategic asset that compounds in value.

## 🍽️ Real Case Study: Lightspeed's Restaurant Targeting System

Let's examine a real implementation that demonstrates systems thinking in practice. Lightspeed built a sophisticated restaurant prospecting system for their point-of-sale solution targeting specific European markets.

### The Challenge

Lightspeed needed to systematically identify and qualify restaurant owners in specific European cities for their point-of-sale system. Traditional prospecting methods couldn't provide the local business coverage or the specific operational insights needed for effective targeting.

### Discovery and Initial Filtering

They used Openmart and Clay's Google Maps API to discover restaurants systematically across target cities, applying intelligent filters based on rating thresholds that indicated business quality, review counts that suggested operational scale, and business hours that confirmed active operations.

This approach provided comprehensive local business coverage that traditional B2B databases couldn't match, capturing the long tail of independently-owned restaurants that represented their core market.

### Enrichment and Classification

For each discovered restaurant, they enriched with revenue estimates using Claygent's research capabilities, providing crucial business sizing information not available in standard databases.

AI classification then categorized each restaurant by cuisine type (fine dining, casual, fast-casual), service model (dine-in, takeout, delivery-focused), and technology needs based on operational complexity. This segmentation enabled targeted messaging and appropriate solution positioning.

### Intelligent Scoring

ICP scoring used weighted factors based on location (high-traffic areas scored higher), estimated size (revenue and review volume), and growth indicators (recent expansion, increasing review counts, hiring signals).

This multi-factor scoring ensured sales resources focused on restaurants most likely to have both need and budget for POS system upgrades.

### Seamless Integration

Qualified prospects flowed directly into Lightspeed's CRM with all custom fields properly populated, relevant outreach sequences automatically triggered, and territory assignments handled systematically based on rep coverage areas.

### Measurable Impact

The results were transformative. Lightspeed went from manually researching 20-30 prospects per week to automatically qualifying 200+ prospects per day—a 30x increase in prospecting capacity.

Sales conversion rates improved significantly because prospects were better qualified with richer contextual data about their operations, challenges, and technology needs.

While competitors relied on manual research, Lightspeed could identify and engage new market opportunities within hours of entering a new city, creating substantial first-mover advantages.

## ✅ Quality Control: Professional Systems vs. Amateur Workflows

Quality control mechanisms separate professional revenue-generating systems from amateur workflows that break under scale or produce unreliable results.

### Systematic Validation Checks

Build validation at every step of your workflow. Does this restaurant exist at this address (verifying against multiple data sources)? Is the revenue estimate reasonable given the location, cuisine type, and review volume? Does the contact email match the business domain or appear legitimate?

### AI-Powered Anomaly Detection

Leverage AI to automatically flag anomalies that human reviewers should examine: restaurants with suspiciously high revenue estimates relative to size indicators, contacts with generic email addresses that suggest gatekeepers rather than decision-makers, businesses showing signals they might be closed or relocated.

This automated flagging enables human judgment to focus on edge cases while the system handles standard scenarios reliably.

### Automatic Exception Handling

Design your system to handle variations systematically. Food trucks get tagged for different sales approaches that acknowledge their mobile operations and different POS needs. Unclassified restaurants get routed for human review rather than forcing them into inappropriate categories. Businesses without discoverable contacts get added to nurture sequences until decision-makers can be identified through alternative methods.

This ensures your system continues operating effectively even when data is incomplete or scenarios are unusual.

## 📊 A Universal Framework for TAM Sourcing Systems

Here's a four-step framework that applies across different prospecting scenarios, from customer expansion to partner identification to competitive intelligence gathering.

### Step 1: Define Your Data Inputs

Ask critical questions about sourcing: What sources will feed your system? How will you ensure data quality and freshness? What backup sources exist when primary sources fail? How will you detect when data becomes stale?

Robust systems plan for multiple input sources and graceful degradation when individual sources have coverage gaps.

### Step 2: Design Data Processing

Plan your data transformation layer: What enrichments do you need to qualify prospects effectively? How will you score and prioritize opportunities? What data points enable accurate classification? How will you handle incomplete or ambiguous data?

This turns raw inputs into actionable intelligence your sales team can use confidently.

### Step 3: Build Your Intelligence Layer

Create the decision-making logic: What rules determine qualification status? How will AI enhance rather than replace human judgment? What feedback loops improve accuracy over time? How do you measure and optimize scoring models?

The intelligence layer is where systems learn and improve, becoming more effective as they process more prospects and receive outcome data.

### Step 4: Design Output Integration

Plan how intelligence flows into action: How will qualified prospects reach sales systems? What outreach sequences or sales motions should trigger? How will you measure performance and ROI? What data needs to flow back to improve the system?

This completes the loop, ensuring market intelligence translates into revenue-generating activities while creating feedback for continuous improvement.

This framework applies far beyond basic prospecting. Regardless of the workflow, the core principles remain constant: design for repeatability, build in quality control, create feedback loops, and optimize for business outcomes rather than just data outputs.

Table of contents[Introduction](#introduction)

[

🔧 The Three Core Components of TAM Sourcing Systems

](#the-three-core-components-of-tam-sourcing-systems)[Data Inputs: Where Prospects Come From](#data-inputs-where-prospects-come-from)[Data Processing: Turning Raw Data Into Intelligence](#data-processing-turning-raw-data-into-intelligence)[Output Integration: Flowing Into Sales Systems](#output-integration-flowing-into-sales-systems)

[

💡 Workflow Thinking vs. Systems Thinking

](#workflow-thinking-vs-systems-thinking)[Workflow Thinking: One-Time Execution](#workflow-thinking-one-time-execution)[Systems Thinking: Continuous Operation](#systems-thinking-continuous-operation)

[

🍽️ Real Case Study: Lightspeed's Restaurant Targeting System

](#real-case-study-lightspeeds-restaurant-targeting-system)[The Challenge](#the-challenge)[Discovery and Initial Filtering](#discovery-and-initial-filtering)[Enrichment and Classification](#enrichment-and-classification)[Intelligent Scoring](#intelligent-scoring)[Seamless Integration](#seamless-integration)[Continuous Improvement Through Feedback](#continuous-improvement-through-feedback)[Measurable Impact](#measurable-impact)

[

👤 Advanced Contact Discovery Strategies

](#advanced-contact-discovery-strategies)[Example: Restaurant Decision-Makers](#example-restaurant-decision-makers)[Multi-Layered Discovery Approach](#multi-layered-discovery-approach)[Contact Validation and Verification](#contact-validation-and-verification)

[

✅ Quality Control: Professional Systems vs. Amateur Workflows

](#quality-control-professional-systems-vs-amateur-workflows)[Systematic Validation Checks](#systematic-validation-checks)[AI-Powered Anomaly Detection](#ai-powered-anomaly-detection)[Automatic Exception Handling](#automatic-exception-handling)

[

📊 A Universal Framework for TAM Sourcing Systems

](#a-universal-framework-for-tam-sourcing-systems)[Step 1: Define Your Data Inputs](#step-1-define-your-data-inputs)[Step 2: Design Data Processing](#step-2-design-data-processing)[Step 3: Build Your Intelligence Layer](#step-3-build-your-intelligence-layer)[Step 4: Design Output Integration](#step-4-design-output-integration)

Related resources

Next up