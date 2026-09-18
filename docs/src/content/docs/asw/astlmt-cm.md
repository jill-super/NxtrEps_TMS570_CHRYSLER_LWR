---
title: "Assist Sum Limit – Current Mode (AstLmt_CM)"
description: "Assist Sum Limit – Current Mode (AstLmt_CM) — AUTOSAR software component `Ap_AstLmt` for the Chrysler LWR EPS — design coverage: Assist Sum Limit CurrentMode; AstLmt CM IntegrationManual."
---


# Assist Sum Limit – Current Mode (`AstLmt_CM`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Assist Sum Limit – Current Mode* (`AstLmt_CM`) — AUTOSAR software component `Ap_AstLmt` for the Chrysler LWR EPS — design coverage: Assist Sum Limit CurrentMode; AstLmt CM IntegrationManual.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `AstLmt_CM/src/Ap_AstLmt.c` | Implementation |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `AstLmt_Init`
- `AstLmt_Per1`
- `AstLmt_Scom_GetSteeringAssistDefeat`
- `AstLmt_Scom_ManualTrqCmd`
- `AstLmt_Scom_SetSteeringAssistDefeat`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_AstLmt_Per1`
- `Rte_IWrite_AstLmt_Per1`
- `Rte_IWriteRef_AstLmt_Per1`
- `Rte_Call_AstLmt_Per1`
- `Rte_Call_SteeringAsstDefeat_WriteBlock`


## Dependencies (direct includes)

- `Rte_Ap_AstLmt.h`
- `Ap_AstLmt_Cfg.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Assist Sum Limit CurrentMode](./doc-assist-sum-limit-currentmode-mdd/) `(Assist_Sum_Limit_CurrentMode_MDD.docx)`
- [AstLmt CM IntegrationManual](./doc-astlmt-cm-integrationmanual/) `(AstLmt_CM_IntegrationManual.docx)`


## Other artefacts (not converted)

- `AstLmt_CM/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `AstLmt_CM/doc/Design Review_AssistSumLmt_CM.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `AstLmt_CM/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
