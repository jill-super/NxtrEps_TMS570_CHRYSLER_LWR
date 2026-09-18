---
title: "State Output Control (StOpCtrl)"
description: "AUTOSAR software component `Ap_StOpCtrl` for the Chrysler LWR EPS — design coverage: State Output Control."
---


# State Output Control (`StOpCtrl`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

AUTOSAR software component `Ap_StOpCtrl` for the Chrysler LWR EPS — design coverage: State Output Control.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR, DaVinci.


## Key files


| File | Role |
| --- | --- |
| `StOpCtrl/src/Ap_StOpCtrl.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `StOpCtrl_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_StOpCtrl_Per1`
- `Rte_IWrite_StOpCtrl_Per1`
- `Rte_IWriteRef_StOpCtrl_Per1`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_StOpCtrl_Per1`


## Dependencies (direct includes)

- `Rte_Ap_StOpCtrl.h`
- `GlobalMacro.h`
- `Ap_StOpCtrl_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [State Output Control](./doc-state-output-control-mdd/) `(State_Output_Control_MDD.docx)`


## Other artefacts (not converted)

- `StOpCtrl/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `StOpCtrl/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
