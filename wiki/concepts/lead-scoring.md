---
title: Lead Scoring
type: concept
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[automated-inbound]]"
tags:
  - concept
  - scoring
  - inbound
  - qualification
  - ai-formulas
---

# Lead Scoring

Assigns a numerical value to each lead indicating conversion likelihood. Eliminates guesswork for reps — instead of reviewing every lead manually, they work the highest-scoring ones first. In an [[inbound-automation-pipeline]], scoring is the gate between enrichment and routing.

## Two Approaches in Clay

### 1. Native Score Row

Clay's built-in scoring action. Supports up to **15 scoring criteria**, auto-generates both a numerical score and a written reasoning explanation for each lead.

**Best for:** Standard scoring dimensions where you can articulate clear rules. Fast to set up, easy to iterate.

### 2. Custom AI Formula Scoring

Write a formula that uses AI to evaluate lead quality based on enrichment data already in the table. More flexible than Score Row — can handle nuanced logic, edge cases, and custom classification schemes.

**Best for:** Complex scoring that requires contextual judgment, multi-factor weighting, or domain-specific logic that Score Row can't capture in 15 criteria.

### The Hybrid Approach (Recommended)

Start with native Score Row on **10-20 rows**. Evaluate the results. If it handles 80% of cases correctly, add an AI formula as a fallback for the remaining 20% — using a [[conditional-runs|conditional run]] so the formula only fires on edge cases where Score Row's output is ambiguous or missing. This keeps credit costs low while covering the full distribution.

## Scoring Dimensions

### Seniority Scoring

| Level | Score | Examples |
|-------|-------|---------|
| C-Level | 9-10 | CEO, CTO, CFO, CRO |
| VP / Director | 7-8 | VP Sales, Director of Ops |
| Manager | 5-6 | Sales Manager, Marketing Manager |
| Individual Contributor | 3-4 | Account Executive, SDR |
| Intern / Entry | 1-2 | Intern, Associate |

### Tech Stack Fit

Score based on the number of relevant tools in the prospect's stack and whether they use complementary vs. competing technology. A company using 3 complementary tools and 0 competitors scores higher than one using 1 complementary tool and 2 competitors.

Use Clay's tech usage enrichments (HG Insights, BuiltWith) to pull stack data, then score with an AI formula that evaluates fit against your ideal stack profile.

### Industry Classification

Standard industry taxonomies (SIC, NAICS) are often too broad or misclassified. The better approach: use AI to classify companies into a **custom industry list** tailored to your ICP.

**Real-world example:** Anthropic's GTM team had Clay classify companies into their own custom industry categories using Claude as the AI model. This approach **3x'd their enrichment coverage** compared to relying on standard industry codes — because their custom categories mapped directly to their sales segments rather than generic government taxonomies.

Build this with an [[ai-formulas|AI formula]] that takes company description, website content, and any existing industry tags as input, then classifies into your custom list.

## Debugging Scoring Formulas

Clay provides an **"Output is Wrong" button** on AI formula results. Use it to flag incorrect outputs — Clay adjusts the formula's prompt based on your feedback.

If the formula is still producing bad results after several iterations:
1. Copy the full formula code from Clay
2. Paste it into Claude (or your preferred LLM)
3. Explain: "Here's my formula. For this input [paste example row data], I expected [X] but got [Y]. Fix the logic."
4. Paste the corrected formula back into Clay
5. Re-run on the problem rows to verify

## Related

- [[inbound-automation-pipeline]] — scoring sits between enrichment and routing
- [[lead-routing]] — scores determine which leads get routed and how
- [[ai-formulas]] — the engine behind custom scoring logic
- [[conditional-runs]] — run expensive scoring only on leads that need it
- [[signal-orchestration]] — multi-signal convergence for composite scores
