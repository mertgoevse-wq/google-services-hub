---
name: sso
description: Use when the user wants to sign in once to Google and be authenticated for all Google services in the hub. Triggers on "sign in google", "google sso", "one login all services", "authenticate google", "/google-services-hub:sso".
argument-hint: "[--scopes all|custom]"
allowed-tools: [Bash, Read, Write, WebFetch, AskUserQuestion]
---

# Google Services Hub — Single Sign-On

Sign in once with your Google account and be authenticated for ALL enabled Google services.

## How it works

Google uses OAuth 2.0. A single consent screen can request scopes for every Google service at once. After consent, one refresh token grants access to all enabled services — no separate logins.

## Steps

1. **Read config** to see which services are enabled and which scopes they need.
2. **Build scope list**: Combine scopes for all enabled services:
   - Gemini/Vertex: `https://www.googleapis.com/auth/cloud-platform`
   - Firebase: `https://www.googleapis.com/auth/firebase`
   - Drive: `https://www.googleapis.com/auth/drive`
   - Gmail: `https://www.googleapis.com/auth/gmail.modify`
   - Calendar: `https://www.googleapis.com/auth/calendar`
   - Sheets/Docs/Slides: `https://www.googleapis.com/auth/documents`, `.../spreadsheets`, `.../presentations`
   - YouTube: `https://www.googleapis.com/auth/youtube`
   - Analytics: `https://www.googleapis.com/auth/analytics.readonly`
   - Maps/Fonts: API key (no OAuth scope needed)
3. **OAuth flow**: Open browser to Google consent URL with all scopes. User signs in once and approves.
4. **Store token**: Save refresh token to `.claude/google-services-hub.local.md` (gitignored). Access tokens are fetched on demand and cached in memory only.
5. **Verify**: Call a lightweight endpoint per service to confirm access.
6. **Report**: Print which services are now authenticated.

## Security

- Refresh token stored locally only, never committed.
- Access tokens are short-lived and held in memory.
- No passwords stored — Google handles authentication.