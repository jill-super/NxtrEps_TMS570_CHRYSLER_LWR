---
title: "System State and Mode Management (StaMd)"
description: "System State and Mode Management (StaMd) — Core States and Modes Module"
---


# System State and Mode Management (`StaMd`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*System State and Mode Management* (`StaMd`) — Core States and Modes Module


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `StaMd/src/Ap_StaMd.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_StaMd_Per1`
- `Rte_Call_DiagMgr_StaCtrl`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_CloseCheckData_WriteBlock`
- `Rte_Call_StaMd_Per1`
- `Rte_Call_TOD_OP`
- `Rte_Call_CloseCheckData_GetErrorStatus`
- `Rte_Call_TypeHData_WriteBlock`


## Dependencies (direct includes)

- `Rte_Ap_StaMd.h`
- `Std_Types.h`
- `Ap_StaMd_Cfg.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `Os.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [States And Modes GeneratedConfiguration](./doc-states-and-modes-generatedconfiguration-mdd/) `(States_And_Modes_GeneratedConfiguration_MDD.docx)`
- [States And Modes](./doc-states-and-modes-mdd/) `(States_And_Modes_MDD.docx)`


## Other artefacts (not converted)

- `StaMd/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `StaMd/doc/Data Dictionary_GeneratedCFG_.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `StaMd/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
