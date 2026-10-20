---
name: cloud-deploy
description: Use when the user wants to deploy, host, or manage applications on Google Cloud or Firebase (Cloud Run, Firebase Hosting, Functions, App Engine, GKE). Triggers on "deploy to firebase", "deploy to cloud run", "host on google cloud", "firebase deploy", "gcp deploy".
argument-hint: "TARGET [path]"
allowed-tools: [Bash, Read, Write]
---

# Google Services Hub — Cloud Deploy

Deploy and manage applications on Google Cloud Platform and Firebase.

## Steps

1. Read config; verify the target service (Firebase / GCP) is enabled.
2. Detect project type (Node, Python, static, container).
3. Run the appropriate deploy command:
   - Firebase Hosting: `firebase deploy --only hosting`
   - Firebase Functions: `firebase deploy --only functions`
   - Cloud Run: `gcloud run deploy`
   - App Engine: `gcloud app deploy`
4. Report URL and status; offer rollback if needed.

## Prerequisites

- `firebase-tools` CLI or `gcloud` CLI installed and authenticated.
- Project configured (`firebase init` / `gcloud config set project`).