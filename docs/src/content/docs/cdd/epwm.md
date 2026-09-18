---
title: "Enhanced Pulse-Width Modulation Driver (ePWM)"
description: "Enhanced Pulse-Width Modulation Driver (ePWM) — AUTOSAR software component `Ap_ePWM2` for the Chrysler LWR EPS — design coverage: NHetRegisters; Nhet 1."
---


# Enhanced Pulse-Width Modulation Driver (`ePWM`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Enhanced Pulse-Width Modulation Driver* (`ePWM`) — AUTOSAR software component `Ap_ePWM2` for the Chrysler LWR EPS — design coverage: NHetRegisters; Nhet 1.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `ePWM/src/Ap_ePWM2.c` | Implementation |
| `ePWM/src/Nhet.c` | Implementation |
| `ePWM/src/Nhet2_ePWM_Prog.c` | Implementation |
| `ePWM/src/Nhet2_ePWM_Prog.het` | Source |
| `ePWM/src/ePWM.c` | Implementation |
| `ePWM/include/Nhet.h` | Public interface |
| `ePWM/include/Nhet2_ePWM_Prog.h` | Public interface |
| `ePWM/include/ePWM.h` | Public interface |
| `ePWM/include/std_nhet.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `ePWM2_Trns1`
- `ePWM2_Trns2`
- `ePWM_Init1`
- `ePWM_Per1`


## Dependencies (direct includes)

- `Rte_Ap_ePWM2.h`
- `ePwm.h`
- `MemMap.h`
- `Nhet.h`
- `std_nhet.h`
- `Nhet2_ePWM_Prog.h`
- `CDD_Data.h`
- `CalConstants.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [NHetRegisters](./doc-nhetregisters/) `(NHetRegisters.pdf)`
- [Nhet 1](./doc-nhet-1-mdd/) `(Nhet_1_MDD.docx)`
- [RegisterReference EPWM](./doc-registerreference-epwm/) `(RegisterReference_EPWM.pdf)`
- [ePWM 1](./doc-epwm-1-mdd/) `(ePWM_1_MDD.docx)`
- [ePWM 2](./doc-epwm-2-mdd/) `(ePWM_2_MDD.docx)`
- [ePWM Integration Manual](./doc-epwm-integration-manual/) `(ePWM_Integration_Manual.docx)`


## Other artefacts (not converted)

- `ePWM/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `ePWM/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
