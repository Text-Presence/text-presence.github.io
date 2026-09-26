---
title: Architecture
nav_order: 2
parent: Documentation
---

# Architecture

TPC separates **detection**, **runtime state**, **presence composition**, and **delivery**.

```text
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

It coordinates target detection, target configuration, runtime state, launch modes, connectors, local serving, and settings.

## UPC

**Unchanted Presence Client** is the presence/template layer.

UPC turns runtime variables into a user-defined presence representation.

## Connectors

Connectors deliver the resulting presence to an external service.

```text
--app discord
```

keeps Discord-specific delivery separate from target detection.

## The boundary

A new application should primarily require a target definition/provider.

A new presence destination should primarily require a connector.

A new presentation format should primarily require a UPC/template definition.
