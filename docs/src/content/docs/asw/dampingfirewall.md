---
title: "Damping Safety Firewall (DampingFirewall)"
description: "Damping Safety Firewall (DampingFirewall) — AUTOSAR software component `Ap_DampingFirewall` for the Chrysler LWR EPS — design coverage: Damping Firewall."
---


# Damping Safety Firewall (`DampingFirewall`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Damping Safety Firewall* (`DampingFirewall`) — AUTOSAR software component `Ap_DampingFirewall` for the Chrysler LWR EPS — design coverage: Damping Firewall.

RTE frame generator: `MICROSAR RTE Generator Version 2.19.1`.


Copyright headers found in sources reference: MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `DampingFirewall/src/Ap_DampingFirewall.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `DampingFirewall_Init1`
- `DampingFirewall_Per1`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_DampingFirewall_Per1`
- `Rte_IWrite_DampingFirewall_Per1`
- `Rte_IWriteRef_DampingFirewall_Per1`
- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_DampingFirewall_Per1`


## Dependencies (direct includes)

- `Rte_Ap_DampingFirewall.h`
- `Ap_DampingFirewall_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `fixmath.h`
- `filters.h`
- `interpolation.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Damping Firewall](./doc-damping-firewall-mdd/) `(Damping_Firewall_MDD.doc)`


## Other artefacts (not converted)

- `DampingFirewall/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `DampingFirewall/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
