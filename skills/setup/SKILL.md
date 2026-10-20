---
name: setup
description: Use when the user wants to connect their Google account to the Google Services Hub plugin, enable Google services, or run first-time setup. Triggers on "setup google", "connect google account", "enable google services", "google login", "/google-services-hub:setup".
argument-hint: "[--services all|list]"
allowed-tools: [Bash, Read, Write, AskUserQuestion]
---

# Google Services Hub — Setup

You are setting up the Google Services Hub plugin. Walk the user through connecting their Google account and selecting which Google services to enable.

## Steps

1. **Check for existing config**: Read `.claude/google-services-hub.local.md` if it exists. If present, ask whether to reconfigure or keep current.

2. **Google account sign-in**: Ask the user to sign in with their Google account (Google AI Pro recommended). Store only an OAuth refresh token reference — never the raw token in plain text. Use the local credential store at `.claude/google-services-hub.local.md`.

3. **Service selection (wizard)**: Present all services grouped, with all pre-selected by default:
   - AI & Models: Gemini API, Google AI Studio, Vertex AI, PaLM/Codey
   - Media: Veo, Imagen, Google Flow, MusicFX/Lyria, Google Stitch
   - Cloud: Firebase, Google Cloud, Apps Script, Project IDX, Colab
   - Design: Material Design 3, Google Fonts, Google Maps Platform
   - Workspace APIs: Drive, Docs, Sheets, Slides, Gmail, Calendar, Forms, Tasks
   - Analytics: Google Analytics 4, Google Tag Manager, YouTube Data API

   Ask the user to confirm or deselect. Allow adding more later via `/google-services-hub:manage-services`.

4. **Write config**: Save selections to `.claude/google-services-hub.local.md` as YAML frontmatter with a `services:` list and `account:` field.

5. **Verify connections**: For each enabled service, do a lightweight health check (e.g. list models for Gemini, list projects for Firebase). Report successes and failures.

6. **Summary**: Print which services are enabled and how to invoke them.

## Output

A configured `.claude/google-services-hub.local.md` and a summary of enabled services.