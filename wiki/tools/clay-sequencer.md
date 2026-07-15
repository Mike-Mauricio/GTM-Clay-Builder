---
title: Clay Sequencer
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[automated-outbound]]"]
tags: [clay-feature, sequencer, outbound, email, native, activation]
---

# Clay Sequencer

Clay's native email sequencing tool that enables end-to-end outbound within Clay — no need to export data to external sequencers. Build campaigns, send personalized sequences, manage replies, and track analytics all in one platform.

## Why It Matters

Before Clay Sequencer, every outbound workflow required exporting data to an external tool (Instantly, SmartLead, SalesLoft, etc.). The native sequencer closes the loop — data stays in Clay from enrichment through delivery and reply management.

## Key Features

### Send Table Data Action
The data sync mechanism between Clay tables and campaigns. Connects your enriched prospect table to a campaign, pushing leads and personalization data.

### Clean Variables
Safe variable substitutions with fallback defaults. When personalization data is missing for a prospect, Clean Variables insert default text instead of sending broken merge tags like "{{empty}}."

### Spintax
Phrase rotation for spam filter avoidance. Example: "Hi|Hello|Hey" randomly selects one greeting per send, making emails appear less templated to email providers.

### Reply Management
- **Campaign Events Table** — Tracks all sends, opens, replies with categorization
- **Reply to Lead** action — AI auto-generates reply drafts based on the prospect's response
- **Slack Approvals** — Human-in-the-loop review before sending AI-generated replies
- **Add Email to Blocklist** — Quick action for opt-out handling
- **Global Inbox** — Cross-campaign reply monitoring

## Setup Steps

### 1. Create Campaign
Two entry points: Campaigns tab (top nav) or Actions tab from an existing table.

### 2. Source Leads
Campaign creates a Contacts Table with:
- Pre-configured email waterfall (for finding/validating emails)
- Send Table Data action (to sync leads to the campaign)

### 3. Configure Email
- Select email column (auto-detected from table)
- **HTML: OFF for cold outreach** — HTML emails hurt deliverability in cold sequences
- Write or paste AI-generated copy using [[ai-snippets]]
- Configure Clean Variables for safe fallbacks
- Add Spintax for phrase rotation

### 4. Set Up Sender
Two options:
- **SMTP** — Custom email server configuration
- **Google OAuth** — Google Workspace authentication (requires admin authorization)

### 5. Configure Scheduling
- Set timezone and business hours
- Email spacing: **~20 minutes recommended** (~24 emails/day per sender)
- Delayed start dates for staged rollouts
- Active days selection (typically weekdays only)

### 6. Launch & Monitor
- Once launched: AI snippets and core settings are **locked**
- **Pause** to edit copy mid-campaign
- **Complete** to end campaign permanently
- Monitor via Campaign Events table and Global Inbox

## Multi-Step Sequences

For multi-step campaigns, each step gets its own:
- Subject line variable
- Email body variable
- Timing configuration (delay between steps)

Use the naming convention: `subject_line_one`, `email_body_one`, `subject_line_two`, `email_body_two`, etc.

## Deliverability Best Practices

1. **HTML off** for cold outreach — plain text converts better and avoids spam filters
2. **~20 min spacing** between sends — natural sending rhythm
3. **Spintax** for phrase variation — avoids pattern detection
4. **Clean Variables** prevent broken merge tags — which trigger spam filters
5. **Inbox rotation** via multiple sender accounts — spreads volume

## When to Use vs. External Sequencers

| Scenario | Clay Sequencer | External (Instantly, SmartLead, etc.) |
|----------|---------------|--------------------------------------|
| Simple cold outbound | Yes — all in one place | Works but adds export complexity |
| Advanced deliverability tools | Basic — sufficient for most | More options (warm-up, rotation, etc.) |
| Omnichannel (email + social) | No — email only | Use [[la-growth-machine]] |
| Reply management | Yes — AI replies + Slack approvals | Varies by tool |
| Team collaboration | Global Inbox | Varies by tool |

## See Also

- [[personalized-outbound-pipeline]] — the upstream content generation
- [[ai-snippets]] — content that feeds into sequencer campaigns
- [[la-growth-machine]] — alternative for omnichannel sequences
- [[sendspark]] — complementary video outreach
- [[tavus]] — complementary AI video replicas
