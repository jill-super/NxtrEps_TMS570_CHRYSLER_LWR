---
title: "Analog-to-Digital Converter Driver (Adc)"
description: "Analog-to-Digital Converter Driver (Adc) — ADC Unit 1 Complex Device Driver"
---


# Analog-to-Digital Converter Driver (`Adc`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Analog-to-Digital Converter Driver* (`Adc`) — ADC Unit 1 Complex Device Driver


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `Adc/src/Adc.c` | Implementation |
| `Adc/src/Adc2.c` | Implementation |
| `Adc/src/Adc_Common.c` | Implementation |
| `Adc/include/Adc.h` | Public interface |
| `Adc/include/Adc2.h` | Public interface |
| `Adc/include/Adc_Common.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Std_Types.h`
- `Adc.h`
- `Adc_Common.h`
- `adc_regs.h`
- `Ap_DiagMgr.h`
- `CalConstants.h`
- `SystemTime.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Adc2.h`
- `CDD_Data.h`
- `Calconstants.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Adc2](./doc-adc2-mdd/) `(Adc2_MDD.docx)`
- [Adc Common](./doc-adc-common-mdd/) `(Adc_Common_MDD.docx)`
- [Adc](./doc-adc-mdd/) `(Adc_MDD.docx)`
- [Integration Manual ADC](./doc-integration-manual-adc/) `(Integration_Manual_ADC.docx)`


## Other artefacts (not converted)

- `Adc/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `Adc/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
