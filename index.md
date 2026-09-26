---
layout: home
title: Text Presence Core
nav_order: 1
description: Text Presence Core — a runtime/framework for application presence.
---

# Text Presence Core

**Presence that comes from the application.**

TPC is a **presence runtime/framework** for detecting application state, connecting it to a target definition, and exposing that state to presence clients.

<div class="code-example" markdown="1">

```text
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

</div>

## What TPC does

- Detects a running target and its state.
- Loads target-specific definitions from JSON.
- Runs presence providers and connectors.
- Supports reusable UPC templates with `{variable}` placeholders.
- Can serve a local RPC endpoint.
- Supports multiple presence instances with `--instant`.
- Provides a terminal UI for runtime settings.

## Quick start

```powershell
tpc --launch upc --app discord --target fl_studio.json
```

[Get started](docs/getting-started/) · [Architecture](docs/architecture/) · [CLI reference](docs/cli/)

{: .note }
TPC is designed as a runtime/framework first — not just a Discord RPC CLI.
