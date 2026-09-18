---
title: "Haptic Lane Feedback Torque Overlay (HaLFTO)"
description: "Haptic Lane Feedback Torque Overlay (HaLFTO) — AUTOSAR software component `Ap_HaLFTO` for the Chrysler LWR EPS — design coverage: HaLFTO."
---


# Haptic Lane Feedback Torque Overlay (`HaLFTO`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Haptic Lane Feedback Torque Overlay* (`HaLFTO`) — AUTOSAR software component `Ap_HaLFTO` for the Chrysler LWR EPS — design coverage: HaLFTO.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `HaLFTO/src/Ap_HaLFTO.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `HaLFTO_Init1`
- `HaLFTO_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_HaLFState_SCom`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_IRead_HaLFTO_Per1`
- `Rte_IWrite_HaLFTO_Per1`
- `Rte_IWriteRef_HaLFTO_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_HaLFTO_Per1`


## Dependencies (direct includes)

- `Rte_Ap_HaLFTO.h`
- `Ap_HaLFTO_Cfg.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `float.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [HaLFTO Integration Manual](./doc-halfto-integration-manual/) `(HaLFTO_Integration_Manual.docx)`
- [HaLFTO](./doc-halfto-mdd/) `(HaLFTO_MDD.docx)`


## Other artefacts (not converted)

- `HaLFTO/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `HaLFTO/doc/Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `HaLFTO/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
