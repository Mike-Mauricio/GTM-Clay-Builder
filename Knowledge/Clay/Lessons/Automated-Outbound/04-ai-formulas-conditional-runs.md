---
title: "AI Formulas + Conditional Runs [Automated Outbound]"
source: "https://university.clay.com/lessons/ai-formulas-conditional-runs-automated-outbound"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
<iframe src="https://www.loom.com/embed/12a035661ca2490f9dae1f70452cc792?sid=0019e7c1-a625-4391-a19c-be079e1fc55a?hide_owner=true&amp;hide_share=true&amp;hide_title=true&amp;hideEmbedTopBar=true" frameborder="0" allowfullscreen=""></iframe>

About this lesson

00:00

## AI Formulas + Conditional Runs

## 🧠 Unlocking the Power of AI Formulas in Clay

*Note: this lesson also appears in Clay 101, Automated Inbound, and CRM Enrichment, so feel free to skim or skip if you've already seen it somewhere else*

This might be one of the most important lessons in this course - because it’s *key* to maximizing the value that Clay provides while minimizing your costs.

AI formulas are credit-free ways to get AI to help you generate custom code in your table that can format, clean, and reshape your data exactly how you want it. We can’t tell you how many times we see users using the AI integration in place of an AI formula in a large table, which can save you hundreds, or thousands of credits.

Conditional runs (which make use of AI formulas!) are how you ensure that you only run enrichments on rows that meet your data criteria. For example, you may only want to run a personal email waterfall for rows where a work email was not found (vs. running personal emails for *all* rows). That’s where condition runs come into play.

Let’s dig in.

### 💡 The Beauty of AI Formulas

When you use enrichments like the base enriched person from profile action, you gain access to a wealth of information. This includes work experience, job titles, education history, certifications, and even volunteering experience. However, the real magic happens when you start using AI formulas to extract specific insights from this data.

Let's say you want to know the total number of educational experiences for each person in your table. Instead of manually counting or writing complex formulas, you can use an AI formula. Here's how:

1. Choose "Ask question about items with AI" from the column options.
2. Use the formula option and prompt the AI to count the total number of experiences.
3. The AI will generate the appropriate code to give you the desired output.

You can apply this same principle to count job experiences, concatenate company names, or string together job titles. The possibilities are nearly endless.  

![Adjusting the formula when the AI doesn't get it right](https://cdn.prod.website-files.com/687e604972375496b891fe58/691e4e2f0bcc3e335be46541_67461452497562c34eabd50e_66f2f3756645ee6ae1a5ebdc_AD_4nXeDShighA6YiRq5bt98amWQSSYc7Ym8hVtttaA6BU4E6JH1GbBTocQ-Wfx6fUC7lxxDOCoBKdIj3DHmAuXfnXMuseE9t-bquZkHmnkoCJ8QZYdwpkA8dcRo88CuF5FluDjNRom1w4tioYCbypiodABsEvA.jpeg)

Using AI formulas to extract all of a contact’s experience from a social profile

### 🔧 Troubleshooting AI Formulas

Sometimes, the AI might not give you exactly what you're looking for on the first try. Don't worry – this is normal and part of the process. You can iterate on your prompts, adjust the wording, or even directly modify the generated code to get the results you need. Remember, the preview feature is your friend here, helping you ensure you're getting the right data before applying the formula.

### 🔀 Mastering Conditional Runs in Clay

Conditional runs are another powerful feature in Clay that can help you optimize your data enrichment process and save credits. Let's explore how they work and how you can leverage them effectively.

### 🌊 Revisiting Waterfalls, the Original Conditional Run

You've actually already used conditional runs without even knowing it … because conditional runs are at the core of what waterfalls do! Waterfalls set up a series of enrichments that run in a specific order, with each subsequent enrichment only running if the previous ones didn't return results. This is achieved through conditional formulas running in the background. But you can modify these conditional formulas however you want to build the workflows of your dreams.

### 🛠️ Building Custom Conditional Runs

The real power comes when you start creating your own custom conditional runs. For example, let's say you want to find personal emails only for contacts where you couldn't find a work email. Here's how you might set that up:

1. Add a new enrichment for personal emails.
2. Click on "Run Settings" and then "Conditional Run."
3. Use the AI to generate a formula that only runs if the validated work email is blank.

This ensures you're not wasting credits trying to find personal emails for contacts where you already have a work email.  

![Checking the AI-generated code for conditional runs](https://cdn.prod.website-files.com/687e604972375496b891fe58/691e4e2f0bcc3e335be4653d_67461452497562c34eabd512_66f2f3736675962fb1c8f503_AD_4nXf1cQpqrWHfFwag4PqNrVo2DTPdpbUMwagcnSGwYdHdHB3Ks22_9oSFg1cDhfGvM3VCPv4xDuf3X50vdRFEHK0D4QSURwkrRCDPImmQLfaMlEyfjBCdyBR9PGxFSZKibweJ4_fo0lqQ3Fx1BDp1Jvqunn4.jpeg)

Creating a conditional run for personal emails

### 💼 Optimizing Your Workflow

By using conditional runs, you can create highly optimized workflows that only run enrichments when necessary. This not only saves you credits but also ensures you're getting the most relevant data for each contact in your database.

### 🚀 Putting It All Together

The combination of AI formulas and conditional runs in Clay provides a powerful toolkit for data enrichment and analysis. You can extract deep insights from your data, create custom enrichment flows, and optimize your credit usage – all within the same platform.

Remember, the key to mastering these features is experimentation. Don't be afraid to try different formulas, adjust your conditions, and see what works best for your specific use case. With practice, you'll be able to create sophisticated data workflows that give you exactly the information you need, when you need it.

Next up