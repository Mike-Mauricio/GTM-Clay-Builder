---
title: Inbound Automation Pipeline
type: pattern
created: 2026-07-14
updated: 2026-07-14
sources:
  - "[[automated-inbound]]"
tags:
  - pattern
  - inbound
  - automation
  - speed-to-lead
  - pipeline
  - fete
---

# Inbound Automation Pipeline

End-to-end pattern for processing inbound leads automatically — from form fill to qualified, enriched lead in CRM and sequencer. The goal: a lead submits a form, and within minutes they receive a personalized, contextually relevant response from the right rep. No manual review, no data entry, no routing delays.

This pattern implements both [[fete-framework|FETE]] (Find → Enrich → Transform → Export) and [[jigsaw-framework|Jigsaw]] (corner pieces first, then fill in the picture) for inbound lead processing.

## Architecture

```
Sources → Enrich → Transform → Score → Route → Personalize → Export
```

Each stage builds on the previous one. The pipeline is designed for [[speed-to-lead]] — every step that doesn't improve routing, scoring, or personalization should be questioned.

---

## Stage 1: Sources

Inbound signals enter Clay via [[clay-webhooks]] or native integrations.

**Common sources:**
- Typeform / web forms (native integration or webhook)
- Zoom webinar registrants and attendees
- Intercom / Zendesk / Drift chat conversations
- Trial signups from product
- Content engagement events via Segment
- Blog subscribers and content downloads

### Short Form Philosophy

Only ask for **name + email** (or LinkedIn URL). Clay enriches everything else.

This isn't laziness — it's conversion math. Adding just 2 fields to a form (going from 3 fields to 5) cuts completion rates **nearly in half**. Every field you add to a form is a tax on conversion. Let the form capture intent; let Clay capture data.

If you need company, title, phone, headcount, industry — Clay can enrich all of those from an email address. Don't make the prospect do work that a machine can do better.

---

## Stage 2: Enrich

Build the full picture of each lead using Clay's enrichment stack. Follow the [[jigsaw-framework|Jigsaw]] approach: start with corner pieces (company domain, LinkedIn URL), then fill in the details.

### Enrichment Decision Tree

Use this hierarchy for every data point you need:

1. **Native enrichments first** — fast, reliable, structured data. Clay's built-in enrichments (Enrich Company, Enrich Person, tech stack lookups) should be the first option for any standard data point.
2. **AI formulas** — if the data is already in the table but needs transformation, classification, or scoring, use [[ai-formulas]] to process it. No additional enrichment credits needed.
3. **[[claygent]]** — for last-mile and niche data that neither native enrichments nor AI formulas can provide. SOC2 compliance status, recent pricing changes, blog topic analysis, review sentiment. Claygent is powerful but expensive — gate it behind qualification.

### Company Enrichment

| Enrichment | Data | Use |
|-----------|------|-----|
| Enrich Company | Firmographics, description, founded date | Baseline company profile |
| Open Jobs | Current job postings | Hiring signals, growth indicators, tech stack clues |
| Headcount Growth | Employee count trends | Growing = more budget, more pain points |
| Tech Usage (HG Insights) | Technology stack | Complementary/competing tech, integration potential |

### Contact Enrichment

| Enrichment | Data | Use |
|-----------|------|-----|
| Enrich Person | Title, seniority, experience | Role-based scoring and personalization |
| LinkedIn Profile | Full professional history | Context for personalized outreach |

### Creative Enrichments via Claygent

For niche data points that differentiate your outreach:
- SOC2 / compliance certifications
- Recent pricing model changes
- Blog content themes and publishing frequency
- G2 / Capterra review sentiment
- Recent funding or M&A activity

---

## Stage 3: Transform

Clean and standardize enriched data using [[clay-normalization-tools]] (free, no credit cost):

- **Company names** — strip Inc., LLC, Ltd., standardize capitalization
- **Whitespace** — trim leading/trailing spaces that break matching
- **Phone numbers** — consistent format for CRM import
- **Locations** — standardize city/state/country formatting

For transformations that require intelligence:
- **Job title extraction** — AI formula to parse "Senior VP of Sales & Business Development" into role = "VP Sales", seniority = "VP"
- **Headcount standardization** — convert ranges ("51-200") into categories ("SMB", "Mid-Market", "Enterprise")

---

## Stage 4: Score

Apply [[lead-scoring]] to determine conversion likelihood and priority.

