---
title: "Power Limit Function – Current Mode (PwrLmtFuncCr)"
description: "Power Limit Function – Current Mode (PwrLmtFuncCr) — AUTOSAR software component `Ap_PwrLmtFuncCr` for the Chrysler LWR EPS — design coverage: Power Limit Function CM."
---


# Power Limit Function – Current Mode (`PwrLmtFuncCr`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Power Limit Function – Current Mode* (`PwrLmtFuncCr`) — AUTOSAR software component `Ap_PwrLmtFuncCr` for the Chrysler LWR EPS — design coverage: Power Limit Function CM.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `PwrLmtFuncCr/src/Ap_PwrLmtFuncCr.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `PwrLmtFuncCr_Init1`
- `PwrLmtFuncCr_Per1`
- `PwrLmtFuncCr_Per2`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_IRead_PwrLmtFuncCr_Per1`
- `Rte_IWrite_PwrLmtFuncCr_Per1`
- `Rte_IWriteRef_PwrLmtFuncCr_Per1`
- `Rte_Call_PwrLmtFuncCr_Per1`
- `Rte_IRead_PwrLmtFuncCr_Per2`
- `Rte_IWrite_PwrLmtFuncCr_Per2`
- `Rte_IWriteRef_PwrLmtFuncCr_Per2`
- `Rte_Call_NxtrDiagMgr_GetNTCStatus`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_PwrLmtFuncCr_Per2`


## Dependencies (direct includes)

- `Rte_Ap_PwrLmtFuncCr.h`
- `Ap_PwrLmtFuncCr_Cfg.h`
- `CalConstants.h`
- `fixmath.h`
- `filters.h`
- `interpolation.h`
- `GlobalMacro.h`
- `float.h`
- `Ap_DiagMgr.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Power Limit Function CM Integration Manual](./doc-power-limit-function-cm-integration-manual/) `(Power_Limit_Function_CM_Integration_Manual.docx)`
- [Power Limit Function CM](./doc-power-limit-function-cm-mdd/) `(Power_Limit_Function_CM_MDD.docx)`


## Other artefacts (not converted)

- `PwrLmtFuncCr/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `PwrLmtFuncCr/doc/Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `PwrLmtFuncCr/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
