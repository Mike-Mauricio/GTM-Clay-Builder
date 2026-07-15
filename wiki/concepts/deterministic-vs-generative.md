---
title: Deterministic vs. Generative Transformations
type: concept
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [concept, transformation, ai-formulas, clay-fundamentals]
---

# Deterministic vs. Generative Transformations

Two modes of AI transformation in Clay, each suited to different tasks. Understanding the distinction prevents over-spending on generative tools when a free deterministic tool would work.

## Deterministic Transformations

**Tool:** [[ai-formulas]] (zero credits)

Structured, rule-based operations with predictable outputs. Same input always produces the same result.

**Use when you know exactly what the result should look like:**
- Extract domain from email address
- Calculate years of experience from dates
- Format phone numbers consistently
- Create comma-separated list from structured data
- Boolean qualification flags (true/false)

**Key property:** No reasoning required. The transformation follows explicit rules.

## Generative Transformations

**Tools:** [[claygent]] (1-3 credits), Use AI enrichment (BYOK for savings)

AI reasoning, interpretation, or creation tasks where the output depends on context and judgment.

**Use when the AI needs to reason, interpret, or create:**
- Classify companies into custom industry categories
- Determine B2B vs. B2C from website language
- Write personalized email intros
- Summarize a company's value proposition
- Score lead quality with rationale

**Key property:** Requires judgment. Different inputs produce contextually appropriate (not identical) outputs.

## Decision Rule

> "If you know exactly what kind of result you want" → AI Formula (free)
> "If the AI needs to reason, interpret, or create" → Use AI / Claygent (costs credits)

## Cost Implications

This distinction is a [[credit-optimization]] strategy:

| Transformation Type | Tool | Cost |
|-------------------|------|------|
| Deterministic | [[ai-formulas]] | Free |
| Generative (with BYOK) | Use AI | ~90% cheaper than Clay credits |
| Generative (Clay credits) | Use AI / Claygent | 1-3 credits per row |

Always check: can this be done deterministically? If yes, use AI Formulas and save the credits for tasks that genuinely need reasoning.

## See Also

- [[ai-formulas]] — the deterministic transformation tool
- [[claygent]] — the primary generative transformation tool
- [[credit-optimization]] — cost implications of choosing correctly
- [[fetc-framework]] — Transform step in FETC
