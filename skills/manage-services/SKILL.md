---
name: manage-services
description: Use when the user wants to add, remove, enable, or disable Google services in the Google Services Hub plugin, or view which services are currently enabled. Triggers on "manage google services", "add google service", "remove google service", "list enabled services", "/google-services-hub:manage-services".
argument-hint: "[--add SERVICE | --remove SERVICE | --list]"
allowed-tools: [Bash, Read, Write, AskUserQuestion]
---

# Google Services Hub — Manage Services

Add, remove, enable, or disable Google services in the configuration.

## Steps

1. Read `.claude/google-services-hub.local.md` to get current enabled services.
2. If `--list`: print enabled services grouped by category.
3. If `--add SERVICE`: add to enabled list (install any needed CLI/API dependency), verify connection, update config.
4. If `--remove SERVICE`: remove from enabled list, update config.
5. If no args: interactive menu to add/remove services.

## Available services

See `references/services-catalog.md` for the full list with setup notes.