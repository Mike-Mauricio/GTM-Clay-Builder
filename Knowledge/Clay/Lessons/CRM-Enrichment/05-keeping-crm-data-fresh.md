---
title: "Keeping your CRM data fresh [CRM Enrichment]"
source: "https://university.clay.com/lessons/keeping-your-crm-data-fresh-crm-enrichment"
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

![](https://www.youtube.com/watch?v=Ex__8pCeD4g)

About this lesson

00:00

## Keeping your CRM data fresh

## Introduction

In our previous lesson, we went over how to enrich CRM data with Clay’s native enrichments as well as Claygent to find that last-mile data. Now, we're tackling a critical challenge that every revenue team is familiar with: keeping your CRM data fresh and up-to-date without constant manual maintenance.

Data gets stale incredibly fast. Contact information changes, people switch jobs, companies evolve their tech stacks, and organizational structures shift. If you're not actively refreshing your CRM data, you're essentially operating with outdated intelligence that undermines your entire go-to-market strategy.

In this lesson, we'll walk through how to set up dynamic contact lists that automatically identify when your data needs refreshing, then use scheduled imports to keep everything current. By the end, you'll have a self-maintaining system that ensures your team is always working with the freshest possible data without any manual intervention.

## 📝 Creating Dynamic Refresh Lists in Your CRM

The foundation of automated data freshness is leveraging your CRM's dynamic list capabilities to automatically identify contacts that need attention. This approach transforms reactive data maintenance into proactive intelligence management.

### Setting Up Your Dynamic List

Within your CRM, create an active or dynamic list and name it something like "Contacts Due for Enrichment Refresh” to make it clear what the list does and helps with organization as you scale your automation.

Set up your filter criteria to identify outdated data systematically. For example, create a custom field called “Last enrichment date” then filter for "Last enrichment date is more than 30 days ago." You can adjust this timeframe based on your data velocity needs.

Tip: Last enrichment date is a custom field that Clay will update— this is different from Last Modified Date or similar fields in SFDC. Make sure to adapt your naming conventions accordingly to avoid confusion.

The beauty of this dynamic approach is that your CRM automatically identifies which contacts need fresh data without any manual list building or remembering to check data staleness. The list continuously updates itself based on your defined criteria.

### Advanced Filtering Logic

Consider layering additional criteria beyond just time-based filters. You might want to prioritize refreshing contacts who are currently in active deals, have high lead scores, or belong to target account lists. This ensures your most important data gets the most frequent attention.

You can also exclude certain contact types from automatic refreshing if they don't require current data—for example, closed-lost prospects or contacts marked as do-not-contact might not need regular enrichment updates.

## 🔄 Automated Import and Scheduling

Now we'll set up Clay to automatically import contacts from your dynamic CRM list, creating a seamless flow from identification to enrichment without manual intervention.

### Clay Import Configuration

In Clay, click "Import" and select your CRM integration (HubSpot or Salesforce) to connect to your dynamic list.

Select the dynamic list you just created and map the fields you want to import. Make sure to include essential identifiers like contact ID, email, name, and your last enrichment date field. These fields provide the foundation for both enrichment and tracking.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/691f506c9cc67d16ef77a120_689ffb7d15994f417999d312_Screenshot%25202025-08-15%2520at%252011.30.22%2520PM.png)

Running your CRM import on a schedule (can be found by clicking Edit Source in your import column)

### Scheduling Strategy

In the run settings (either right click on your import column header or navigate to Table Settings at the bottom right corner), configure your source to run on a schedule that aligns with your data freshness requirements.

Clay will now automatically check your dynamic CRM list and import any new contacts that have aged into the refresh window. As contacts naturally age out of your freshness criteria, they'll automatically join the list and get queued for refreshment.

## 🔧 Processing and Updates

Once contacts are imported for refreshing, you need systematic processes to enrich them and push updates back to your CRM while maintaining proper tracking.

## 📅 Last Enrichment Date

How do you know which date to map in as your Last Enrichment Date?

The refresh/update date is included in metadata for each enrichment. If you're running an enrichment like Enrich company or Enrich person, you can just right click and pull out Last Refresh Date. Make sure to right click and convert in to a Date field if that's what your CRM field expects.

![](https://cdn.prod.website-files.com/687e604972375496b891fe58/691f506c9cc67d16ef77a127_68c0b2baedc189c0e424171b_Screenshot%25202025-09-09%2520at%25207.04.26%25E2%2580%25AFPM.png)

Create a formula column that standardizes the enrichment date to match your CRM's expected format. This ensures clean data integration and proper tracking of refresh cycles.

After enriching your contacts with fresh data through your standard enrichment workflows, use Clay’s Create or Update action to push the updated information back to your CRM. Crucially, make sure to update the "Last enrichment date" field so the contact exits the refresh queue and won't be re-enriched until the next cycle.

If you're only using Claygent enrichments, you might need an extra step to find the last refresh date.

<iframe src="https://demo.arcade.software/wxj23t319y928aZnveeA?embed&amp;embed_mobile=inline&amp;embed_desktop=inline&amp;show_copy_link=true" title="Add and Configure a Formula Column in Your Data Table" frameborder="0" allowfullscreen="" allow="clipboard-write"></iframe>

## ⚙️ The Automated System in Action

Once this infrastructure is set up, your system operates completely hands-off, creating a self-maintaining data environment that scales with your business.

- Every day (or on whatever schedule you've configured), Clay automatically checks your CRM's dynamic list for contacts that need refreshing. New contacts that have aged into your refresh window get automatically imported without any manual intervention.
- These contacts flow through your enrichment workflows to gather fresh data from current sources. Updates get pushed back to your CRM with current information, and the last enrichment date gets updated to reset the refresh cycle.
- The system continues this cycle automatically, ensuring your data freshness without any ongoing manual management or remembering to run updates.

This approach scales effortlessly with your database size. Whether you have hundreds or hundreds of thousands of contacts, the system operates on the same principles and automatically handles the volume through systematic processing.

## 🔧 Advanced Implementation Considerations

As you implement and optimize your dynamic refresh system, consider these advanced strategies for maximum effectiveness.

### Segmented Refresh Cycles

You might want different refresh frequencies for different contact types. VIP prospects and active opportunities might need monthly refreshes, while broader prospect databases might only require quarterly updates. Create multiple dynamic lists with different time criteria to support these varying needs.

You can also layer in additional triggers beyond time-based criteria. For example, automatically refresh contacts when they change companies, receive promotions, or when your sales team marks them as high priority for specific campaigns.

### Selective Data Refreshing

Consider which data points actually require regular updating. Contact information like emails and phone numbers change frequently and benefit from regular refreshment, but static information like educational background or company founding dates probably don't need monthly updates.

Focus your refresh workflows on data points that change frequently and impact your sales effectiveness, optimizing both cost and system performance.

## 📊 Systematic vs. Reactive Data Management

The key insight here is that data freshness should be systematic and proactive, not reactive and crisis-driven. Most teams only realize their data is stale when emails bounce, phone calls fail, or outreach efforts fall flat due to outdated information.

By then, you've already lost opportunities, wasted time on ineffective outreach, and potentially damaged relationships through irrelevant communications based on stale data.

### Proactive Intelligence Management

This dynamic refresh system flips that reactive model entirely. You're proactively maintaining data quality before it becomes a problem, ensuring your team always has the intelligence they need for effective engagement.

Your CRM transforms from a static repository that slowly degrades over time into a living, breathing database that automatically maintains itself and continuously improves in quality and relevance.

Next up