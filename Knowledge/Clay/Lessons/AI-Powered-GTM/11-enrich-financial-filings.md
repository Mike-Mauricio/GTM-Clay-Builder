---
title: "Enrich from Financial Filings [AI-Powered GTM Automation]"
source: "https://university.clay.com/lessons/enrich-from-financial-filings"
author:
published:
created: 2026-07-13
description:
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=eyF5YJFM3-U)

About this lesson

00:00

## Enrich from Financial Filings

Now that we've covered enriching images and screenshots, it's time for one more AI enrichment lesson, this one focusing on **financial filings**. This is one of my favorite integrations, and it couldn't be simpler to use.

## 🎯 Why You'd Enrich from Financial Filings

Let's say you're reaching out to operations leaders at a public company. Instead of guessing what their pain points are, you can ask Oakie AI to pull recent insights from their 10-K or 10-Q—like mentions of cost-saving initiatives or upcoming tech investments.

That gives you real material to tailor your message and start a meaningful conversation. You only need a few key data points from a 10-K or 10-Q to ground a conversation around what leadership actually cares about.

<iframe src="https://demo.arcade.software/Ho9XWMMoxUyV1o2MNypM?embed&amp;embed_mobile=tab&amp;embed_desktop=inline&amp;show_copy_link=true" title="Enrich from Financial Filings" frameborder="0" allowfullscreen=""></iframe>

## 📝 Step-by-Step Process with Oakie AI

Here's how you would use Clay and the Oakie AI enrichment to gather insights from any public company's financial statements:

1. **Start with your list of public companies**
2. **Use the waterfall enrichment** to get company domain names (pulls from Clearbit, Google, and other sources)
3. **Find each company's stock ticker using Claygent**:
	- Go to Enrich and select Claygent
		- Use the Meta prompter with this prompt: "Help me find the stock ticker for this company from this domain"
		- Input the domain and run the enrichment

Once you have the stock ticker, you can use the Oakie AI enrichment to analyze the financial documents:

1. **Set up the Oakie AI enrichment**
2. **Input the stock ticker**
3. **Specify the date range and filing type** (10-K or 10-Q)
4. **Enter your questions about the company**
5. **Run the enrichment**

## 💪 Making the Data Actionable

The initial output will be comprehensive but lengthy. To make it more actionable:

1. **Use AI to summarize the findings**
2. **Use the Meta prompter** to write your prompt
3. **Ask it to "Extract three key insights about challenges this company is facing"**
4. **Map the key points to separate columns** once you get the results

Now you have three clear, focused insights about the company that you can use in executive meetings or outbound messaging.

## 🔄 Oakie AI vs. Claygent: When to Use Each

A common question we get is: **Can you just use Claygent to accomplish the same thing as Oakie AI?**

The answer is **yes—but with some tradeoffs.**

If you need just **a few high-confidence insights** from a company's 10-K or 10-Q, and you're working with public companies, **Oakie AI is usually the better option**. It's more reliable, faster, and doesn't require finding the 10-K yourself.

But if you want to **ask multiple questions**, pull data in a specific format, or get more control over how the output is structured, **Claygent gives you that flexibility** —as long as you're okay with a little extra setup and the risk of not finding the 10-K every time with Claygent.

## 🎆 Conclusion

To recap:

- **Use Oakie AI** for **accuracy and simplicity**
- **Use Claygent** for **depth and customization**

Pick the tool that fits the workflow you're building.

## 🔜 What's Next

That completes our coverage of the Enrich step in the FETC framework. In the next lesson, we'll move onto the third piece of FETC ("fetch"): Transform.

Next up