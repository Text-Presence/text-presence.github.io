---
title: Getting Started
nav_order: 1
parent: Documentation
---

# Getting Started

TPC is built around a simple idea: **the application owns the state; TPC turns that state into presence.**

## Build

```powershell
cmake -S . -B build
cmake --build build --config Release
```

The runtime is produced as:

```text
build\Release\tpc.exe
```

## Define a target

A target describes how TPC identifies an application and what runtime information it can provide.

```json
{
  "application": "fl_studio",
  "title": "FL Studio",
  "provider": "fl_studio",
  "process": "FL64.exe"
}
```

## Run TPC

```powershell
tpc --launch upc --app discord --target fl_studio.json
```

A runtime session can report the detected target, provider, process, PID, and window.

```text
+----------------------------------------+
| running Text Presence.                 |
|----------------------------------------|
| FL Studio                              |
|                                        |
| fl_studio                              |
| Provider: fl_studio                    |
| Process: FL64.exe                      |
| PID: 20640                             |
| Window: FL Studio 2026                 |
|                                        |
+----------------------------------------+
 Target: fl_studio  |  Ctrl+C to exit
```
