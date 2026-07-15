---
title: "Finding People in Clay [Clay 101: GTM Automation]"
source: "https://university.clay.com/lessons/finding-people-in-clay"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=0-M-xpFLfEQ)

About this lesson

00:00

## Finding People in Clay

This is our next lesson in the Find phase of Clay 101! Now that you know how to find companies, let's talk about finding the right people at those companies.

People search in Clay is designed to layer on top of your company data, so you can identify and filter the right contacts based on:

- Job title
- Seniority
- Location
- …and much more

By building on your enriched company data, you can create targeted prospect lists without doing a bunch of redundant manual work.

In this lesson, we'll cover how to find and extract people data from a list of companies using Clay's Find People feature.

## 📋 Before Getting Started with Finding People

Here's what you should have:

- A list of companies in Clay. If you followed our previous lesson on Finding Companies, you should already have this.
- LinkedIn profile URLs or company domains for those companies. Remember the Jigsaw framework? These company identifiers are the "corner pieces" to find the right people
- Finally, you should also have a clear idea of your target personas. Are you looking for decision-makers in marketing? Technical users in engineering? The clearer your persona definition, the more effective your search will be.

## 🔍 Step-by-Step: Finding People

Let's start with your company list.

- Before launching a people search, make sure your company table is properly structured with key identifiers like social media URLs or domains. These identifiers are essential for accurate people search results.
- To access the Find People modal, click on the Actions button in the top-right corner of your screen and select "Find People at These Companies" from the dropdown menu.
- When the Find People modal opens, you'll see a few auto-mapped fields in the companies section:
- Table Reference: This should be the table containing your company data.
- Company Identifier: Ideally, this should be LinkedIn profile URLs, but if unavailable, you can use company domains instead.
- View Selection: Use the default view unless you need to specify a subset of companies.
- Next, define your search criteria using any of the available filters. For job titles and functions, you can use specific titles like "VP of Marketing" or broader functions like "marketing" to cast a wider net.
- Experience levels let you find contacts who have been in their role for specific time periods, like 6+ months or 1+ year.
- Location filters are useful if you want to target people in specific geographic areas.
- You can also filter by certifications like HubSpot or Salesforce, languages spoken, education background, and past experiences.
- And finally, exclusions allow you to filter out existing customers or other contacts you don't want to include.

For example, let's say we're looking for senior leaders (VPs, Directors, Heads) in revenue, marketing, go-to-market, and sales who live in New York.

Once the filters are set, preview the list of contacts that match your criteria. Take time to iterate and refine your search until you're happy with the results. There's nothing more annoying than importing a list to a table only to realize it wasn't quite right, and now you need to redo your search again.

When you're satisfied, click "Import" to add contacts to a new table in Clay.

Just like with companies, I recommend skipping default enrichments until you're confident you know what enrichments you need.

Last thing: after your initial import, you can always expand your search by clicking the source column in your People table and adjusting the filters. This adds new contacts without removing existing ones. Just remember that broader parameters (like including additional job titles) may require more cleanup later.

**Important note:** This data is a *starting snapshot* ofdata. If *live data* and *accuracy* are critical, you can use Enrich actions, e.g. Enrich People to get the most up-to-date information about a person. We'll dig more into that in future lessons.

## 🔗 The Last Piece of This Workflow: Linked Tables

One of the powerful features of Clay is how it automatically links your Find Companies table to your Find People table. This creates a relationship between the two tables that allows you to extract company attributes directly into your people table.

For example, say you wanted to reference a recent AirBnB news event for the 10 people in your list who work at AirBnB. Instead of paying credits to enrich each person (10 times total), you would do it once at the company level and pull it into your people data for all your contacts.

## 🎯 Conclusion

Using Clay's Find People feature, you can efficiently build high-quality contact lists by layering filters like job title, seniority, and location. This way, you can make sure your outreach efforts are focused on the most relevant decision-makers.

In our next lesson, we'll look at using Google Maps to find businesses you might not find in traditional B2B databases. This is perfect for targeting local service providers, retail shops, and professional practices.

Next up