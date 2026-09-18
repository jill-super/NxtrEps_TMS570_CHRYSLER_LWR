---
title: "Wheel Imbalance Rejection (WhlImbRej)"
description: "AUTOSAR software component `Ap_WhlImbRej` for the Chrysler LWR EPS — design coverage: Wheel Imbalance Rejection."
---


# Wheel Imbalance Rejection (`WhlImbRej`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

AUTOSAR software component `Ap_WhlImbRej` for the Chrysler LWR EPS — design coverage: Wheel Imbalance Rejection.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `WhlImbRej/src/Ap_WhlImbRej.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `WhlImbRej_Init1`
- `WhlImbRej_Per1`
- `WhlImbRej_Per2`
- `WhlImbRej_Per3`
- `WhlImbRej_SCom_GetWIRInfo`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_WhlImbRej_Per1`
- `Rte_IWrite_WhlImbRej_Per1`
- `Rte_IWriteRef_WhlImbRej_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_WhlImbRej_Per1`
- `Rte_Call_WhlImbRej_Per2`
- `Rte_IWrite_WhlImbRej_Per3`
- `Rte_IWriteRef_WhlImbRej_Per3`
- `Rte_Call_WhlImbRej_Per3`


## Dependencies (direct includes)

- `Rte_Ap_WhlImbRej.h`
- `GlobalMacro.h`
- `fixmath.h`
- `CalConstants.h`
- `filters.h`
- `interpolation.h`
- `Filter_Types.h`
- `Ap_WhlImbRej_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Wheel Imbalance Rejection](./doc-wheel-imbalance-rejection-mdd/) `(Wheel_Imbalance_Rejection_MDD.docx)`


## Other artefacts (not converted)

- `WhlImbRej/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `WhlImbRej/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
