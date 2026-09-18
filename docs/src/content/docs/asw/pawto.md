---
title: "Park Assist Torque Overlay (PAwTO)"
description: "Park Assist Torque Overlay (PAwTO) — AUTOSAR software component `Ap_PAwTO` for the Chrysler LWR EPS — design coverage: PAwTO."
---


# Park Assist Torque Overlay (`PAwTO`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Park Assist Torque Overlay* (`PAwTO`) — AUTOSAR software component `Ap_PAwTO` for the Chrysler LWR EPS — design coverage: PAwTO.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `PAwTO/src/Ap_PAwTO.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `PAwTO_Init1`
- `PAwTO_Per1`
- `PAwTO_Per2`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_PAwTO_Init1`
- `Rte_Call_PrkAssistState_SCom`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_IRead_PAwTO_Per1`
- `Rte_IWrite_PAwTO_Per1`
- `Rte_IWriteRef_PAwTO_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCActive`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_PAwTO_Per1`
- `Rte_IRead_PAwTO_Per2`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_PAwTO_Per2`


## Dependencies (direct includes)

- `Rte_Ap_PAwTO.h`
- `Ap_PAwTO_Cfg.h`
- `GlobalMacro.h`
- `fixmath.h`
- `filters.h`
- `CalConstants.h`
- `float.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [PAwTO Integration Manual](./doc-pawto-integration-manual/) `(PAwTO_Integration_Manual.docx)`
- [PAwTO](./doc-pawto-mdd/) `(PAwTO_MDD.docx)`


## Other artefacts (not converted)

- `PAwTO/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `PAwTO/doc/Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `PAwTO/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
