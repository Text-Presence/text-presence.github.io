---
layout: home
title: Text Presence Core
nav_order: 1
description: Text Presence Core — a runtime/framework for application presence.
---

# Text Presence Core

**Presence that comes from the application.**

TPC is a **presence runtime/framework** for detecting application state, connecting it to a target definition, and exposing that state to presence clients.

It is designed to sit between an application and a presence representation:

```
Application
    ↓
TPC Target Detection
    ↓
UPC / Presence Layer
    ↓
Connector
    ↓
Presence Service
```

## What TPC does

- Detects a running target and its state.
- Loads target-specific definitions from JSON.
- Runs presence providers/connectors.
- Supports reusable UPC templates with `{variable}` placeholders.
- Can serve a local RPC endpoint.
- Supports multiple presence instances with `--instant`.
- Provides a terminal UI for runtime settings.

## Quick start

```powershell
tpc --launch upc --app discord --target fl_studio.json
```

For a continuously running target, TPC can keep the detected state synchronized with the connector.

[Get started](docs/getting-started/) · [Architecture](docs/architecture/) · [CLI reference](docs/cli/)
