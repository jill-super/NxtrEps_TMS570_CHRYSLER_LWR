---
title: "Temporal Monitoring (TmprlMon)"
description: "Temporal Monitoring (TmprlMon) — AUTOSAR software component `Sa_TmprlMon` for the Chrysler LWR EPS — design coverage: Temporal Monitor 2; Temporal Monitor."
---


# Temporal Monitoring (`TmprlMon`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Temporal Monitoring* (`TmprlMon`) — AUTOSAR software component `Sa_TmprlMon` for the Chrysler LWR EPS — design coverage: Temporal Monitor 2; Temporal Monitor.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `TmprlMon/src/Sa_TmprlMon.c` | Implementation |
| `TmprlMon/src/Sa_TmprlMon2.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `TmprlMon_Per1`
- `TmprlMon_Per2`
- `TmprlMon_Per3`
- `TmprlMon_Trns1`
- `TmprlMon_Trns2`
- `TmprlMon2_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_WdMonitor_OP`
- `Rte_Call_TmprlMon_Per1`
- `Rte_IRead_TmprlMon_Per2`
- `Rte_IWrite_TmprlMon_Per2`
- `Rte_IWriteRef_TmprlMon_Per2`
- `Rte_Call_FetDrvCntl_OP`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_PwrSwitchEn_OP`
- `Rte_Call_SysFault2_OP`
- `Rte_Call_SysFault3_OP`
- `Rte_Call_WdReset_OP`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_TmprlMon_Per2`
- `Rte_Call_TmprlMon_Per3`
- `Rte_IWrite_TmprlMon_Trns1`
- `Rte_IWriteRef_TmprlMon_Trns1`
- `Rte_Call_TmprlMon2_Per1`


## Dependencies (direct includes)

- `Rte_Sa_TmprlMon.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `Sa_TmprlMon_Cfg.h`
- `MemMap.h`
- `Rte_Sa_TmprlMon2.h`
- `Sa_TmprlMon2_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Temporal Monitor Integration Manual](./doc-temporal-monitor-integration-manual/) `(Temporal Monitor_Integration_Manual.docx)`
- [Temporal Monitor 2](./doc-temporal-monitor-2-mdd/) `(Temporal_Monitor_2_MDD.docx)`
- [Temporal Monitor](./doc-temporal-monitor-mdd/) `(Temporal_Monitor_MDD.docx)`


## Other artefacts (not converted)

- `TmprlMon/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `TmprlMon/doc/TmplMon Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `TmprlMon/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
