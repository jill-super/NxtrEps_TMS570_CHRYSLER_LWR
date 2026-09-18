---
title: "Motor Velocity Sensing (MtrVel)"
description: "Motor Velocity Sensing (MtrVel) — AUTOSAR software component `Sa_MtrVel` for the Chrysler LWR EPS — design coverage: MotorVelocity2; MotorVelocity3."
---


# Motor Velocity Sensing (`MtrVel`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Motor Velocity Sensing* (`MtrVel`) — AUTOSAR software component `Sa_MtrVel` for the Chrysler LWR EPS — design coverage: MotorVelocity2; MotorVelocity3.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `MtrVel/src/Sa_MtrVel.c` | Implementation |
| `MtrVel/src/Sa_MtrVel2.c` | Implementation |
| `MtrVel/src/Sa_MtrVel3.c` | Implementation |
| `MtrVel/include/Sa_MtrVel.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `MtrVel_Init1`
- `MtrVel_Per1`
- `MtrVel_Per2`
- `MtrVel2_Init`
- `MtrVel2_Per1`
- `MtrVel2_Per2`
- `MtrVel3_Init`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_MtrVel_Per1`
- `Rte_IWrite_MtrVel_Per1`
- `Rte_IWriteRef_MtrVel_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_MtrVel_Per1`
- `Rte_IRead_MtrVel_Per2`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_MtrVel_Per2`
- `Rte_IRead_MtrVel2_Init`
- `Rte_IRead_MtrVel2_Per1`
- `Rte_IWrite_MtrVel2_Per1`
- `Rte_IWriteRef_MtrVel2_Per1`
- `Rte_Call_MtrVel2_Per1`
- `Rte_IRead_MtrVel2_Per2`
- `Rte_Call_MtrVel2_Per2`


## Dependencies (direct includes)

- `Rte_Sa_MtrVel.h`
- `Sa_MtrVel.h`
- `Sa_MtrVel_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `filters.h`
- `interpolation.h`
- `MemMap.h`
- `Rte_Sa_MtrVel2.h`
- `Sa_MtrVel2_Cfg.h`
- `Rte_Sa_MtrVel3.h`
- `Sa_MtrPos.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [MotorVelocity2](./doc-motorvelocity2-mdd/) `(MotorVelocity2_MDD.doc)`
- [MotorVelocity3](./doc-motorvelocity3-mdd/) `(MotorVelocity3_MDD.doc)`
- [MotorVelocity](./doc-motorvelocity-mdd/) `(MotorVelocity_MDD.doc)`


## Other artefacts (not converted)

- `MtrVel/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrVel/doc/MtrVel_SwAlgorithm_Analysis.xlsx` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrVel/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
