---
title: "Diagnostic Metrics Library (Metrics)"
description: "Diagnostic Metrics Library (Metrics) — Data for Metrics"
---


# Diagnostic Metrics Library (`Metrics`)

<span class="origin-badge origin-thirdparty">Third-party · customised</span>

> **Origin:** Originally Delphi Technologies instrumentation code, maintained/customised in this project for EPS metrics collection.

## Purpose

*Diagnostic Metrics Library* (`Metrics`) — Data for Metrics


Copyright headers found in sources reference: Delphi Technologies, ETAS.


## Key files


| File | Role |
| --- | --- |
| `Metrics/src/Metrics.c` | Implementation |
| `Metrics/src/sys_pmu.asm` | Assembly |
| `Metrics/include/Metrics.h` | Public interface |
| `Metrics/include/Metrics_Enable.h` | Public interface |
| `Metrics/include/sys_pmu.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Metrics.h`
- `Det.h`
- `GlobalMacro.h`
- `SystemTime.h`
- `sys_pmu.h`
- `string.h`
- `Rte_Type.h`
- `Metrics_Enable.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Metrics Integration Manual](./doc-metrics-integration-manual/) `(Metrics_Integration_Manual.docx)`
- [Metrics](./doc-metrics-mdd/) `(Metrics_MDD.docx)`


## Other artefacts (not converted)

- `Metrics/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
