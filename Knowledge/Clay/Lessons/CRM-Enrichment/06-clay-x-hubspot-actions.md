---
title: "Clay x HubSpot Actions [CRM Enrichment]"
source: "https://university.clay.com/lessons/clay-x-hubspot-actions-crm-enrichment"
author:
published:
created: 2026-07-14
description:
tags:
  - "clippings"
---
##### CRM Enrichment

Build data hygiene processes for your CRM at scale, and keep it automatically up-to-date.

Progress

![](https://www.youtube.com/watch?v=8ietWF-t3N0)

About this lesson

00:00

## Clay x HubSpot Actions

## Introduction

In our previous lesson, we covered the technical foundations of CRM enrichment: connecting Clay to HubSpot and Salesforce, importing your contacts, and setting up proper field architecture.

Now we're diving into Clay's HubSpot actions, which are the core building blocks for actually working with your HubSpot data inside Clay.

This lesson focuses specifically on HubSpot actions. In the next lesson, we'll cover Salesforce-specific actions, so feel free to focus on whichever CRM your team uses.

## 📚 Understanding HubSpot Actions

### Read-Only vs. Write Operations

First, you have **Lookup** actions. These pull data FROM HubSpot INTO Clay without changing anything in your CRM. Think of these as read-only operations—you're simply viewing and importing existing data for analysis or enrichment purposes. Your HubSpot database remains completely unchanged regardless of how many times you run these actions.

With Lookup actions, you can experiment freely—there's no risk of damaging your CRM data or disrupting your sales team's workflow. You can run tests, try different queries, and iterate on your approach without any consequences to your production data.

Then you have **Create** and **Update** actions. These push data FROM Clay TO HubSpot and actually modify your CRM records. These are write operations that make real, permanent changes to your database that affect every user in your organization.

With Create and Update actions, you need to be more careful and methodical. These actions have real business consequences because they modify data that your entire revenue team relies on for their daily operations.

Think of it this way: Lookup is like reading a book—you're not changing the content, just consuming information. Update and Create are like editing the book or adding new pages—you're making permanent changes that affect everyone who reads it afterward.

## 🔍 Lookup Actions

### Primary Use Cases

- **Contact and Company Lookup** allows you to pull existing contact records, company profiles, and all their associated data into Clay for further enrichment or analysis. This creates a foundation layer of existing CRM data that you can then enhance with external sources.
- **Duplicate Checking** represents another powerful use case that prevents CRM pollution. Before creating new records, you can lookup existing contacts by email or company domain to avoid creating duplicates in your CRM. This proactive approach maintains data hygiene and prevents the confusion that comes from multiple records for the same prospect.
- **Data Verification** allows you to cross-reference information between Clay and HubSpot to identify inconsistencies or outdated records that need attention. You might discover that contact job titles in HubSpot don't match current LinkedIn information, creating opportunities for targeted updates.

## ✏️ Create and Update Actions

These actions are where Clay becomes truly powerful for CRM enrichment, but they also require careful planning and execution because they make permanent changes to your HubSpot database.

### Create Actions

Create actions let you add completely new contacts, companies, or deals to HubSpot directly from Clay. This capability is perfect for adding enriched prospects from your outbound research, importing leads from external sources, or creating records for companies discovered through signal monitoring.

The key with Create actions is ensuring you're not accidentally creating duplicate records. This requires combining Create actions with Lookup actions to check for existing records before attempting to create new ones.

### Update Actions

Update actions modify existing HubSpot records with new data from Clay. You might update contact records with enriched job titles, add company funding information, append research notes, or populate custom fields with insights gathered from external sources.

## ⚙️ Setting Up Conditional Logic for Updates

When setting up Update actions, you must specify conditions for when the update should run. This prevents accidental overwrites and ensures you're only updating records when it makes strategic sense.

### Common Conditional Patterns

Consider implementing conditions like:

- **Empty Fields**: Only update if the current field is empty. This prevents overwriting existing, potentially valuable data with automated enrichment.
- **Recency Validation**: Only update if the new data is more recent than existing information. This ensures you're not replacing fresh data with stale information.
- **Confidence Thresholds**: Only update if the confidence score or data quality meets a certain threshold. This prevents low-quality enrichment from polluting your CRM.
- **Source Prioritization**: Only update if the new data comes from a higher-priority source than the existing information. This creates a hierarchy of data quality that protects your most reliable information.

Without proper conditions, you could accidentally overwrite good data with incomplete or outdated information, creating more problems than you solve.

### Create Action 101

For Create actions, you want to use conditional formulas to only create new records if nothing was found during your Lookup phase. This prevents duplicate creation while ensuring you capture all net-new prospects from your enrichment workflows.

## 🧪 Safe Experimentation Practices

Here's a best practice that will save you significant headaches during development: turn off auto-update when you're experimenting with Create or Update workflows.

Instead of automatic execution, you can manually trigger updates on small batches of records once you've verified everything looks correct in Clay. This allows you to review the intended changes, spot potential issues, and make corrections before they affect your production CRM data.

Once you're confident in your workflow and have tested it thoroughly on small datasets, you can re-enable auto-update for seamless automation.

## 🔄 Combining Actions for Powerful Workflows

As you start building more sophisticated enrichment systems, you'll often combine these actions into comprehensive workflows that handle the complete enrichment lifecycle.

### Typical Workflow Pattern

A sophisticated workflow might follow this sequence:

**1\. Data Enrichment**: Start by enriching your prospect data using external sources and AI research to gather comprehensive intelligence.

**2\. Data Lookup**: Use Lookup actions to check if contacts already exist in HubSpot, preventing duplicate creation while identifying existing records that need updates.

**3\. Selective Creation**: Create new contacts for prospects not already in HubSpot, ensuring your CRM captures all qualified opportunities from your research.

**4\. Targeted Updates**: Update existing contacts with enriched information, but only where the new data adds value or fills gaps in existing records.

The beauty of Clay's HubSpot integration is that it gives you surgical precision over your CRM data. You can enrich exactly what you want, when you want, with complete transparency into every change. This level of control enables sophisticated data strategies that would be impossible with manual processes or simple bulk operations.

Next up