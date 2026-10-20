---
name: analytics
description: Use when the user wants to work with Google Analytics 4, Google Tag Manager, or YouTube Data API. Triggers on "google analytics", "tag manager", "youtube api", "ga4".
argument-hint: "SERVICE ACTION [args]"
allowed-tools: [Bash, Read, Write, WebFetch]
---

# Google Services Hub — Analytics

Work with Google Analytics 4, Tag Manager, and YouTube Data API.

## Steps

1. Read config; verify the service is enabled.
2. Use the service's REST API with the stored Google access token.
3. Return metrics, reports, or management results.

## Services

- GA4: run reports, list properties, manage audiences
- Tag Manager: manage containers, tags, triggers
- YouTube Data API: search videos, manage playlists, get channel stats