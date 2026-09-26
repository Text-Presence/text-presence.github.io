---
title: UPC
nav_order: 4
parent: Documentation
---

# UPC

**Unchanted Presence Client** is TPC's template/presentation layer.

It is not just a Discord RPC configuration file. UPC composes runtime data into a presence representation.

## Variables

UPC uses `{variable}` placeholders:

```text
You're using {application}
{project} · {bpm} BPM
{genre} · {mood}
```

TPC supplies those values at runtime.

## Custom variables

Projects can define additional variables through a root custom-variable file such as:

```text
.valve.json
```

This keeps presentation customization separate from application detection.

{: .important }
Target data answers **“what is happening?”**. UPC answers **“how should it be represented?”**
