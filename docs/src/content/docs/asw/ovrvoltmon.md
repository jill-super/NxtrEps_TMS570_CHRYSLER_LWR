---
title: "Over-Voltage Monitoring (OvrVoltMon)"
description: "Over-Voltage Monitoring (OvrVoltMon) — AUTOSAR software component `Sa_OvrVoltMon` for the Chrysler LWR EPS — design coverage: OverVoltageMonitor."
---


# Over-Voltage Monitoring (`OvrVoltMon`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Over-Voltage Monitoring* (`OvrVoltMon`) — AUTOSAR software component `Sa_OvrVoltMon` for the Chrysler LWR EPS — design coverage: OverVoltageMonitor.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `OvrVoltMon/src/Sa_OvrVoltMon.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `OvrVoltMon_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_OvrVoltMon_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_phyOvrVoltFdbk_OP`
- `Rte_Call_OvrVoltMon_Per1`


## Dependencies (direct includes)

- `Rte_Sa_OvrVoltMon.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `Sa_OvrVoltMon_Cfg.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [OverVoltageMonitor](./doc-overvoltagemonitor-mdd/) `(OverVoltageMonitor_MDD.docx)`
- [OvrVoltMon Integration Manual](./doc-ovrvoltmon-integration-manual/) `(OvrVoltMon_Integration_Manual.docx)`


## Other artefacts (not converted)

- `OvrVoltMon/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `OvrVoltMon/doc/Design Review_OvrVoltMon.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `OvrVoltMon/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
