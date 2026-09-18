---
title: "Active Pull Compensation (ActivePull)"
description: "Active Pull Compensation (ActivePull) — AUTOSAR software component `Ap_ActivePull` for the Chrysler LWR EPS — design coverage: Active Pull Comp."
---


# Active Pull Compensation (`ActivePull`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Active Pull Compensation* (`ActivePull`) — AUTOSAR software component `Ap_ActivePull` for the Chrysler LWR EPS — design coverage: Active Pull Comp.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `ActivePull/src/Ap_ActivePull.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `ActivePull_Init1`
- `ActivePull_Per1`
- `ActivePull_Per2`
- `ActivePull_Per3`
- `ActivePull_SCom_ReadParam`
- `ActivePull_SCom_Reset`
- `ActivePull_SCom_SetLTComp`
- `ActivePull_SCom_SetSTComp`
- `ActivePull_Trns1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_ActivePull_Per1`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_ActivePull_Per1`
- `Rte_IRead_ActivePull_Per2`
- `Rte_IWrite_ActivePull_Per2`
- `Rte_IWriteRef_ActivePull_Per2`
- `Rte_Call_ActivePull_Per2`
- `Rte_IRead_ActivePull_Per3`
- `Rte_Call_ActivePull_Per3`


## Dependencies (direct includes)

- `Rte_Ap_ActivePull.h`
- `Ap_ActivePull_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `fixmath.h`
- `filters.h`
- `interpolation.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Active Pull Comp](./doc-active-pull-comp-mdd/) `(Active_Pull_Comp_MDD.docx)`


## Other artefacts (not converted)

- `ActivePull/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `ActivePull/doc/Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `ActivePull/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
