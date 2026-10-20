---
name: workspace-apis
description: Use when the user wants to interact with Google Workspace (Drive, Docs, Sheets, Slides, Gmail, Calendar, Forms, Tasks) via API. Triggers on "google drive", "google docs", "google sheets", "gmail", "google calendar", "workspace api".
argument-hint: "SERVICE ACTION [args]"
allowed-tools: [Bash, Read, Write, WebFetch]
---

# Google Services Hub — Workspace APIs

Interact with Google Workspace services via their REST APIs.

## Steps

1. Read config; verify the requested Workspace service is enabled.
2. Obtain an access token for the Google account (OAuth, scoped to the service).
3. Execute the requested action:
   - Drive: list/create/share files
   - Docs/Sheets/Slides: read/write content
   - Gmail: list/send/search messages
   - Calendar: list/create events
   - Forms/Tasks: manage forms/tasks
4. Return structured results.

## Auth

Uses a single Google OAuth consent covering all Workspace scopes, so one sign-in covers all services.