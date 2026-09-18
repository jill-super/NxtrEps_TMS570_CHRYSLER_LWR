---
title: "Global Signal Overwrite Diagnostics (Gsod)"
description: "Global Signal Overwrite Diagnostics (Gsod) — AUTOSAR software component `Ap_Gsod` for the Chrysler LWR EPS — design coverage: Gsod."
---


# Global Signal Overwrite Diagnostics (`Gsod`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Global Signal Overwrite Diagnostics* (`Gsod`) — AUTOSAR software component `Ap_Gsod` for the Chrysler LWR EPS — design coverage: Gsod.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1 (Beta)`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `Gsod/src/Ap_Gsod.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `Gsod_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_Gsod_Per1`


## Dependencies (direct includes)

- `Rte_Ap_Gsod.h`
- `Ap_Gsod_Cfg.h`
- `Os.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Gsod](./doc-gsod-mdd/) `(Gsod_MDD.docx)`


## Other artefacts (not converted)

- `Gsod/doc/Data Dictionary.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `Gsod/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
