---
title: "Bulk Capacitor Pre-Charge (BkCpPc)"
description: "Bulk Capacitor Pre-Charge (BkCpPc) — AUTOSAR software component `Sa_BkCpPc` for the Chrysler LWR EPS — design coverage: Bulk Cap Precharge."
---


# Bulk Capacitor Pre-Charge (`BkCpPc`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Bulk Capacitor Pre-Charge* (`BkCpPc`) — AUTOSAR software component `Sa_BkCpPc` for the Chrysler LWR EPS — design coverage: Bulk Cap Precharge.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1 (Beta)`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `BkCpPc/src/Sa_BkCpPc.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `BkCpPc_Per1`
- `BkCpPc_Trns1`
- `BkCpPc_Trns2`
- `CapPcDcStub_OP_SET`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_BkCpPc_Per1`
- `Rte_IWrite_BkCpPc_Per1`
- `Rte_IWriteRef_BkCpPc_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_PhyCapDischarge_OP`
- `Rte_Call_PhyCapPrecharge_OP`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_BkCpPc_Per1`
- `Rte_IWrite_BkCpPc_Trns1`
- `Rte_IWriteRef_BkCpPc_Trns1`
- `Rte_IWrite_BkCpPc_Trns2`
- `Rte_IWriteRef_BkCpPc_Trns2`


## Dependencies (direct includes)

- `Rte_Sa_BkCpPc.h`
- `Sa_BkCpPc_Cfg.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Bulk Cap Precharge](./doc-bulk-cap-precharge-mdd/) `(Bulk_Cap_Precharge_MDD.docx)`


## Other artefacts (not converted)

- `BkCpPc/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `BkCpPc/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
