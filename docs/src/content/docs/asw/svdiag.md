---
title: "Supply Voltage and Motor Driver Diagnostics (SVDiag)"
description: "Supply Voltage and Motor Driver Diagnostics (SVDiag) — AUTOSAR software component `Ap_DigPhsReasDiag` for the Chrysler LWR EPS — design coverage: DigPhsReasDiag; Motor Driver Diagnostics."
---


# Supply Voltage and Motor Driver Diagnostics (`SVDiag`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Supply Voltage and Motor Driver Diagnostics* (`SVDiag`) — AUTOSAR software component `Ap_DigPhsReasDiag` for the Chrysler LWR EPS — design coverage: DigPhsReasDiag; Motor Driver Diagnostics.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `SVDiag/src/Ap_DigPhsReasDiag.c` | Implementation |
| `SVDiag/src/Sa_MtrDrvDiag.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `DigPhsReasDiag_Init`
- `DigPhsReasDiag_Per1`
- `DigPhsReasDiag_Trans1`
- `MtrDrvDiag_Per1`
- `MtrDrvDiag_Per2`
- `MtrDrvDiag_Trns1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_DigPhsReasDiag_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_DigPhsReasDiag_Per1`
- `Rte_Call_NxtrDiagMgr_GetEventFailed`
- `Rte_IRead_MtrDrvDiag_Per1`
- `Rte_IWrite_MtrDrvDiag_Per1`
- `Rte_IWriteRef_MtrDrvDiag_Per1`
- `Rte_Call_FetDrvReset_OP`
- `Rte_Call_FetFlt1Data_OP`
- `Rte_Call_FetFlt2Clk_OP`
- `Rte_Call_IoHwAbPortConfig_SetFetFlt2ToOutput`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_MtrDrvDiag_Per1`
- `Rte_IWrite_MtrDrvDiag_Trns1`
- `Rte_IWriteRef_MtrDrvDiag_Trns1`


## Dependencies (direct includes)

- `Rte_Ap_DigPhsReasDiag.h`
- `CalConstants.h`
- `fixmath.h`
- `GlobalMacro.h`
- `filters.h`
- `Ap_DigPhsReasDiag_Cfg.h`
- `MemMap.h`
- `Rte_Sa_MtrDrvDiag.h`
- `Os.h`
- `Sa_MtrDrvDiag_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [DigPhsReasDiag](./doc-digphsreasdiag-mdd/) `(DigPhsReasDiag_MDD.docx)`
- [Motor Driver Diagnostics](./doc-motor-driver-diagnostics-mdd/) `(Motor_Driver_Diagnostics_MDD.docx)`
- [SVDiag Integration Manual](./doc-svdiag-integration-manual/) `(SVDiag_Integration_Manual.docx)`


## Other artefacts (not converted)

- `SVDiag/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `SVDiag/doc/SVDiag_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `SVDiag/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
