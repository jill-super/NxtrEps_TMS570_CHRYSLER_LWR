---
title: "Motor Temperature Estimation (MtrTempEst)"
description: "AUTOSAR software component `Ap_MtrTempEst` for the Chrysler LWR EPS — design coverage: Motor Temperature Estimation."
---


# Motor Temperature Estimation (`MtrTempEst`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

AUTOSAR software component `Ap_MtrTempEst` for the Chrysler LWR EPS — design coverage: Motor Temperature Estimation.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `MtrTempEst/src/Ap_MtrTempEst.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `MtrTempEst_Init1`
- `MtrTempEst_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_MtrTempEst_Init1`
- `Rte_IWrite_MtrTempEst_Init1`
- `Rte_IWriteRef_MtrTempEst_Init1`
- `Rte_IRead_MtrTempEst_Per1`
- `Rte_IWrite_MtrTempEst_Per1`
- `Rte_IWriteRef_MtrTempEst_Per1`
- `Rte_Call_MtrTempEst_Per1`


## Dependencies (direct includes)

- `Rte_Ap_MtrTempEst.h`
- `Ap_MtrTempEst_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `filters.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Motor Temperature Estimation Integration Manual](./doc-motor-temperature-estimation-integration-manual/) `(Motor_Temperature_Estimation_Integration_Manual.docx)`
- [Motor Temperature Estimation](./doc-motor-temperature-estimation-mdd/) `(Motor_Temperature_Estimation_MDD.docx)`


## Other artefacts (not converted)

- `MtrTempEst/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrTempEst/doc/MtrTempEst_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrTempEst/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
