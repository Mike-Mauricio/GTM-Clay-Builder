---
title: "Modash integration - Clay Docs"
source: "https://university.clay.com/docs/modash-integration-overview"
author:
published:
created: 2026-07-14
description: "Discover and analyze social media creators."
tags:
  - "clippings"
---
Overview

Modash provides real-time creator data and analytics across Instagram, TikTok, and YouTube. With this integration, you can discover influencers, analyze their audience and content performance, and gather contact information — all within Clay.

## Creating a table with Modash

1. In a workbook, click `+ Add` at the bottom.
2. Search for `Modash` and select from the results.
3. In the modal, you will be asked to `Select Modash account`.
	- If you haven't already connected your Modash account, click `+ Add account` and go through authentication. Otherwise, use the Clay-provided key.

## Enriching data with Modash

1. While in a Clay table, click `Add enrichment` and search for `Modash`.
2. Under `Integrations`, select one of the Modash options.
3. In the modal, you will be asked to `Select Modash account`.
	- If you have your own account, click `+ Add account` and go through authentication. Otherwise, use the Clay-provided key.

### Action Get Instagram user info

Enrich an Instagram profile with follower count, engagement rate, bio, recent posts, and audience demographics.

**Inputs**

- **Instagram handle or profile URL:** e.g., `@username` or `https://instagram.com/username`

### Action Get Instagram user feed

Pull the most recent posts from an Instagram profile, including captions, likes, comments, and media URLs.

**Inputs**

- **Instagram handle or profile URL**

### Action Get Instagram media info

Get detailed stats for a specific Instagram post or reel, including likes, comments, views, and engagement rate.

**Inputs**

- **Instagram post URL or shortcode:** e.g., `https://www.instagram.com/p/ABC123/` or `ABC123`

### Action Get TikTok user info

Enrich a TikTok profile with follower count, video count, likes, bio, and audience demographics.

**Inputs**

- **TikTok handle, profile URL, or user ID**

### Action Get TikTok media info

Get detailed stats for a specific TikTok video, including views, likes, comments, shares, and play duration.

**Inputs**

- **TikTok video URL or video ID**

### Action Get YouTube channel info

Enrich a YouTube channel with subscriber count, video count, total views, and recent uploads.

**Inputs**

- **YouTube channel URL or channel ID**

### Action Get YouTube uploaded videos

Pull the most recent videos from a YouTube channel, including titles, views, likes, and publish dates.

**Inputs**

- **YouTube channel URL or channel ID**

### Action Get YouTube video info

Get detailed stats for a specific YouTube video, including views, likes, comments, and engagement rate.

**Inputs**

- **YouTube video URL or video ID**

### Action Get YouTube video subtitles

Extract the full transcript/subtitles from a YouTube video.

**Inputs**

- **YouTube video URL or video ID**

### Run settings

- **Auto-update:** Re-run enrichment when source data changes.
- **Only run if:** The enrichment will only run if conditions are met. [Learn more about conditional formulas](https://www.clay.com/university/lesson/ai-formulas-conditional-runs-clay-101).

## Best practices

### For enrichments

- **Handle URLs flexibly:** Clay automatically parses handles from full URLs, so you can pass `https://instagram.com/username` instead of just `@username`.
- **Use conditional runs:** Save credits by only enriching profiles that meet certain criteria (e.g., follower count > 10K).
- **Combine with AI formulas:** After pulling comments or transcripts, use Clay's AI formulas to analyze sentiment, extract themes, or summarize content.