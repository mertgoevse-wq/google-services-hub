---
name: use-service
description: Use when the user wants to use a specific Google service from the hub, e.g. generate an image with Imagen, create a video with Veo, query Gemini, deploy to Firebase, or call any Google API. Triggers on "use gemini", "generate image", "generate video", "deploy firebase", "google api", service names.
argument-hint: "SERVICE [args...]"
allowed-tools: [Bash, Read, Write, WebFetch]
---

# Google Services Hub — Use Service

Invoke a specific Google service from the enabled set.

## Steps

1. Read `.claude/google-services-hub.local.md` to confirm the service is enabled. If not, suggest enabling it via `/google-services-hub:manage-services`.
2. Route to the appropriate service handler based on the service name.
3. Execute the requested action using the service's API/CLI.
4. Return results and any follow-up suggestions.

## Routing

- `gemini` / `ai` → Gemini API (text, code, multimodal)
- `veo` → Veo video generation
- `imagen` → Imagen image generation
- `flow` → Google Flow workflow
- `stitch` → Google Stitch design-to-code
- `firebase` → Firebase CLI
- `gcp` → gcloud CLI
- `workspace` → Google Workspace APIs (Drive, Docs, Sheets, Gmail, Calendar)
- `maps` → Google Maps Platform
- `analytics` → Google Analytics 4
- `youtube` → YouTube Data API