---
title: "Stability Compensation (StabilityComp)"
description: "Stability Compensation (StabilityComp) — AUTOSAR software component `Ap_StabilityComp` for the Chrysler LWR EPS — design coverage: StabilityCompensation2; StabilityCompensation."
---


# Stability Compensation (`StabilityComp`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Stability Compensation* (`StabilityComp`) — AUTOSAR software component `Ap_StabilityComp` for the Chrysler LWR EPS — design coverage: StabilityCompensation2; StabilityCompensation.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `StabilityComp/src/Ap_StabilityComp.c` | Implementation |
| `StabilityComp/src/Ap_StabilityComp2.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `StabilityComp_Init1`
- `StabilityComp_Per1`
- `StabilityComp2_Init1`
- `StabilityComp2_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_StabilityComp_Per1`
- `Rte_IWrite_StabilityComp_Per1`
- `Rte_IWriteRef_StabilityComp_Per1`
- `Rte_Call_FaultInjection_SCom`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_StabilityComp_Per1`
- `Rte_IRead_StabilityComp2_Per1`
- `Rte_IWrite_StabilityComp2_Per1`
- `Rte_IWriteRef_StabilityComp2_Per1`
- `Rte_Call_StabilityComp2_Per1`


## Dependencies (direct includes)

- `Rte_Ap_StabilityComp.h`
- `filters.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `interpolation.h`
- `Ap_StabilityComp_Cfg.h`
- `fixmath.h`
- `MemMap.h`
- `Rte_Ap_StabilityComp2.h`
- `Ap_StabilityComp2_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [StabilityCompensation2](./doc-stabilitycompensation2-mdd/) `(StabilityCompensation2_MDD.docx)`
- [StabilityCompensation](./doc-stabilitycompensation-mdd/) `(StabilityCompensation_MDD.docx)`


## Other artefacts (not converted)

- `StabilityComp/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `StabilityComp/doc/StabilityComp_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `StabilityComp/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
