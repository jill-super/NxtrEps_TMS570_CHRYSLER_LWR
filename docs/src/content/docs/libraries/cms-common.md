---
title: "Common Manufacturing Services (CMS_Common)"
description: "Common Manufacturing Services (CMS_Common) — Common Manufacturing Program Interface for XCP and ISO services"
---


# Common Manufacturing Services (`CMS_Common`)

<span class="origin-badge origin-custom">Custom</span> <span class="origin-badge origin-vector">Contains Vector-derived file(s)</span>

> **Origin:** Nexteer in-house manufacturing/diagnostics services. Note: `EPS_DiagSrvcs_XCP.Vector.c` is derived from Vector XCP sample code.

## Purpose

*Common Manufacturing Services* (`CMS_Common`) — Common Manufacturing Program Interface for XCP and ISO services


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `CMS_Common/src/EPS_DiagSrvcs_ISO.c` | Implementation |
| `CMS_Common/src/EPS_DiagSrvcs_XCP.Vector.c` | Implementation |
| `CMS_Common/src/EPS_DiagSrvcs_XCP.c` | Implementation |
| `CMS_Common/include/EPS_DiagSrvcs_CommonData.h` | Public interface |
| `CMS_Common/include/EPS_DiagSrvcs_ISO.h` | Public interface |
| `CMS_Common/include/EPS_DiagSrvcs_SrvcLUTbl.h` | Public interface |
| `CMS_Common/include/EPS_DiagSrvcs_XCP.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `EPS_DiagSrvcs_CommonData.h`
- `EPS_DiagSrvcs_SrvcLUTbl.h`
- `EPS_DiagSrvcs_ISO.Interface.h`
- `EPS_DiagSrvcs_ISO.h`
- `EPS_DiagSrvcs_XCP.Interface.h`
- `EPS_DiagSrvcs_XCP.h`
- `SystemTime.h`
- `tiotp_regs.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Other artefacts (not converted)

- `CMS_Common/doc/CMSCommon Design Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `CMS_Common/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `CMS_Common/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
