---
title: "Current Reasonableness Diagnostics (CurrReasDiag)"
description: "Current Reasonableness Diagnostics (CurrReasDiag) — AUTOSAR software component `Ap_CurrReasDiag` for the Chrysler LWR EPS system on the TMS570."
---


# Current Reasonableness Diagnostics (`CurrReasDiag`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Current Reasonableness Diagnostics* (`CurrReasDiag`) — AUTOSAR software component `Ap_CurrReasDiag` for the Chrysler LWR EPS system on the TMS570.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1 (Beta)`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `CurrReasDiag/src/Ap_CurrReasDiag.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `CurrReasDiag_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_CurrReasDiag_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`


## Dependencies (direct includes)

- `Rte_Ap_CurrReasDiag.h`
- `CalConstants.h`
- `fixmath.h`
- `interpolation.h`
- `filters.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Other artefacts (not converted)

- `CurrReasDiag/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `CurrReasDiag/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
