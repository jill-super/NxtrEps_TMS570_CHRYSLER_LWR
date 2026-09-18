---
title: "Battery Voltage Diagnostics (BVDiag)"
description: "AUTOSAR software component `Ap_BVDiag` for the Chrysler LWR EPS — design coverage: Battery Voltage Diagnostics."
---


# Battery Voltage Diagnostics (`BVDiag`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

AUTOSAR software component `Ap_BVDiag` for the Chrysler LWR EPS — design coverage: Battery Voltage Diagnostics.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `BVDiag/src/Ap_BVDiag.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `BVDiag_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_BVDiag_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_SystemTime_DtrmnElapsedTime`
- `Rte_Call_SystemTime_GetSystemTime`
- `Rte_Call_BVDiag_Per1`


## Dependencies (direct includes)

- `Rte_Ap_BVDiag.h`
- `Ap_BVDiag_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `SystemTime.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [BVDiag Integration Manual](./doc-bvdiag-integration-manual/) `(BVDiag_Integration_Manual.docx)`
- [Battery Voltage Diagnostics](./doc-battery-voltage-diagnostics/) `(Battery_Voltage_Diagnostics.doc)`


## Other artefacts (not converted)

- `BVDiag/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `BVDiag/doc/Design Review Template.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `BVDiag/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
