---
title: CLI Reference
nav_order: 5
parent: Documentation
---

# CLI Reference

TPC is controlled through composable options.

## Launch

```powershell
tpc --launch upc
```

Current launch layers:

```text
upc
rpc
fpc
ppc
```

## Connector

```powershell
tpc --app discord
```

## Target

```powershell
tpc --target fl_studio.json
```

## Multiple instances

```powershell
tpc --instant
```

## Local RPC server

```powershell
tpc --serve
```

## Settings

```powershell
tpc --settings
```

## Help

```powershell
tpc --help
```

## Typical command

```powershell
tpc --launch upc --app discord --target fl_studio.json
```
