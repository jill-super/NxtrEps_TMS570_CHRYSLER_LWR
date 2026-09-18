---
title: "Motor Control – Current Mode (MtrCtrl_CM)"
description: "Motor Control – Current Mode (MtrCtrl_CM) — AUTOSAR software component `Ap_CurrCmd` for the Chrysler LWR EPS — design coverage: CurrCmd; CurrParamComp."
---


# Motor Control – Current Mode (`MtrCtrl_CM`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Motor Control – Current Mode* (`MtrCtrl_CM`) — AUTOSAR software component `Ap_CurrCmd` for the Chrysler LWR EPS — design coverage: CurrCmd; CurrParamComp.

RTE frame generator: `MICROSAR RTE Generator Version 2.17.2`.


Copyright headers found in sources reference: Texas Instruments, MICROSAR.


## Key files


| File | Role |
| --- | --- |
| `MtrCtrl_CM/src/Ap_CurrCmd.c` | Implementation |
| `MtrCtrl_CM/src/Ap_CurrParamComp.c` | Implementation |
| `MtrCtrl_CM/src/Ap_PICurrCntrl.c` | Implementation |
| `MtrCtrl_CM/src/Ap_PeakCurrEst.c` | Implementation |
| `MtrCtrl_CM/src/Ap_QuadDet.c` | Implementation |
| `MtrCtrl_CM/src/Ap_TrqCanc.c` | Implementation |
| `MtrCtrl_CM/src/Ap_TrqCmdScl.c` | Implementation |
| `MtrCtrl_CM/include/Ap_MtrCtrl.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Runnable entities


Detected from `Runnable Entity Name:` markers in the sources:

- `CurrCmd_Init`
- `CurrCmd_Per1`
- `CurrParamComp_Init`
- `CurrParamComp_Per1`
- `CurrParamComp_Per2`
- `SCom_EOLNomMtrParam_Get`
- `SCom_EOLNomMtrParam_Set`
- `PICurrCntrl_Per2`
- `PeakCurrEst_Per1`
- `PeakCurrEst_Per2`
- `QuadDet_Per1`
- `TrqCanc_Init`
- `TrqCanc_Per1`
- `TrqCanc_Scom_ReadCogTrqCal`
- `TrqCanc_Scom_SetCogTrqCal`
- `TrqCmdScl_Per1`
- `TrqCmdScl_SCom_Get`
- `TrqCmdScl_SCom_Set`


## RTE ports used (sample)


Sender/receiver and client/server accessors referenced by the implementation (truncated sample):

- `Rte_IRead_CurrCmd_Per1`
- `Rte_IWrite_CurrCmd_Per1`
- `Rte_IWriteRef_CurrCmd_Per1`
- `Rte_Call_CurrCmd_Per1`
- `Rte_IWrite_CurrParamComp_Init`
- `Rte_IWriteRef_CurrParamComp_Init`
- `Rte_IRead_CurrParamComp_Per1`
- `Rte_IWrite_CurrParamComp_Per1`
- `Rte_IWriteRef_CurrParamComp_Per1`
- `Rte_Call_CurrParamComp_Per1`
- `Rte_IRead_CurrParamComp_Per2`
- `Rte_Call_CurrParamComp_Per2`
- `Rte_Call_EOLNomMtrParamBlk_WriteBlock`
- `Rte_IRead_PICurrCntrl_Per2`
- `Rte_IWrite_PICurrCntrl_Per2`
- `Rte_IWriteRef_PICurrCntrl_Per2`
- `Rte_Call_PICurrCntrl_Per2`
- `Rte_IRead_PeakCurrEst_Per1`
- `Rte_IWrite_PeakCurrEst_Per1`
- `Rte_IWriteRef_PeakCurrEst_Per1`
- `Rte_Call_PeakCurrEst_Per1`
- `Rte_IWrite_PeakCurrEst_Per2`
- `Rte_IWriteRef_PeakCurrEst_Per2`
- `Rte_Call_PeakCurrEst_Per2`
- `Rte_IRead_QuadDet_Per1`


## Dependencies (direct includes)

- `Rte_Ap_CurrCmd.h`
- `Ap_CurrCmd_Cfg.h`
- `CalConstants.h`
- `fixmath.h`
- `interpolation.h`
- `filters.h`
- `Ap_MtrCtrl.h`
- `MtrCtrl_Cfg.h`
- `MemMap.h`
- `Rte_Ap_CurrParamComp.h`
- `Ap_CurrParamComp_Cfg.h`
- `Interpolation.h`
- `GlobalMacro.h`
- `Rte_Ap_PICurrCntrl.h`
- `Ap_PICurrCntrl_Cfg.h`
- `Std_Types.h`
- `Rte_Ap_PeakCurrEst.h`
- `Ap_PeakCurrEst_Cfg.h`
- `Rte_Ap_QuadDet.h`
- `Ap_QuadDet_Cfg.h`
- `Rte_Ap_TrqCanc.h`
- `Ap_TrqCanc_Cfg.h`
- `Rte_Ap_TrqCmdScl.h`
- `Ap_TrqCmdScl_Cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [CurrCmd](./doc-currcmd-mdd/) `(CurrCmd_MDD.doc)`
- [CurrParamComp](./doc-currparamcomp-mdd/) `(CurrParamComp_MDD.docx)`
- [MtrCntrl Integration Manual](./doc-mtrcntrl-integration-manual/) `(MtrCntrl_Integration_Manual.docx)`
- [PICurrentContrl](./doc-picurrentcontrl/) `(PICurrentContrl.doc)`
- [PeakCurrEst](./doc-peakcurrest-mdd/) `(PeakCurrEst_MDD.docx)`
- [Quadrant Detection](./doc-quadrant-detection-mdd/) `(Quadrant_Detection_MDD.docx)`
- [TorqueCmdScaling](./doc-torquecmdscaling-mdd/) `(TorqueCmdScaling_MDD.doc)`
- [TrqCanc](./doc-trqcanc-mdd/) `(TrqCanc_MDD.docx)`


## Other artefacts (not converted)

- `MtrCtrl_CM/doc/Data Dictionary.xls` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrCtrl_CM/doc/Design Review_MtrCtrl_CM.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `MtrCtrl_CM/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
