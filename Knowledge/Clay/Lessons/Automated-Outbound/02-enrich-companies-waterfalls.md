---
title: "Enrich Companies (Waterfalls) [Automated Outbound]"
source: "https://university.clay.com/lessons/enrich-companies-waterfalls-automated-outbound"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
<iframe src="https://www.loom.com/embed/28a52d1bfc30433c8ebce609d26783ca?sid=4f09a6b6-5223-4dd2-9764-470ff910b24e?hide_owner=true&amp;hide_share=true&amp;hide_title=true&amp;hideEmbedTopBar=true" frameborder="0" allowfullscreen=""></iframe>

About this lesson

00:00

## Enrich Companies (Waterfalls)

## Enriching Companies (Waterfalls) 🌊

*Note: this lesson also appears in Clay 101, Automated Inbound, and CRM Enrichment, so feel free to skim or skip if you've already seen it somewhere else  
*

### 💪 Using Waterfalls for Data Enrichment Superpowers

Once you’ve gotten your base list of Company Data into Clay, it’s time to augment that list with everything else you need to get razor sharp on your ICP, and how you’re going to reach out to them.  
  
At the company level, that data most often looks like recent news, tech stack, funding, revenue, headcount, and more. Really any technographic or firmographic data that will either help you better qualify your leads, or better personalize your messaging.

### 🧩 Data Enrichment is Just a Digital Puzzle

On first encounter, data enrichment can feel incredibly daunting. While you might know that you want to grab tech stack and revenue, you may not know how to programmatically get company websites or social URLs if your list doesn’t have them right off the bat.  
  
Luckily, because we’re starting with a Find Companies search, we already have everything we need to be successful data superheroes.  
  
But in case you’re ever feeling stuck on a specific data enrichment puzzle, just remember that all you really need to do is first find your corner pieces. Once you’ve found your corner pieces you can round out the edge with waterfalls, and then use AI Web Scraping (Claygent) to try and fill in the trickier center parts of the picture.  
  
For companies, your corner data pieces are going to be **domain** and **company social URL**. Once you have those two pieces, you can use any other company enrichment waterfall to get whatever data you need.  
  
For people, your corner data pieces are going to be **full\_name** and **contact social URL**.But we’ll dig deeper into people in a later lesson.

### 🤔 How Do Waterfalls Work?

Now that you know you can access almost any of the waterfall enrichments from your corner data pieces, it’s time to understand … what actually *is* a waterfall?

In short, a waterfall is an intelligent way to get *only* the data that you need on a row by row basis from each provider. In the pre-waterfall era, it was common practice for a revenue team to have subscriptions to between 6-12 different data providers. When you’re paying that much money for data, you want to be as frugal as possible.  
  
The best sales teams would upload their lead lists CSVs to the first data provider, then download to a google sheet, and use VLOOKUP magic to filter down to only the percentage of the list that *wasn’t* found from the first provider. From there, they then re downloaded the new CSV from the google sheet, uploaded it to the second provider, got their results, and then rinsed and repeated for up to a dozen different providers.  
  
Waterfalls take that entire manual process (faulty, often inaccurate, and no matter what - time consuming) and automate each step along the way. Let’s say we’re trying to obtain Funding Stage from our list of companies. In the Funding Stage waterfall shown below, we’ll *first* try to get that data from Intellizence. If we find the data from Intellizence, the rest of the providers won’t run. If we *don’t* find the data from Intellizence, then we’ll try Dealroom. Then Harmonic. Then Owler. Then Pitchbook.

![01:45](https://cdn.prod.website-files.com/687e604972375496b891fe58/691e4e327906ac4eaaba7f3e_66f2ed39414f1fc8d4d04432_AD_4nXcUHwkQs-kKiBth1ghMqMAHa2n88qC5YqZnlrj8a_XY0BUMSlSTumwO8Cp0MHIvnQCVYH7iv1GRsPLQ-oK_AY1kcF3YLT2kbc3hNhrxUJOtXNKJyQVjAzVTKH7tF1gXT6JpXm_F4CEEtLiTjW-soweIoKWI.jpeg)

Waterfalls help you maximize data coverage while minimizing data costs. You can have it all.

### 🤔 Understanding Waterfall Results

Once we run the fundraising waterfall, we’ll see a beautiful cascade of our waterfall data across the 5 providers we ran it with.  
  
There are a few edge cases to waterfalls worth noting. First is that while the **enrichment** might be successful, if it doesn’t have the **data point** that we want – we’ll still waterfall to the next provider, as you can see happening in row 2 below.  
  
Looking at your provider columns is the quickest way to understand how a waterfall is working, but ultimately, all the providers will feed their data into one final result column for you to use in the rest of your clay table.

![03:09](https://cdn.prod.website-files.com/687e604972375496b891fe58/691e4e327906ac4eaaba7f3b_66f2ed398093494bc50e63c0_AD_4nXfESOe_xm8cDeE0N7R4kUdE_IEUKDQjl59ruHiWNwmtq5h3ehK5Q1K6ypkOqiE2-miGrBbyhlczuNTb_5JagtbcKQyuEF7OMjHao-Q6vZhwQZAK4kvtv34pC4n0tNN-T1X-t2S3eYZHOZwB6vTDQ0z04lQC.jpeg)

With Intellizence alone, we would have 0% coverage. With Dealroom we get 70%. With Intellizence, Dealroom, and Harmonic, we reach the mythical 100%

Now that we’ve got funding stage for these companies, we could repeat this process with any other data point that’s important to our strategy. Revenue, Tech Stack, Headcount, just to name a few.  
  
Once we’ve gotten the enriched company data that we need - it’s finally time to Find People.

Next up