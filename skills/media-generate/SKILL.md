---
name: media-generate
description: Use when the user wants to generate media (images, videos, music) using Google services (Imagen, Veo, MusicFX/Lyria, Google Flow). Triggers on "generate image", "generate video", "create music", "make a banner", "create logo", "media generation".
argument-hint: "TYPE PROMPT [--service veo|imagen|flow|lyria]"
allowed-tools: [Bash, Read, Write, WebFetch]
---

# Google Services Hub — Media Generation

Generate images, videos, and music using Google's media generation services.

## Steps

1. Determine media type: image, video, or music.
2. Determine service: Imagen (image), Veo (video), Lyria/MusicFX (music), Google Flow (orchestrated pipelines).
3. Check service is enabled in config; if not, prompt to enable.
4. Build the request with the user's prompt and any parameters (aspect ratio, duration, style).
5. Execute via the service API.
6. Save output to a sensible location (e.g. `./media/`) and report path + preview.

## Examples

- `/google-services-hub:media-generate image "a mountain landscape at sunset"` → Imagen
- `/google-services-hub:media-generate video "a drone shot over a city"` → Veo
- `/google-services-hub:media-generate music "upbeat electronic track"` → Lyria