**Recommended approach:**
1. Start with Clay's native **Score Row** (up to 15 criteria, generates score + reasoning)
2. Test on 10-20 rows
3. If it handles 80%+ of cases, add an AI formula as fallback for edge cases using [[conditional-runs]]

**Key scoring dimensions:**
- Seniority (C-level through intern, scored 1-10)
- Tech stack fit (complementary tools, competing tools, stack density)
- Industry classification (custom categories via AI, not generic SIC/NAICS)
- Company size and growth trajectory
- Behavioral signals (webinar attendance > form fill > blog subscribe)

---

## Stage 5: Route

Apply [[lead-routing]] to assign each qualified lead to the right rep.

Clay's native **Distribute Leads Round Robin (Weighted)** action references a rep table with names, emails, statuses, and weights. Higher weight = higher share of leads.

Rep table can sync from Salesforce on a schedule to stay current with team changes, territories, and PTO.

---

## Stage 6: Personalize

Before generating outreach, check CRM first — **Lookup** action against Salesforce/HubSpot to determine if this lead is already a contact, in an active deal, or assigned to another rep. Use the [[crm-export-dedup]] pattern to avoid messaging existing contacts or stepping on active relationships.

### Inbound Email Formula

Structure every automated inbound email with three components:

1. **Line 1 — Personalized Insight**: Pull a specific data point from enrichments. Not "I saw your company is growing" — use the actual data: "Noticed [Company] posted 3 engineering roles this month and just adopted Snowflake."
2. **Line 2 — Connect to Problem**: Bridge the insight to the problem your product solves. "Teams scaling that fast usually hit [specific pain point] around this stage."
3. **Line 3 — Clear CTA**: One specific ask. Not "Would love to chat sometime" — use "Open for a 15-min call Thursday to see if [product] fits?"

Use the [[ai-snippets]] approach: generate multiple personalization snippets per lead, then assemble the email from the best-fitting components rather than generating the full email in one shot.

---

## Stage 7: Export

Push qualified, enriched, scored, routed, and personalized leads to downstream systems:

- **CRM** (Salesforce, HubSpot) — create/update contact and opportunity records using [[crm-export-dedup]] pattern
- **Sequencer** (Outreach, Apollo, Salesloft) — auto-enroll in the appropriate sequence based on score and segment
- **Slack** — digest alerts to the sales team with lead summary, score, reasoning, and assigned rep
- **Last Enrichment Date** — stamp each record for ongoing refresh. Leads that don't convert immediately can be re-enriched later to catch new signals.

---

## 10-Step End-to-End Example

A complete inbound pipeline from Typeform to CRM:

1. **Typeform form** — name + email only (short form philosophy)
2. **Webhook to Clay** — [[clay-webhooks]] captures submission in real-time
3. **Corner piece enrichment** — Enrich Company from email domain. Get firmographics, description, headcount, industry.
4. **Deep firmographic enrichment** — Tech stack (HG Insights), open jobs, headcount growth trends
5. **Contact enrichment** — Enrich Person for title, seniority, LinkedIn profile, professional history
6. **Normalize** — [[clay-normalization-tools]] for company names, whitespace, phone formatting, locations
7. **Score** — [[lead-scoring]] with Score Row (seniority + tech fit + industry) plus AI formula fallback
8. **Personalize AI copy** — Generate email using enrichment data: insight line + problem line + CTA. Use [[ai-snippets]].
9. **Route to AEs** — [[lead-routing]] weighted round robin to assigned rep
10. **Export** — Push to CRM (create contact + log activity) and auto-enroll in sequencer. Fire Slack alert.

Total time from form submission to rep notification: **under 5 minutes** with a well-configured pipeline.

---

## Related

- [[speed-to-lead]] — the metric this entire pipeline optimizes for
- [[fete-framework]] — the enrichment framework underlying the pipeline
- [[jigsaw-framework]] — corner-pieces-first enrichment strategy
- [[lead-scoring]] — qualification layer
- [[lead-routing]] — assignment layer
- [[clay-webhooks]] — real-time signal capture
- [[ai-formulas]] — custom scoring and classification
- [[claygent]] — last-mile niche enrichment
- [[clay-normalization-tools]] — free data cleaning
- [[crm-export-dedup]] — clean CRM export
- [[ai-snippets]] — personalization approach
- [[conditional-runs]] — gating expensive enrichments
