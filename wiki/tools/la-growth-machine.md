---
title: La Growth Machine
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[automated-outbound]]"]
tags: [external-tool, sequencer, omnichannel, outbound, twitter, email]
---

# La Growth Machine (LGM)

An omnichannel sequencing tool that integrates with Clay for messaging across email, Twitter, and other platforms in a single campaign. Fills a gap the [[clay-sequencer]] doesn't cover — multi-platform outreach sequences.

## When to Use

- **Omnichannel outreach** — Reach prospects on email AND social platforms in one coordinated sequence
- **High-value prospects** — Reserve omnichannel for top-tier targets (social platform limits constrain volume)
- **ICP active on Twitter** — Only add Twitter if your ICP actually uses it (startup founders, software companies)

## Setup in Clay

1. **Link identities in LGM** — Connect Twitter, email accounts, complete platform verifications
2. **Create custom audiences** per campaign in LGM
3. **In Clay:** Add LGM enrichment with API key
4. **Select audience** matching the target campaign
5. **Input lead info** (name, email, social profiles)
6. **Map Clay's AI-generated messages** to LGM custom attributes
7. **Run** to push personalized leads and copy to LGM

## Channel Strategy

| Channel | Best For | Limits |
|---------|----------|--------|
| Email | Primary outreach, all prospects | Standard deliverability limits |
| Twitter/X | Startup founders, tech community, thought leaders | Platform rate limits, connection required |
| LinkedIn | Professional B2B outreach | Connection request limits |

**Key principle:** Only use channels where your ICP is active. Adding Twitter to a campaign targeting healthcare executives wastes effort.

## Omnichannel vs. Single-Channel

| Approach | Volume | Conversion | Best For |
|----------|--------|-----------|----------|
| Email only ([[clay-sequencer]]) | High | Good | Scale outbound |
| Omnichannel (LGM) | Lower (social limits) | Higher per-touch | High-value accounts |

## See Also

- [[clay-sequencer]] — Clay's native email-only sequencer
- [[personalized-outbound-pipeline]] — upstream content generation
- [[ai-snippets]] — content that feeds LGM custom attributes
