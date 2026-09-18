---
title: "Absolute Hardware Position Serial Communication (AbsHwPosScom)"
description: "Absolute Hardware Position Serial Communication (AbsHwPosScom) — AUTOSAR software component `Ap_AbsHwPosScom` for the Chrysler LWR EPS — design coverage: AbsHwPosSCom."
---


# Absolute Hardware Position Serial Communication (`AbsHwPosScom`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Absolute Hardware Position Serial Communication* (`AbsHwPosScom`) — AUTOSAR software component `Ap_AbsHwPosScom` for the Chrysler LWR EPS — design coverage: AbsHwPosSCom.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `AbsHwPosScom/src/Ap_AbsHwPosScom.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `AbsHwPosScom_Init1`
- `AbsHwPosScom_Per1`
- `AbsHwPosScom_Per2`
- `AbsHwPosScom_Per3`
- `AbsHwPosScom_Scom_HwPosSrvRead`
- `AbsHwPosScom_Scom_HwPosSrvSetToZero`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_IRead_AbsHwPosScom_Per1`
- `Rte_IWrite_AbsHwPosScom_Per1`
- `Rte_IWriteRef_AbsHwPosScom_Per1`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_AbsHwPosScom_Per1`
- `Rte_IRead_AbsHwPosScom_Per2`
- `Rte_Call_AbsHwPosScom_Per2`
- `Rte_IRead_AbsHwPosScom_Per3`
- `Rte_Call_AbsHwPosScom_Per3`


## Dependencies (direct includes)

- `Rte_Ap_AbsHwPosScom.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `filters.h`
- `Interpolation.h`
- `fixmath.h`
- `Ap_AbsHwPosScom_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [AbsHwPosSCom](./doc-abshwposscom-mdd/) `(AbsHwPosSCom_MDD.docx)`


## Other artefacts (not converted)

- `AbsHwPosScom/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `AbsHwPosScom/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
