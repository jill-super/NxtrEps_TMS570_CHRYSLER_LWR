---
title: "Thermal Duty Cycle Management (ThrmDutyCycle)"
description: "Thermal Duty Cycle Management (ThrmDutyCycle) — AUTOSAR software component `Ap_ThrmlDutyCycle` for the Chrysler LWR EPS — design coverage: Thermal Duty Cycle."
---


# Thermal Duty Cycle Management (`ThrmDutyCycle`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Thermal Duty Cycle Management* (`ThrmDutyCycle`) — AUTOSAR software component `Ap_ThrmlDutyCycle` for the Chrysler LWR EPS — design coverage: Thermal Duty Cycle.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `ThrmDutyCycle/src/Ap_ThrmlDutyCycle.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `ThrmlDutyCycle_Init1`
- `ThrmlDutyCycle_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_ThrmlDutyCycle_Init1`
- `Rte_IRead_ThrmlDutyCycle_Per1`
- `Rte_IWrite_ThrmlDutyCycle_Per1`
- `Rte_IWriteRef_ThrmlDutyCycle_Per1`
- `Rte_Call_NxtrDiagMgr_GetNTCFailed`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_ThrmlDutyCycle_Per1`


## Dependencies (direct includes)

- `Rte_Ap_ThrmlDutyCycle.h`
- `Ap_ThrmlDutyCycle_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `filters.h`
- `interpolation.h`
- `math.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [ThermalDutyCycle Integration Manual](./doc-thermaldutycycle-integration-manual/) `(ThermalDutyCycle_Integration_Manual.docx)`
- [Thermal Duty Cycle](./doc-thermal-duty-cycle-mdd/) `(Thermal_Duty_Cycle_MDD.docx)`


## Other artefacts (not converted)

- `ThrmDutyCycle/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `ThrmDutyCycle/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
