---
title: Development
nav_order: 6
parent: Documentation
---

# Development

TPC is developed as a native C++/CMake project.

## Build

```powershell
cmake -S . -B build
cmake --build build --config Release
```

## Test

TPC uses CTest:

```powershell
ctest --test-dir build -C Release --output-on-failure
```

## Development model

Keep the boundaries clear:

```text
target detection
       ↓
runtime
       ↓
presence layer
       ↓
connector
```

When adding application support, prefer extending the target/provider layer rather than putting application-specific detection into UPC or a connector.
