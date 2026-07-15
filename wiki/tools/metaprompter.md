---
title: Metaprompter
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, prompting, ai, credit-optimization, claygent]
---

# Metaprompter

Clay's built-in prompt improvement tool (the "Help me" button) that generates better prompts before you spend credits. Describe what you want in plain language, and Metaprompter writes an optimized prompt for [[claygent]] or AI enrichments.

## How It Works

1. Open any Claygent or AI enrichment column
2. Click "Help me" (Metaprompter button)
3. Describe your goal in plain language
4. Metaprompter generates an optimized prompt with:
   - Clear structure and steps
   - Output format specifications
   - Negative constraints
   - Fallback logic

## Example

**Your input:** "Write a subject line that starts with 'Congrats on' and references the person's most recent award, job change, or any other reason to celebrate."

**Metaprompter output:** A full, structured prompt with specific instructions, output formatting, and edge case handling.

## Why It Matters

Better prompts = better results on the first try = fewer retries = fewer wasted credits.

Metaprompter is a [[credit-optimization]] tool — investing a few seconds in prompt quality can save significant credits across hundreds of rows.

## When to Use

- **Before any new Claygent prompt** — Start with Metaprompter, then refine
- **When a Claygent is returning poor results** — Rewrite the prompt via Metaprompter
- **For complex extraction tasks** — Metaprompter adds structure you might miss
- **When writing classification prompts** — Metaprompter generates category definitions

## Relationship to Prompt Engineering

Metaprompter automates the principles from [[prompt-engineering-at-scale]]:
- Adds context/system prompt framing
- Structures step-by-step instructions
- Specifies output format
- Includes negative constraints

It's a shortcut to better prompts — but understanding the underlying principles still helps you refine Metaprompter's output.

## See Also

- [[claygent]] — the primary tool Metaprompter optimizes prompts for
- [[claygent-builder]] — Builder's Sculptor is a more advanced version of this concept
- [[prompt-engineering-at-scale]] — the principles Metaprompter automates
- [[credit-optimization]] — better prompts as a cost-saving strategy
