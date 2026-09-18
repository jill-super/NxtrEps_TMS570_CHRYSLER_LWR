---
title: "Steering Return Control (Return)"
description: "Steering Return Control (Return) — AUTOSAR software component `Ap_Return` for the Chrysler LWR EPS — design coverage: Return."
---


# Steering Return Control (`Return`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Steering Return Control* (`Return`) — AUTOSAR software component `Ap_Return` for the Chrysler LWR EPS — design coverage: Return.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `Return/src/Ap_Return.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `Return_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_Return_Per1`
- `Rte_IWrite_Return_Per1`
- `Rte_IWriteRef_Return_Per1`
- `Rte_Call_FltInjection_SCom`
- `Rte_Call_Return_Per1`


## Dependencies (direct includes)

- `Rte_Ap_Return.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `interpolation.h`
- `Ap_Return_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Return](./doc-return-mdd/) `(Return_MDD.docx)`


## Other artefacts (not converted)

- `Return/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `Return/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
