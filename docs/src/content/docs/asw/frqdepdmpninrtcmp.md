---
title: "Frequency-Dependent Damping and Inertia Compensation (FrqDepDmpnInrtCmp)"
description: "Frequency-Dependent Damping and Inertia Compensation (FrqDepDmpnInrtCmp) — AUTOSAR software component `Ap_FrqDepDmpnInrtCmp` for the Chrysler LWR EPS — design coverage: Frequency Dependant Damping And Inertia Compenstation."
---


# Frequency-Dependent Damping and Inertia Compensation (`FrqDepDmpnInrtCmp`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Frequency-Dependent Damping and Inertia Compensation* (`FrqDepDmpnInrtCmp`) — AUTOSAR software component `Ap_FrqDepDmpnInrtCmp` for the Chrysler LWR EPS — design coverage: Frequency Dependant Damping And Inertia Compenstation.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `FrqDepDmpnInrtCmp/src/Ap_FrqDepDmpnInrtCmp.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `FrqDepDmpnInrtCmp_Init`
- `FrqDepDmpnInrtCmp_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_FrqDepDmpnInrtCmp_Per1`
- `Rte_IWrite_FrqDepDmpnInrtCmp_Per1`
- `Rte_IWriteRef_FrqDepDmpnInrtCmp_Per1`
- `Rte_Call_FltInjection_SCom`
- `Rte_Call_FrqDepDmpnInrtCmp_Per1`


## Dependencies (direct includes)

- `Rte_Ap_FrqDepDmpnInrtCmp.h`
- `Ap_FrqDepDmpnInrtCmp_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `filters.h`
- `interpolation.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Frequency Dependant Damping And Inertia Compenstation](./doc-frequency-dependant-damping-and-inertia-compenstation-mdd/) `(Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD.docx)`


## Other artefacts (not converted)

- `FrqDepDmpnInrtCmp/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `FrqDepDmpnInrtCmp/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
