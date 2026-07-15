---
title: Clay Signals
type: concept
created: 2026-07-14
updated: 2026-07-14
sources: ["[[signals-and-abm]]"]
tags: [concept, signals, intent, monitoring, real-time, proactive-gtm]
---

# Clay Signals

Dynamic monitoring systems that detect buying intent in real-time. Signals transform GTM from reactive prospecting (finding companies that fit your ICP) to proactive opportunity capture (catching them at the exact moment they're ready to buy).

## The Timing Problem

In B2B sales, timing is everything. Perfect product-market fit and compelling value props don't matter if you reach out at the wrong time. Signals solve this by identifying the exact moment a company transitions from not needing your solution to actively looking for one.

## Evolution of Signal Detection

| Era | Approach | Limitation |
|-----|----------|-----------|
| **Manual Research** | Reps scroll social media, set Google alerts | Caps at 20-30 accounts, inconsistent |
| **Intent Data** | Buy lists of accounts searching keywords | Reactive — by the time they're searching, they're evaluating competitors |
| **Automated Intelligence** | Clay monitors for business events proactively | Catches needs before prospects realize they should evaluate solutions |

## The Four Categories of B2B Signals

### Intent Signals
Companies researching your category, visiting competitor sites, downloading relevant content. Valuable but **late-stage** — prospects are already comparing solutions.

### Growth Signals
Companies scaling rapidly, creating immediate needs:
- Funding announcements → new budget
- Aggressive hiring → need new tools
- New office openings → expansion
- Web traffic increases → need infrastructure

### Change Signals
Transitions that create new needs and disrupt vendor relationships:
- Leadership changes (new CMO, CTO, VP Sales)
- Technology migrations
- Organizational restructuring
- New business line launches

### Distress Signals
Challenges that create urgency and openness to switching:
- Negative reviews mentioning specific pain points
- Compliance violations
- Public complaints about current vendors
- System outages revealing infrastructure problems

## Default vs. Custom Signals

### Default Signals (Pre-Built)
Clay's greatest hits — enterprise-grade monitoring out of the box:
- **Career Movement** — job changes, new hires, promotions, layoffs, relocations
- **News & Fundraising** — funding rounds, M&A, partnerships, product launches
- **Job Postings** — hiring patterns revealing expansion, budget, tech adoption
- **Brand Mentions** — competitor discussions, customer sentiment, partnership signals
- **Website Intent** — page visits, content engagement, pricing page interactions
- **Customer Sentiment** — G2/Capterra/TrustRadius reviews, feature requests, churn indicators

### Custom Signals (User-Built)
Monitor anything digitally accessible — proprietary intelligence competitors can't replicate:
- Tech stack changes (CRM migrations, new tool adoptions)
- Compliance/certifications (SOC2, HIPAA, ISO)
- Geographic expansion (new offices, international hiring)
- Website content changes (pricing updates, team page additions)
- First-party data (product usage via Snowflake, Gong conversation topics)
- Financial filings (SEC, revenue guidance, executive compensation)
- Engineering density (GitHub activity, technical job postings)

Custom signals are the source of [[gtm-alpha]] — they detect opportunities everyone else misses.

## Signal Prioritization Matrix

Plot signals on two dimensions:
- **Frequency** — how often does this signal occur in your target market?
- **Conversion potential** — how likely does this signal lead to a sale?

Signals scoring high on both are golden opportunities — prioritize building these first.

## Real-World Examples

**Vanta:** Monitors funding announcements, security engineer hiring, and SOC2-related content. Reaches out at the exact moment companies realize they need compliance automation — often before they know solutions like Vanta exist.

**Canva:** Uses AI to analyze social media posts for brand inconsistencies (inconsistent fonts, off-brand colors, misaligned logos). Engages heads of brand/design within hours of problematic content posting.

## See Also

- [[signal-orchestration]] — combining multiple signals for higher-intent detection
- [[signal-based-prospecting]] — the pattern for signal → enrich → qualify → act
- [[gtm-alpha]] — custom signals as competitive advantage
- [[abm-architecture]] — signals powering account-based marketing
- [[conditional-runs]] — gating enrichments based on signal qualification
