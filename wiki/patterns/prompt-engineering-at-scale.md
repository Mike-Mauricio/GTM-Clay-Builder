---
title: Prompt Engineering at Scale
type: pattern
created: 2026-07-13
updated: 2026-07-13
sources: ["[[limitless-research]]", "[[clay-101-gtm-automation]]"]
tags: [pattern, prompting, ai, claygent, copywriting, best-practice]
---

# Prompt Engineering at Scale

Prompting Clay's AI tools (especially [[claygent]]) at scale is fundamentally different from chat-style prompting. In chat, you iterate back and forth. At scale, your prompt runs on hundreds or thousands of rows with no opportunity to clarify — it must be precise and self-contained on the first pass.

## Four Core Principles

### 1. Set Context with a System Prompt
Tell the AI who it is and what it's trying to accomplish before giving instructions:
- "You are a B2B research analyst evaluating companies for outbound sales..."
- "You are analyzing a company's website to determine if they are a good fit for [product]..."

Context sets the frame for all downstream reasoning.

### 2. Give Clear Step-by-Step Instructions
Break complex tasks into numbered steps. Don't rely on the AI to infer your process:
- "Step 1: Visit the company's About page"
- "Step 2: Identify the primary product or service"
- "Step 3: Determine if they serve B2B or B2C customers"

### 3. Specify Output Format Explicitly
Tell the AI exactly how to format its response:
- "Return only: Yes or No"
- "Format as: [Name] | [Title] | [Department]"
- "Keep output under 50 words"
- "If not found, return 'N/A' — do not explain why"

Without format constraints, AI outputs are inconsistent across rows — some return paragraphs, some return single words.

### 4. Leverage Neon Model's Multi-Column Extraction
Claygent's Neon model can return structured data across multiple columns from a single run. Instead of running 3 separate Claygent queries (one for each data point), use Neon to extract all 3 in one pass — saving 2x the credits.

## Copywriting Prompt Checklist

When using AI for writing outbound messages, follow this structure:

1. **3-5 style examples** — Show the AI what good output looks like. Real examples beat abstract descriptions.
2. **Negative exclusion criteria** — Tell it what NOT to write. "Do not use words like 'revolutionary', 'game-changing', or 'synergy'." "Do not start with 'I hope this email finds you well.'"
3. **Formatting and tone specifications** — "Casual but professional. No exclamation marks. Maximum 3 sentences."
4. **Structure and starting instructions** — "Start with a specific observation about their company. End with a question, not a CTA."

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Vague instructions ("find useful info") | Specific asks ("find the CEO's name and title") |
| No output format ("tell me about them") | Explicit format ("Return: [yes/no]") |
| No negative constraints | Add "Do NOT..." clauses |
| Assuming AI will ask for clarification | It won't at scale — be complete upfront |
| Using the most expensive model by default | Start with Neon (cheapest), upgrade only if needed |

## Relationship to Scraping

In the [[scraping-hierarchy]], prompt quality directly determines [[claygent]] effectiveness. A well-crafted prompt can often extract what you need with the cheapest model (1 credit), while a vague prompt may fail even with the most expensive model (3 credits). Invest time in prompts before spending money on model upgrades.

## See Also

- [[claygent]] — the primary tool these prompts drive
- [[ai-formulas]] — also benefit from clear prompting (for generative use cases)
- [[credit-optimization]] — better prompts = fewer retries = lower cost
- [[scraping-hierarchy]] — prompt quality determines Claygent effectiveness
