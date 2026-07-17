---
title: "Guide: Finding companies and people in Clay"
source: "https://university.clay.com/docs/finding-companies-and-people-in-clay"
author:
published:
created: 2026-07-14
description: "Best practices to Clay's company and people search features."
tags:
  - "clippings"
---
Overview

Clay's `Find Companies` and `Find People` sources give you instant access to billions of company and people profiles — all in one place. Here are the best practices we recommend to streamline your searches and surface the strongest results.

## Excluding companies and people

You can exclude up to **150,000 companies or people** from any company or people search by adding up to **three exclusion sources**. Each exclusion source can be one of:

- A Clay table
- A comma-separated list of URLs (e.g., LinkedIn profile or company page URLs)
- A CSV file

**Identifiers to use:**

- For companies: domain or LinkedIn URL
- For people: LinkedIn URL

This is the current way to suppress your existing CRM or list against new searches. In the future, Audiences will allow you to exclude an entire synced CRM instance (e.g., all of Salesforce) in one step.

## Limitations

**Geographic coverage**

**United States:** Highest data quality and coverage.

**International (EMEA/APAC):**

- Expect 15–25% lower coverage than US
- Phone numbers especially may have limited availability
- Europe/DACH regions may require adjusted expectations

**Company segments with lower data quality**

- SMB businesses (especially those with limited social profiles)
- Agencies
- Companies with minimal online presence

## Troubleshooting

### Find People returns fewer results than expected

Clay uses stored snapshot data rather than live LinkedIn search, so results will never be a perfect mirror of what LinkedIn shows on a company's people page. Common causes:

- **Private or restricted profiles** — Clay can only surface profiles that are accessible in the stored dataset. Profiles set to private on LinkedIn are excluded.
- **Domain-to-company mapping issues** — when you provide a domain instead of a LinkedIn URL, Clay resolves it through a company lookup that can occasionally return the wrong entity, especially for subsidiaries, rebranded companies, or companies with stale LinkedIn slugs. Switch to the **LinkedIn company URL** as your input to bypass this lookup entirely.
- **Filters set too narrowly** — title, location, or seniority filters that are too specific can exclude real matches. Try broadening one filter at a time to diagnose where results drop off.

If profiles still appear to be missing after switching to LinkedIn URLs, use **Claygent** to find the missing profiles via Google search, then pass those LinkedIn URLs directly into `Enrich Person`. This uses a live-scraping fallback that isn't constrained by the stored dataset.

### Find People is returning people from the wrong company

This almost always points to a domain-to-company mapping issue. When Clay resolves a domain to a LinkedIn company, it can occasionally surface a parent company, subsidiary, or a generic LinkedIn company page instead of the intended one. Use the company's **LinkedIn URL** as the input instead of the domain to ensure Clay maps to the exact intended entity.

## FAQs

### Why is this person showing up despite having moved companies?

Clay's company and people search relies on snapshot data that may lag behind real-time changes. To confirm current employment, run `Enrich Person` and use the formula in the **Verify current employment** section above to check whether the company matches.

### Why am I finding people with unexpected job titles?

First, check that you're filtering on **Job title keywords** (not just function or seniority). If you're using **Is similar to** mode, you may get some fuzzy matches — filter those out with a formula or AI after the fact.

### Why isn't someone I found on LinkedIn showing in Clay?

Your search filters may be too specific. Try broadening your criteria incrementally. The profile may also not yet be in the dataset.

### How often is company and people data updated?

High-importance profiles (frequently accessed records, decision-makers, active companies) are updated much more frequently. The full universe of long-tail profiles is updated regularly, though high-importance profiles refresh more frequently.

Table of contents

[

Company search

](#company-search)[Anchor on description keywords](#anchor-on-description-keywords)[Use AI filters to avoid paying for data you won't use](#use-ai-filters-to-avoid-paying-for-data-you-wont-use)[Understand how filters combine](#understand-how-filters-combine)

[

People search

](#people-search)[Choose your starting point](#choose-your-starting-point)[Build job title lists instead of relying on the function dropdown](#build-job-title-lists-instead-of-relying-on-the-function-dropdown)[Choose the right title match mode](#choose-the-right-title-match-mode)[Use LinkedIn URLs, not domains, as company identifiers](#use-linkedin-urls-not-domains-as-company-identifiers)[Run conditional people searches with table views](#run-conditional-people-searches-with-table-views)[Source vs. enrichment — when to use each](#source-vs-enrichment-when-to-use-each)[Use dynamic location filtering with in-table actions](#use-dynamic-location-filtering-with-in-table-actions)[Verify current employment before using results](#verify-current-employment-before-using-results)[Excluding companies and people](#excluding-companies-and-people)[Limitations](#limitations)

[

Troubleshooting

](#troubleshooting)[Find People returns fewer results than expected](#find-people-returns-fewer-results-than-expected)[Find People is returning people from the wrong company](#find-people-is-returning-people-from-the-wrong-company)

[

FAQs

](#faqs)[Why is this person showing up despite having moved companies?](#why-is-this-person-showing-up-despite-having-moved-companies)[Why am I finding people with unexpected job titles?](#why-am-i-finding-people-with-unexpected-job-titles)[Why isn't someone I found on LinkedIn showing in Clay?](#why-isnt-someone-i-found-on-linkedin-showing-in-clay)[How often is company and people data updated?](#how-often-is-company-and-people-data-updated)[Can I run a people search only on companies that meet certain criteria?](#can-i-run-a-people-search-only-on-companies-that-meet-certain-criteria)[What's the difference between the people search source and the enrichment action?](#whats-the-difference-between-the-people-search-source-and-the-enrichment-action)