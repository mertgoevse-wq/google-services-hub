# Google Services Hub

All-in-one Claude Code plugin for Google services. Connect once with your Google AI Pro account and use every Google service relevant to coding, building apps, and creating media — AI, media generation, cloud, design, and Google Workspace APIs.

## Services included

**AI & Models**
- Gemini API (text, code, multimodal)
- Google AI Studio
- Vertex AI (enterprise models, training)
- PaLM / Codey

**Media Generation**
- Veo (video)
- Imagen (images)
- Google Flow (workflow orchestration)
- MusicFX / Lyria (music)
- Google Stitch (UI/design-to-code)

**Cloud & Backend**
- Firebase (Auth, Firestore, Realtime DB, Hosting, Functions, Storage)
- Google Cloud (Compute, Storage, Functions, Cloud Run, BigQuery)
- Apps Script
- Project IDX (cloud dev environment)
- Google Colab

**Design & Web**
- Material Design 3
- Google Fonts
- Google Maps Platform

**Google Workspace APIs**
- Drive, Docs, Sheets, Slides, Gmail, Calendar, Forms, Tasks

**Analytics & Marketing**
- Google Analytics 4
- Google Tag Manager
- YouTube Data API

## Setup

1. Install the plugin: `cc --plugin-dir /path/to/google-services-hub`
2. Run `/google-services-hub:setup` to connect your Google account and choose which services to enable.
3. All services are pre-selected during setup; you can add/remove later with `/google-services-hub:manage-services`.

## Authentication

Uses your Google AI Pro account via OAuth. Credentials are stored locally in `.claude/google-services-hub.local.md` (gitignored). No hardcoded secrets.

## License

MIT