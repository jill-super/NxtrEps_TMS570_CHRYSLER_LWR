---
title: "TMS570 Micro Diagnostics (TMS570_uDiag)"
description: "TMS570 Micro Diagnostics (TMS570_uDiag) — Data and Prefetch Abort Handler"
---


# TMS570 Micro Diagnostics (`TMS570_uDiag`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*TMS570 Micro Diagnostics* (`TMS570_uDiag`) — Data and Prefetch Abort Handler


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `TMS570_uDiag/src/AbortHandler.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagCCRM.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagClockMonitor.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagECC.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagESM.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagFPU.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagIOMM.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagLossOfExec.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagParity.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagResetHandler.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagStaticRegs.c` | Implementation |
| `TMS570_uDiag/src/Cd_uDiagUtility.asm` | Assembly |
| `TMS570_uDiag/src/Cd_uDiagVIM.c` | Implementation |
| `TMS570_uDiag/src/FlsTst.c` | Implementation |
| `TMS570_uDiag/src/FlsTst_Irq.c` | Implementation |
| `TMS570_uDiag/src/OsErrCallouts.c` | Implementation |
| `TMS570_uDiag/src/RednRpdShtdn.c` | Implementation |
| `TMS570_uDiag/src/WdgResetHandler.c` | Implementation |
| `TMS570_uDiag/src/dabort.asm` | Assembly |
| `TMS570_uDiag/src/pabort.asm` | Assembly |
| `TMS570_uDiag/src/undefinst.asm` | Assembly |
| `TMS570_uDiag/include/Cd_uDiagUtility.h` | Public interface |
| `TMS570_uDiag/include/FlsTst.h` | Public interface |
| `TMS570_uDiag/include/RednRpdShtdn.h` | Public interface |
| `TMS570_uDiag/include/uDiag.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `uDiagECC_Per`
- `uDiagLossOfExec_Per2`
- `uDiagLossOfExec_Per3`
- `uDiagResetHandler_Init`
- `uDiagStaticRegs_Per`
- `uDiagVIM_Per`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_Call_NxtrDiagMgr_SetNTCStatus`
- `Rte_Call_uDiagECC_Per`
- `Rte_Call_uDiagLossOfExec_Per2`
- `Rte_Call_uDiagLossOfExec_Per3`
- `Rte_Call_uDiagStaticRegs_Per`
- `Rte_Call_uDiagVIM_Per`


## Dependencies (direct includes)

- `Std_Types.h`
- `ResetCause.h`
- `RednRpdShtdn.h`
- `Rte_Cd_uDiag.h`
- `uDiag.h`
- `esm_regs.h`
- `dcc_regs.h`
- `system_regs.h`
- `uDiag_Cfg.h`
- `flash_regs.h`
- `tcram_regs.h`
- `GlobalMacro.h`
- `CalConstants.h`
- `MemMap.h`
- `Interrupts.h`
- `Os.h`
- `Ap_DiagMgr.h`
- `sys_core.h`
- `Cd_uDiagUtility.h`
- `iomm_regs.h`
- `adc_regs.h`
- `htu_regs.h`
- `n2het_regs.h`
- `dcan_regs.h`
- `appinit_cfg.h`
- `interrupts.h`
- `sys_common.h`
- `vim_regs.h`
- `tcb.h`
- `FlsTst.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Cd uDiagFPU](./doc-cd-udiagfpu-mdd/) `(Cd_uDiagFPU_MDD.docx)`
- [Cd uDiagUtility](./doc-cd-udiagutility-mdd/) `(Cd_uDiagUtility_MDD.docx)`
- [Cd uDiag Integration Manual](./doc-cd-udiag-integration-manual/) `(Cd_uDiag_Integration_Manual.docx)`
- [FlsTst Integration Manual](./doc-flstst-integration-manual/) `(FlsTst_Integration_Manual.docx)`
- [FlsTst](./doc-flstst-mdd/) `(FlsTst_MDD.docx)`
- [OsErrCallouts](./doc-oserrcallouts-mdd/) `(OsErrCallouts_MDD.docx)`


## Other artefacts (not converted)

- `TMS570_uDiag/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `TMS570_uDiag/doc/uDiag_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `TMS570_uDiag/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
