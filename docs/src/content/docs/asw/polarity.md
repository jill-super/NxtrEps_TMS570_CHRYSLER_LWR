---
title: "Signal Polarity Management (Polarity)"
description: "Signal Polarity Management (Polarity) — AUTOSAR software component `Ap_Polarity` for the Chrysler LWR EPS — design coverage: Polarity."
---


# Signal Polarity Management (`Polarity`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Signal Polarity Management* (`Polarity`) — AUTOSAR software component `Ap_Polarity` for the Chrysler LWR EPS — design coverage: Polarity.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `Polarity/src/Ap_Polarity.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `Polarity_Init1`
- `Polarity_Per1`
- `Polarity_SCom_ReadPolarity`
- `Polarity_SCom_SetPolarity`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IWrite_Polarity_Init1`
- `Rte_IWriteRef_Polarity_Init1`
- `Rte_IRead_Polarity_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_Polarity_Per1`
- `Rte_Call_Polarity_WriteBlock`


## Dependencies (direct includes)

- `Rte_Ap_Polarity.h`
- `Ap_Polarity_Cfg.h`
- `Os.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Polarity](./doc-polarity-mdd/) `(Polarity_MDD.docx)`


## Other artefacts (not converted)

- `Polarity/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `Polarity/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
