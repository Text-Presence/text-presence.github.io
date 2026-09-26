---
title: Architecture
nav_order: 3
parent: Documentation
---

# Architecture

TPC separates **detection**, **runtime state**, **presence composition**, and **delivery**.

## Runtime flow

```
┌─────────────────┐
│   Application   │
└────────┬────────┘
         │ process / window / target state
         ▼
┌─────────────────┐
│ Target Detection│
└────────┬────────┘
         │ normalized runtime data
         ▼
┌─────────────────┐
│       TPC       │
│ Presence Runtime│
└────────┬────────┘
         │ variables / events
         ▼
┌─────────────────┐
│       UPC       │
│ Template / UI   │
└────────┬────────┘
         │ rendered presence
         ▼
┌─────────────────┐
│    Connector    │
└────────┬────────┘
         ▼
┌─────────────────┐
│ Presence Service│
└─────────────────┘
```

## TPC

**Text Presence Core** is the runtime/framework.

Its job is to coordinate:

- target detection
- target configuration
- runtime state
- launch modes
- connectors
- local serving
- settings and inspection

TPC should not need to know how every final presence sentence is written.

## UPC

**Unchanted Presence Client** is the presence/template layer.

UPC takes runtime variables and turns them into a user-defined representation.

For example:

```text
You're using {application}
{project} · {bpm} BPM
{genre} · {mood}
```

A target can provide values such as:

```text
application = FL Studio
project     = Farland
bpm         = 120
genre       = Breakcore
mood        = Breakcore
```

## Connectors

Connectors deliver the resulting presence to an external service.

The connector is selected independently from target detection:

```text
--app discord
```

This keeps Discord-specific behavior out of the core target model.

## Why the separation matters

A new application should primarily require a target definition/provider.

A new presence destination should primarily require a connector.

A new presentation format should primarily require a UPC/template definition.

That gives TPC a modular path as the project grows.
