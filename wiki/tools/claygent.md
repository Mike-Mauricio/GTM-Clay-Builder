---
title: Claygent
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[clay-101-gtm-automation]]", "[[limitless-research]]", "[[ai-powered-gtm-automation]]"]
tags: [clay-feature, ai, web-scraping, enrichment, last-mile-data, scraping-hierarchy]
---

# Claygent

Clay's AI-powered web scraper that solves the "last mile data problem" — finding custom, niche data points that no traditional enrichment provider collects. Unlike static database lookups, Claygent browses websites in real time to answer specific questions.

## How It Works

1. You write a natural language prompt describing what to find
2. Claygent visits the specified URL(s) — company website, LinkedIn profile, etc.
3. It reads page content and extracts the answer
4. Results are returned to the Clay column with confidence scores

## Model Selection

Claygent offers multiple AI models, each optimized for different tasks:

| Model | Best For | Key Advantage |
|-------|----------|--------------|
| **Neon** (flagship) | Structured extraction, multi-column output | Formats results into multiple columns from a single run — saves credits by extracting several data points in one pass |
| **Helium** | Simple lookups, yes/no questions | 1 credit — cheapest option for basic extraction |
| **Argon** | Complex reasoning, multi-source analysis | 3 credits — for tasks requiring deep judgment |
| **GPT-4** | Complex reasoning, nuanced analysis | Strong at interpreting ambiguous or context-heavy content |
| **Claude Opus** | Complex reasoning, detailed research | Strong at synthesis and multi-step analysis |

**Default to Neon** for most extraction tasks. Its multi-column output is a significant credit saver — instead of running 3 separate queries for 3 data points, Neon extracts all 3 in one pass. Escalate to GPT-4 or Claude only when the task requires complex reasoning that Neon can't handle.

## Credit Tiers

| Tier | Credits | Best For |
|------|---------|----------|
| Simple (1 credit) | 1 | Yes/no questions, single data point extraction |
| Moderate (2 credits) | 2 | Multi-step analysis, cross-page research |
| Complex (3 credits) | 3 | Deep research, synthesis across multiple sources |

Always start with the cheapest tier that can handle the task. Upgrade only if results are incomplete.

## Preset Templates

Claygent includes a library of preset prompt templates for common tasks (e.g., finding 10-K reports, identifying decision-makers, extracting pricing info). Access via the enrichment panel under Tools > AI. Use presets as starting points — then refine with negative constraints and output control per [[prompt-engineering-at-scale]].

## Input Requirements

**For companies:**
- Domain (required)
- LinkedIn URL, category tags (optional, improves accuracy)

**For people:**
- LinkedIn URL (required)
- Name, company, title (optional context)

## Prompt Engineering

### Structure
Use second person ("Visit this company's website and...") with clear instructions and constraints.

### Negative Constraints (Critical)
Always specify what NOT to return. Claygent will over-include without guardrails:
- "Do NOT return the CEO"
- "Do NOT return anyone with 'intern' in their title"
- "Do NOT include information from social media profiles"

### Fallback Logic
Handle missing data gracefully:
- "If they haven't posted recently, summarize their About section instead"
- "If no pricing page exists, return 'Not found'"

### Output Control
Manage token usage and column size:
- "Keep output under 50 words"
- "Return only the job title, nothing else"
- "Format as: [Name] - [Title]"

### Metaprompter
Use the "Help me" button to auto-generate prompts. Good starting point — then refine with negative constraints and output control.

## Example Prompt

```
Visit this company's homepage. Does it offer a free trial?
Return "Yes" if they mention free trial, demo, or trial period.
Return "No" if no trial is mentioned.
Do NOT include pricing information.
Keep output to one word.
```

## Common Use Cases

| Use Case | What Claygent Finds |
|----------|-------------------|
| B2B vs B2C classification | Business model from website content |
| Integration detection | Whether a company uses specific tools |
| Value proposition extraction | How a company describes what they do |
| Technology mentions | Specific tech mentioned on site |
| Free trial availability | Whether free trial/demo is offered |
| Recent news/updates | Latest company announcements |
| Leadership identification | Specific roles from team pages |

## When to Use vs. Standard Enrichments

| Scenario | Use Standard Enrichment | Use Claygent |
|----------|----------------------|--------------|
| Company headcount | Yes — database has it | No |
| Company funding | Yes — database has it | No |
| Work email | Yes — [[clay-email-waterfall]] | No |
| "Do they have a free trial?" | No database tracks this | Yes |
| "What integrations do they list?" | No database tracks this | Yes |
| "What's their latest blog topic?" | No database tracks this | Yes |

Claygent is for [[jigsaw-framework|fill data]] — the specialized layer that creates [[gtm-alpha]].

## Claygent Builder

[[claygent-builder|Claygent Builder]] provides a centralized environment for building, testing (free), and deploying Claygent agents. Build once with Sculptor (natural language agent creation), test without consuming credits, and deploy across multiple tables — changes propagate everywhere. See [[claygent-builder]] for full details.

## Position in Scraping Hierarchy

From [[scraping-hierarchy]]:
```
**Claygent** → Zenrows → Apify → Native Scraper → Chrome Extension
```

Claygent is the **first tool to reach for** when you need data from the web. Only escalate to [[zenrows]] (anti-bot bypass), [[apify]] (platform-specific), [[clay-native-scraper]] (simple/cheap), or [[clay-chrome-extension]] (visual browser) when Claygent isn't the right fit.

## See Also

- [[scraping-hierarchy]] — Claygent's position as the default scraping tool
- [[prompt-engineering-at-scale]] — how to write effective Claygent prompts
- [[jigsaw-framework]] — Claygent handles the fill layer
- [[gtm-alpha]] — the competitive advantage Claygent enables
- [[credit-optimization]] — managing Claygent credit spend
- [[ai-formulas]] — credit-free alternative for data already in Clay
