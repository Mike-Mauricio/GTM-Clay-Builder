---
title: "Importing from your CRM [CRM Enrichment]"
source: "https://university.clay.com/lessons/importing-from-your-crm-crm-enrichment"
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

![](https://www.youtube.com/watch?v=r6H8X7-Iays)

About this lesson

00:00

## Importing from your CRM

## Introduction

In our previous lesson, we covered the why and what of CRM enrichment. Now we're diving into the setup, specifically how to import data from your CRM into Clay. This is where the rubber meets the road. Getting your import process right sets the foundation for everything else we'll build in this course.

The first step in any CRM enrichment workflow is getting your existing data into Clay efficiently and correctly. The good news is that Clay has native integrations with both HubSpot and Salesforce, so you won't need to export CSV files or deal with manual data transfers that can introduce errors and become outdated quickly.

Before we dive into the technical setup, let's talk about the foundation that makes everything else work: proper field structure in your CRM. This strategic preparation will save you countless hours of cleanup work and ensure your enriched data delivers maximum value to your sales team.

## 🔗 Connecting Clay to HubSpot

HubSpot users benefit from a streamlined integration process that makes data import straightforward and reliable. Here's how to set it up:

In Clay, click "Import" and select "HubSpot" from the integrations menu. You'll be prompted to authenticate with your HubSpot account, which gives Clay the permissions it needs to read from and write back to your HubSpot data. This authentication process ensures secure access while maintaining your data privacy and compliance requirements.

Once connected, you'll see four main object types available for import, each serving different purposes in your enrichment strategy:

- **Company objects** contain your account-level data like company name, domain, industry, and revenue information
- **Contact objects** hold individual person records with names, emails, job titles, and contact information
- **Deal objects** track your sales opportunities with stages, amounts, and close dates
- **Lead objects** capture early-stage prospects before they become full contacts in your system

### Strategic Decisions

The key decision is choosing which list to pull from, as HubSpot organizes records into lists that can be imported individually. This list-based approach allows for targeted enrichment rather than processing your entire database.

Here's a pro tip that can save you significant Clay credits: filter your data in HubSpot before importing to Clay. If you only want to enrich contacts from enterprise accounts, for example, create a filtered list in HubSpot first. This prevents you from spending credits on enrichment for records you don't actually need to process.

During the import process, you'll see options to include read-only properties and exclude empty columns. Read-only properties are system-generated fields like create dates and last modified timestamps. Including them can be useful for analysis and workflow logic, but they'll consume columns in your Clay table, so consider whether you'll actually use this information.

Once your data is imported, you can click on any cell to see all the available properties from that HubSpot record, giving you complete visibility into what data is available for enrichment workflows.

## 🏢 Salesforce Integration Setup

For Salesforce users, the process follows similar principles but offers more complexity and customization options that reflect Salesforce's enterprise-focused architecture.

Navigate to the import action in Clay and select Salesforce. You'll follow a similar authentication process where Clay will ask you to log into your Salesforce instance and grant the necessary permissions for data access.

For Salesforce, you can choose to import from a list or static report. However, reports are capped at 2,000 records per report, so we recommend importing from lists whenever possible for larger datasets. This limitation makes list-based imports the preferred approach for most enrichment workflows.

### Salesforce Complexity Considerations

You'll notice that Salesforce has many more object types than HubSpot, reflecting its more granular data architecture. However, Contact and Account objects are typically what you'll want to pull for enrichment purposes, as these contain the core prospect and customer information.

The key difference with Salesforce is the complexity of field mapping. Salesforce allows for extensive customization, so your field names and data types might be quite different from standard objects. Take time to review the field mapping during import to ensure Clay is pulling the right data into the right columns. This upfront investment prevents downstream confusion and data processing errors.

## 🏗️ Strategic CRM Field Architecture

Here's where many teams go wrong: they treat their CRM like a dumping ground for random data points instead of architecting it strategically for enrichment workflows. Before you start enriching data in Clay, you need to create the right fields in your CRM to receive that enriched data effectively.

Poor field architecture leads to messy data, confused sales teams, and missed opportunities. Well-planned field structure creates a foundation for scalable, actionable enrichment that drives real business results.

### Field Creation Best Practices

At Clay, we follow these essential best practices for field creation and set-up:

**Prioritize Simplicity**: Try to only create fields you actually need and will actively use. Every additional field adds complexity to your data model and makes it harder for your team to find what they're looking for. Each field should have a clear purpose and expected usage pattern.

**Use Clear Naming Conventions**: Establish consistent, human-readable names for fields across your entire CRM. Avoid technical jargon or abbreviations that might confuse users. Consider prefixing Clay-enriched fields with "Clay\_" to make their source clear.

**Control Field Creation**: Avoid having too many cooks in the kitchen. Make sure your entire organization knows when and why new fields are being created. Have a standard protocol for requesting new fields and getting approval before they're added to your CRM schema.

**Organize Information Logically**: Most CRMs allow you to organize fields into sections or groups. Group all your Clay enrichment fields together so they're easy to parse and manage. This organization helps sales reps quickly find the enriched data they need.

**Ensure Data Type Compatibility**: Make sure Clay data matches your CRM field types and formatting requirements before exporting. If your CRM expects a date field, ensure Clay is sending properly formatted dates. If you need currency values, verify the format matches your CRM's expectations. This compatibility prevents import errors and data corruption.

### Example Field Architecture

There's no single correct way to structure enrichment fields, but here's how we approach it at Clay: we maintain a central repository in our CRM to store all signals data from Clay. Every enriched record connects to an Account, Contact, or both, depending on whether the data is company-level or person-level information.

This centralized approach ensures consistency while making it easy for sales reps to understand where to find different types of enriched intelligence. Company-level data like funding rounds or technology adoptions connects to Account records, while person-level data like job changes or social media activity connects to Contact records.

## ⏱️ The Setup Investment Payoff

The time you invest in proper setup now will pay dividends throughout your enrichment operations. If you rush through the setup and field architecture, you'll spend far more time later cleaning up messy data, retraining team members, and dealing with confused sales processes.

Think of this setup phase as building the foundation for a house— you want it solid and well-planned because everything else depends on it. A strong foundation supports sophisticated enrichment workflows, while a weak foundation creates ongoing operational challenges.

Remember, the goal is to get clean, organized, actionable data that your sales and marketing teams can actually use to drive measurable results. Well-structured data enables better conversations, more accurate forecasting, and ultimately more closed deals.

Next up