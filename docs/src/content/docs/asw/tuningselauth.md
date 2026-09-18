---
title: "Tuning Selection Authority (TuningSelAuth)"
description: "Tuning Selection Authority (TuningSelAuth) — AUTOSAR software component `Ap_TuningSelAuth` for the Chrysler LWR EPS — design coverage: Tuning Select Authority."
---


# Tuning Selection Authority (`TuningSelAuth`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Tuning Selection Authority* (`TuningSelAuth`) — AUTOSAR software component `Ap_TuningSelAuth` for the Chrysler LWR EPS — design coverage: Tuning Select Authority.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `TuningSelAuth/src/Ap_TuningSelAuth.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `TuningSelAuth_Init1`
- `TuningSelAuth_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_TuningSelAuth_Init1`
- `Rte_IWrite_TuningSelAuth_Init1`
- `Rte_IWriteRef_TuningSelAuth_Init1`
- `Rte_IRead_TuningSelAuth_Per1`
- `Rte_IWrite_TuningSelAuth_Per1`
- `Rte_IWriteRef_TuningSelAuth_Per1`
- `Rte_Call_TuningSelAuth_Per1`


## Dependencies (direct includes)

- `Rte_Ap_TuningSelAuth.h`
- `CalConstants.h`
- `filters.h`
- `GlobalMacro.h`
- `Ap_TuningSelAuth_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Tuning Select Authority](./doc-tuning-select-authority-mdd/) `(Tuning_Select_Authority_MDD.docx)`


## Other artefacts (not converted)

- `TuningSelAuth/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `TuningSelAuth/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
