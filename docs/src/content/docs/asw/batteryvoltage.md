---
title: "Battery Voltage Monitoring (BatteryVoltage)"
description: "Battery Voltage Monitoring (BatteryVoltage) — AUTOSAR software component `Ap_BatteryVoltage` for the Chrysler LWR EPS — design coverage: Battery Voltage."
---


# Battery Voltage Monitoring (`BatteryVoltage`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Battery Voltage Monitoring* (`BatteryVoltage`) — AUTOSAR software component `Ap_BatteryVoltage` for the Chrysler LWR EPS — design coverage: Battery Voltage.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1 (Beta)`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `BatteryVoltage/src/Ap_BatteryVoltage.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `BatteryVoltage_Per1`
- `BatteryVoltage_Per2`
- `BatteryVoltage_SCom_ClearTransOvData`
- `BatteryVoltage_SCom_ReadTransOvData`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_BatteryVoltage_Per1`
- `Rte_IWrite_BatteryVoltage_Per1`
- `Rte_IWriteRef_BatteryVoltage_Per1`
- `Rte_Call_FltInjection_SCom`
- `Rte_Call_BatteryVoltage_Per1`
- `Rte_IRead_BatteryVoltage_Per2`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_BatteryVoltage_Per2`
- `Rte_Call_OvervoltageData_SetRamBlockStatus`


## Dependencies (direct includes)

- `Rte_Ap_BatteryVoltage.h`
- `Ap_BatteryVoltage_Cfg.h`
- `fixmath.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [BatteryVoltage Integration Manual](./doc-batteryvoltage-integration-manual/) `(BatteryVoltage_Integration_Manual.docx)`
- [Battery Voltage](./doc-battery-voltage-mdd/) `(Battery_Voltage_MDD.doc)`


## Other artefacts (not converted)

- `BatteryVoltage/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `BatteryVoltage/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
