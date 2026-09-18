---
title: "Controller Temperature Monitoring (CtrlTemp)"
description: "Controller Temperature Monitoring (CtrlTemp) — AUTOSAR software component `Sa_CtrlTemp` for the Chrysler LWR EPS — design coverage: Controller Temperature."
---


# Controller Temperature Monitoring (`CtrlTemp`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Controller Temperature Monitoring* (`CtrlTemp`) — AUTOSAR software component `Sa_CtrlTemp` for the Chrysler LWR EPS — design coverage: Controller Temperature.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `CtrlTemp/src/Sa_CtrlTemp.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `CtrlTemp_Init1`
- `CtrlTemp_Per1`
- `CtrlTemp_Per2`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_CtrlTemp_Init1`
- `Rte_IWrite_CtrlTemp_Init1`
- `Rte_IWriteRef_CtrlTemp_Init1`
- `Rte_IRead_CtrlTemp_Per1`
- `Rte_IWrite_CtrlTemp_Per1`
- `Rte_IWriteRef_CtrlTemp_Per1`
- `Rte_Call_CtrlTemp_Per1`
- `Rte_IRead_CtrlTemp_Per2`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_CtrlTemp_Per2`


## Dependencies (direct includes)

- `Rte_Sa_CtrlTemp.h`
- `fixmath.h`
- `filters.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `Sa_CtrlTemp_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Controller Temperature](./doc-controller-temperature-mdd/) `(Controller_Temperature_MDD.docx)`
- [CtrlTemp Integration Manual](./doc-ctrltemp-integration-manual/) `(CtrlTemp_Integration_Manual.docx)`


## Other artefacts (not converted)

- `CtrlTemp/doc/CtrlTemp_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `CtrlTemp/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `CtrlTemp/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
