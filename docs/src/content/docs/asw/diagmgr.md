---
title: "Diagnostic Manager (DiagMgr)"
description: "Core Diagnostic Manager Functionality"
---


# Diagnostic Manager (`DiagMgr`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

Core Diagnostic Manager Functionality


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `DiagMgr/src/Ap_DiagMgr_Core.c` | Implementation |
| `DiagMgr/src/Ap_DiagMgr_DemIf.c` | Implementation |
| `DiagMgr/src/Ap_DiagMgr_FailAction.c` | Implementation |
| `DiagMgr/include/Ap_DiagMgr.h` | Public interface |
| `DiagMgr/include/Ap_DiagMgr_Types.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_DemIf_RestartDem`
- `Rte_Call_DemIf_SetOperationCycleState`
- `Rte_Call_DemIf_DemShutdown`
- `Rte_Call_DiagMgr_Per2`
- `Rte_Call_DemIf_SetEventStatus`
- `Rte_Call_DiagMgr_Per1`


## Dependencies (direct includes)

- `Std_Types.h`
- `Ap_DiagMgr.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `Os.h`
- `MemMap.h`
- `fixmath.h`
- `NvM.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Diagnostics Manager Core](./doc-diagnostics-manager-core-mdd/) `(Diagnostics_Manager_Core_MDD.docx)`
- [Diagnostics Manager DemIf](./doc-diagnostics-manager-demif-mdd/) `(Diagnostics_Manager_DemIf_MDD.docx)`
- [Diagnostics Manager FailAction](./doc-diagnostics-manager-failaction-mdd/) `(Diagnostics_Manager_FailAction_MDD.docx)`
- [Diagnostics Manager GeneratedCfg](./doc-diagnostics-manager-generatedcfg-mdd/) `(Diagnostics_Manager_GeneratedCfg_MDD.docx)`


## Other artefacts (not converted)

- `DiagMgr/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `DiagMgr/doc/DiagMgr Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `DiagMgr/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
