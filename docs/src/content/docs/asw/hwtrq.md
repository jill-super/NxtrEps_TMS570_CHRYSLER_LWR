---
title: "Handwheel Torque Sensing (HwTrq)"
description: "Handwheel Torque Sensing (HwTrq) — AUTOSAR software component `Sa_HwTrq` for the Chrysler LWR EPS — design coverage: Handwheel Torque 2; Handwheel Torque."
---


# Handwheel Torque Sensing (`HwTrq`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Handwheel Torque Sensing* (`HwTrq`) — AUTOSAR software component `Sa_HwTrq` for the Chrysler LWR EPS — design coverage: Handwheel Torque 2; Handwheel Torque.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `HwTrq/src/Sa_HwTrq.c` | Implementation |
| `HwTrq/src/Sa_HwTrq2.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `HwTrq_Init`
- `HwTrq_Per1`
- `HwTrq_Per2`
- `HwTrq_Per3`
- `HwTrq_SCom_ClrHwTrqScale`
- `HwTrq_SCom_ClrHwTrqTrim`
- `HwTrq_SCom_ManualSetHwTrqTrim`
- `HwTrq_SCom_ReadEOLTrqStep`
- `HwTrq_SCom_ReadHwTrqScale`
- `HwTrq_SCom_ReadHwTrqTrim`
- `HwTrq_SCom_SetEOLTrqStep`
- `HwTrq_SCom_SetHwTrqScale`
- `HwTrq_SCom_SetHwTrqTrim`
- `HwTrq2_Init1`
- `HwTrq2_Per1`
- `HwTrq2_Per2`
- `HwTrq2_Per3`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_HwTrq_Init`
- `Rte_IWrite_HwTrq_Init`
- `Rte_IWriteRef_HwTrq_Init`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_HwTrqTrim_GetErrorStatus`
- `Rte_IRead_HwTrq_Per1`
- `Rte_IWrite_HwTrq_Per1`
- `Rte_IWriteRef_HwTrq_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCStatus`
- `Rte_Call_HwTrq_Per1`
- `Rte_IRead_HwTrq_Per2`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_HwTrq_Per2`
- `Rte_Call_HwTrq_Per3`
- `Rte_Call_HwTrqScale_WriteBlock`
- `Rte_Call_HwTrqTrim_WriteBlock`
- `Rte_Call_EOLTrqStep_WriteBlock`
- `Rte_IRead_HwTrq2_Per1`
- `Rte_IWrite_HwTrq2_Per1`
- `Rte_IWriteRef_HwTrq2_Per1`
- `Rte_Call_HwTrq2_Per1`
- `Rte_IRead_HwTrq2_Per2`
- `Rte_Call_HwTrq2_Per2`
- `Rte_IRead_HwTrq2_Per3`
- `Rte_Call_HwTrq2_Per3`


## Dependencies (direct includes)

- `Rte_Sa_HwTrq.h`
- `CalConstants.h`
- `fixmath.h`
- `GlobalMacro.h`
- `filters.h`
- `interpolation.h`
- `Sa_HwTrq_Cfg.h`
- `MemMap.h`
- `Rte_Sa_HwTrq2.h`
- `Sa_HwTrq2_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Handwheel Torque 2](./doc-handwheel-torque-2-mdd/) `(Handwheel_Torque_2_MDD.docx)`
- [Handwheel Torque](./doc-handwheel-torque-mdd/) `(Handwheel_Torque_MDD.doc)`


## Other artefacts (not converted)

- `HwTrq/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `HwTrq/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
