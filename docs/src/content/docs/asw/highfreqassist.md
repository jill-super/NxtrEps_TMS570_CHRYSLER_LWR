---
title: "High-Frequency Assist Control (HighFreqAssist)"
description: "High-Frequency Assist Control (HighFreqAssist) — AUTOSAR software component `Ap_HighFreqAssist` for the Chrysler LWR EPS — design coverage: High Frequency Assist."
---


# High-Frequency Assist Control (`HighFreqAssist`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*High-Frequency Assist Control* (`HighFreqAssist`) — AUTOSAR software component `Ap_HighFreqAssist` for the Chrysler LWR EPS — design coverage: High Frequency Assist.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `HighFreqAssist/src/Ap_HighFreqAssist.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `HighFreqAssist_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_HighFreqAssist_Per1`
- `Rte_IWrite_HighFreqAssist_Per1`
- `Rte_IWriteRef_HighFreqAssist_Per1`
- `Rte_Call_HighFreqAssist_Per1`


## Dependencies (direct includes)

- `Rte_Ap_HighFreqAssist.h`
- `Ap_HighFreqAssist_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `filters.h`
- `interpolation.h`
- `fixmath.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [HighFreqAssist Integration Manual](./doc-highfreqassist-integration-manual/) `(HighFreqAssist_Integration_Manual.docx)`
- [High Frequency Assist](./doc-high-frequency-assist-mdd/) `(High_Frequency_Assist_MDD.docx)`


## Other artefacts (not converted)

- `HighFreqAssist/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `HighFreqAssist/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
