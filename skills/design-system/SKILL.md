---
name: design-system
description: Use when the user wants to work with Google design tools: Google Stitch (design-to-code), Material Design 3, Google Fonts, Google Maps Platform. Triggers on "google stitch", "material design", "google fonts", "maps api", "design system".
argument-hint: "SERVICE ACTION [args]"
allowed-tools: [Bash, Read, Write, WebFetch]
---

# Google Services Hub — Design System

Work with Google's design and mapping services.

## Steps

1. Read config; verify the service is enabled.
2. Route to the appropriate tool:
   - Stitch: convert designs to code
   - Material Design 3: fetch tokens, components, guidelines
   - Google Fonts: search and embed fonts
   - Maps Platform: geocoding, maps, places
3. Return results or generated code.

## Services

- Google Stitch: design-to-code conversion
- Material Design 3: design tokens and components
- Google Fonts: font catalog and CSS embeds
- Google Maps Platform: Maps, Places, Geocoding, Routes APIs