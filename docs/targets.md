---
title: Targets
nav_order: 3
parent: Documentation
---

# Targets

A **target** describes an application that TPC can detect.

Target definitions are data-driven JSON files.

| Field | Purpose |
|---|---|
| `application` | Stable target identifier |
| `title` | Human-readable application name |
| `provider` | Detection/provider implementation |
| `process` | Process used to identify the application |

## Example

```json
{
  "application": "fl_studio",
  "title": "FL Studio",
  "provider": "fl_studio",
  "process": "FL64.exe"
}
```

## Runtime data

A provider can expose application-specific state:

```text
project
bpm
progress
elapsed
mood
genre
```

TPC normalizes that information so the presence layer can consume it.
