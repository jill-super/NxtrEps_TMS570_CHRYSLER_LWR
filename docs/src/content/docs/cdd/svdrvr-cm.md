---
title: "Space-Vector Motor Driver – Current Mode (SVDrvr_CM)"
description: "Space-Vector Motor Driver – Current Mode (SVDrvr_CM) — Non-AUTOSAR PWM driver required to perform EPS motor"
---


# Space-Vector Motor Driver – Current Mode (`SVDrvr_CM`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Space-Vector Motor Driver – Current Mode* (`SVDrvr_CM`) — Non-AUTOSAR PWM driver required to perform EPS motor


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `SVDrvr_CM/src/PwmCdd.c` | Implementation |
| `SVDrvr_CM/include/PwmCdd.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Std_Types.h`
- `PwmCdd.h`
- `CDD_Data.h`
- `CalConstants.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CDD_Func.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [PWMCdd Integration Manual](./doc-pwmcdd-integration-manual/) `(PWMCdd_Integration_Manual.docx)`
- [PWM CDD](./doc-pwm-cdd-mdd/) `(PWM_CDD_MDD.docx)`


## Other artefacts (not converted)

- `SVDrvr_CM/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `SVDrvr_CM/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
