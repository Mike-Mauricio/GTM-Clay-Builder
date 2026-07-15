---
title: ABM Architecture
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources: ["[[signals-and-abm]]"]
tags: [pattern, abm, account-based-marketing, signals, multi-table, targeting]
---

# ABM Architecture

Account-Based Marketing in Clay — precision targeting of high-value accounts using real-time intelligence, multi-channel engagement, and staged progression. ABM is spear fishing, not net casting: 100-2,000 accounts maximum, a few thousand contacts per year.

## Clay as ABM Central Nervous System

Clay serves as the unified data layer connecting first-party data, enrichment providers, [[clay-signals|intent signals]], and CRM. Intelligence operates at two levels:

- **Company level** — priorities, expansion, funding, job postings → when accounts are ready
- **People level** — new hires, role changes, champion movements → who to reach and when

## The Three ABM Stages

### Stage 1: Aware
**Entry triggers:** Social connections, social engagement, website visits, event attendance, investor intros.

**Tactics:**
- Social media auto-connect sequences
- Paid advertising
- Personalized landing pages
- Warm introductions (cross-reference exec social connections with target accounts)
- Event invitations (filter target list by location + contact grade)

### Stage 2: Interested
**Entry triggers:** Workspace creation, pricing page visits, positive replies, high-intent event attendance.

**Tactics:**
- Retargeting ads (via [[versium]] email hashes → Meta/Google audiences)
- Signal-based outbound sequences
- Webinars and case studies
- Product signal monitoring (feature usage, milestone triggers)
- Web intent tracking (time on site, multiple visits, pricing page depth)

### Stage 3: Evaluating
**Entry triggers:** Contact sales form submissions, discovery meetings booked.

**Tactics:**
- Executive dinners and referrals
- Multi-threading across the organization (use Gong to identify stakeholders mentioned in calls)
- Pre-call research briefs (auto-generated: company summary, funding, partnerships, relevant news)
- New hire tracking during evaluation (trigger immediate outreach to bring them up to speed)

## The Three-Table Architecture

Clay's internal ABM architecture — replicable for any team:

### Table 1: Named Account List
- Import contacts from CRM on schedule
- Key columns: name, normalized social URL, current ABM stage, contact grade
- Source of truth for account progression

### Table 2: Brand Mentions Tracking
- Use **Find Post Audiences** action to pull mentions of your domain
- Run daily within defined timeframe
- Classify posts with AI: built something with your product? mentioned competitor? showed buying intent?
- Enrich poster profile, normalize social URL, check company domain against CRM
- Score engagement level to prioritize follow-up

### Table 3: Lookup & Stage Updates
- Pull current ABM stage from Table 1
- Lookup social URL from Table 2
- If match meets criteria → auto-update stage → write back to CRM

This creates a **closed-loop system** where social signals automatically advance ABM stages. Reps get real-time alerts but make strategic decisions about how to engage.

## Ad Intelligence Layer

### Competitive Intelligence
Use [[adyntel]] to monitor competitor ad campaigns — creative, copy, headlines, CTAs. Combine with spend analysis to identify companies investing in advertising.

### Retargeting Flow
1. Identify social engagers or website visitors
2. Enrich and validate ICP fit
3. Get email hashes via [[versium]]
4. Filter non-ICP contacts with [[conditional-runs]]
5. Push to Meta via Clay's native ad audience export
6. Track engagement → trigger automated follow-up

## See Also

- [[clay-signals]] — signal types powering ABM detection
- [[signal-orchestration]] — combining signals for stage progression
- [[signal-based-prospecting]] — the signal → enrich → act pipeline
- [[adyntel]] — competitive ad intelligence
- [[versium]] — email hashes for ad matching
- [[personalized-outbound-pipeline]] — outreach for ABM accounts
- [[crm-enrichment-lifecycle]] — CRM data maintenance for ABM accounts
