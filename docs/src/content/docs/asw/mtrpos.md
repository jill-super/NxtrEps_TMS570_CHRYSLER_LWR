---
title: "Motor Position Sensing (MtrPos)"
description: "Motor Position Sensing (MtrPos) — AUTOSAR software component `Sa_MtrPos` for the Chrysler LWR EPS — design coverage: Motor Position 2; Motor Position 3."
---


# Motor Position Sensing (`MtrPos`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Motor Position Sensing* (`MtrPos`) — AUTOSAR software component `Sa_MtrPos` for the Chrysler LWR EPS — design coverage: Motor Position 2; Motor Position 3.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `MtrPos/src/Sa_MtrPos.c` | Implementation |
| `MtrPos/src/Sa_MtrPos2.c` | Implementation |
| `MtrPos/src/Sa_MtrPos3.c` | Implementation |
| `MtrPos/include/Sa_MtrPos.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `MtrPos_Init1`
- `MtrPos_Per2`
- `MtrPos_SCom_ReadEOLMtrCals`
- `MtrPos_SCom_SetEOLMtrCals`
- `MtrPos2_Init1`
- `MtrPos2_Per1`
- `MtrPos3_Per1`
- `MtrPos3_Per2`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_MtrPos_Per2`
- `Rte_IWrite_MtrPos_Per2`
- `Rte_IWriteRef_MtrPos_Per2`
- `Rte_Call_EOLMtrCals_WriteBlock`
- `Rte_IRead_MtrPos2_Per1`
- `Rte_IWrite_MtrPos2_Per1`
- `Rte_IWriteRef_MtrPos2_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_MtrPos2_Per1`
- `Rte_IRead_MtrPos3_Per1`
- `Rte_Call_MtrPos3_Per1`
- `Rte_IRead_MtrPos3_Per2`
- `Rte_Call_MtrPos3_Per2`


## Dependencies (direct includes)

- `Rte_Sa_MtrPos.h`
- `Sa_MtrPos.h`
- `GlobalMacro.h`
- `fixmath.h`
- `Adc2.h`
- `SystemTime.h`
- `atan2.h`
- `Os.h`
- `MemMap.h`
- `Rte_Sa_MtrPos2.h`
- `Sa_MtrPos2_Cfg.h`
- `interpolation.h`
- `filters.h`
- `CalConstants.h`
- `Rte_Sa_MtrPos3.h`
- `Sa_MtrPos3_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Motor Position 2](./doc-motor-position-2-mdd/) `(Motor_Position_2_MDD.docx)`
- [Motor Position 3](./doc-motor-position-3-mdd/) `(Motor_Position_3_MDD.docx)`
- [Motor Position](./doc-motor-position-mdd/) `(Motor_Position_MDD.docx)`


## Other artefacts (not converted)

- `MtrPos/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrPos/doc/MtrPos Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrPos/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
