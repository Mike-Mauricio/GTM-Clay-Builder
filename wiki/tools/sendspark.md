---
title: SendSpark
type: tool
created: 2026-07-14
updated: 2026-07-14
sources: ["[[automated-outbound]]"]
tags: [external-tool, video, outbound, personalization, ai-video]
---

# SendSpark

An AI video generation tool integrated with Clay for creating personalized video messages at scale. Each prospect gets a unique video with their name, company, and custom background — generated automatically from Clay's enrichment data.

## How It Works

1. Get API credentials from SendSpark (API key + secret key)
2. In Clay, connect via credentials
3. Populate personalization fields:
   - Prospect name
   - Email address
   - Company name
   - Background URL (optional — e.g., prospect's company website)
4. Run integration
5. Wait for "success" confirmation per row
6. Extract direct video link from results
7. Include video link in outbound email or sequence

## Use Cases

- **Cold outreach differentiation** — Video stands out in crowded inboxes
- **Account-based selling** — Personalized videos for high-value targets
- **Event follow-up** — Quick personalized recap videos
- **Product demos** — Personalized walkthrough with prospect's branding

## SendSpark vs. Tavus

| Dimension | SendSpark | [[tavus\|Tavus]] |
|-----------|----------|-------|
| Approach | AI-generated personalized videos | AI replica deepfake-style videos |
| Setup | API key connection | Consent video + training (3-5 hours) |
| Personalization | Name, company, background overlay | Full script recitation by your AI replica |
| Speed | Quick generation | Minutes per video after replica created |
| Best for | Fast personalized videos at scale | Premium, high-touch personalized outreach |

## See Also

- [[tavus]] — alternative for deeper AI video personalization
- [[clay-sequencer]] — embed video links in email sequences
- [[personalized-outbound-pipeline]] — video as a Create step output
- [[ai-snippets]] — text content that can reference or complement videos
