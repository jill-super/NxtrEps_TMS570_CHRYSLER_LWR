---
title: "Average Friction Learning (AvgFricLrn)"
description: "AUTOSAR software component `Ap_AvgFricLrn` for the Chrysler LWR EPS — design coverage: Average Friction Learning."
---


# Average Friction Learning (`AvgFricLrn`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

AUTOSAR software component `Ap_AvgFricLrn` for the Chrysler LWR EPS — design coverage: Average Friction Learning.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1 (Beta)`.


Copyright headers found in sources reference: Vector Informatik, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `AvgFricLrn/src/Ap_AvgFricLrn.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `AvgFricLrn_Init1`
- `AvgFricLrn_Per1`
- `AvgFricLrn_SCom_GetEOLFric`
- `AvgFricLrn_SCom_GetOffsetOutputDefeat`
- `AvgFricLrn_SCom_GetSelect`
- `AvgFricLrn_SCom_InitLearnedTables`
- `AvgFricLrn_SCom_ResetToZero`
- `AvgFricLrn_SCom_SetEOLFric`
- `AvgFricLrn_SCom_SetOffsetOutputDefeat`
- `AvgFricLrn_SCom_SetSelect`
- `AvgFricLrn_Trns1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IWrite_AvgFricLrn_Init1`
- `Rte_IWriteRef_AvgFricLrn_Init1`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_IRead_AvgFricLrn_Per1`
- `Rte_IWrite_AvgFricLrn_Per1`
- `Rte_IWriteRef_AvgFricLrn_Per1`
- `Rte_Call_FltInjection_SCom`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_AvgFricLrnData_WriteBlock`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_AvgFricLrn_Per1`


## Dependencies (direct includes)

- `Rte_Ap_AvgFricLrn.h`
- `CalConstants.h`
- `fixmath.h`
- `GlobalMacro.h`
- `filters.h`
- `interpolation.h`
- `Ap_AvgFricLrn_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Average Friction Learning](./doc-average-friction-learning-mdd/) `(Average_Friction_Learning_MDD.docx)`


## Other artefacts (not converted)

- `AvgFricLrn/doc/AvgFricLrn Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `AvgFricLrn/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `AvgFricLrn/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
