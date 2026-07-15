---
title: Twain
type: tool
created: 2026-07-13
updated: 2026-07-13
sources: ["[[ai-powered-gtm-automation]]"]
tags: [clay-feature, enrichment, content-creation, email-sequences, outbound]
---

# Twain

Clay's native integration for generating full multi-step email sequences with structured components. Produces complete outbound sequences (1-4 steps) with automatically decomposed elements: subject line, intro, body/value prop, CTA, and PS/signature.

## Twain vs. AI Snippets

| Dimension | [[ai-snippets|AI Snippets]] | Twain |
|-----------|-------------|-------|
| Control | Full control at sentence level | Structured but less granular |
| Speed | Slower — build each snippet separately | Faster — generates full sequence in one pass |
| Customization | Maximum — each piece independently tuned | Moderate — configure parameters, Twain handles structure |
| Multi-step | Must build each step manually | Native multi-step support (1-4 emails) |
| Best for | High-touch personalization, premium accounts | Scale outbound, consistent sequence structure |

**Decision rule:** Snippets for full control at sentence level. Twain for faster structured output at scale.

## Setup in Clay

### Pre-defined Sequences
1. Choose sequence type (1-4 steps)
2. Configure prompt parameters:
   - Prospect description
   - Outreach signal (why reaching out now)
   - ICP description
   - Problem statement
3. Add prospect info: first name, last name, social profile URL
4. Run — Twain generates all steps

### Custom Sequences (via Twain Account)
1. Create custom sequence templates in your Twain account
2. Get sequence ID
3. Reference sequence ID in Clay's Twain enrichment
4. Map Clay columns to Twain parameters

## Output Structure

Each step in a Twain sequence is automatically decomposed into:

| Component | Description |
|-----------|-------------|
| Subject Line | Hook / trigger-based subject |
| Intro Line | Personalized opening |
| Body / Value Prop | Core message and value proposition |
| CTA | Call to action |
| PS / Signature | Personal touch or follow-up note |

Each component maps to its own Clay column for easy review and editing.

## Finding Social Profiles

Twain works best with social profile URLs for personalization context. If you don't have them:
- Use [[claygent]] to find LinkedIn URLs from email addresses
- Use [[clay-find-people]] which includes LinkedIn URLs by default

## See Also

- [[ai-snippets]] — alternative: modular content generation (more control)
- [[fetc-framework]] — Twain powers the Create step
- [[personalized-outbound-pipeline]] — end-to-end implementation
- [[claygent]] — for finding social profile URLs Twain needs
