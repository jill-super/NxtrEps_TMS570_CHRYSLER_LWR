---
title: "Generated Configuration Data (GenData)"
description: "Generated Configuration Data (GenData) — DaVinci-generated BSW and RTE configuration artefacts"
---


# Generated Configuration Data (`GenData`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector DaVinci-generated. All files below are outputs of the configuration toolchain, not hand-written sources.

## Purpose

*Generated Configuration Data* (`GenData`) — Central store of generated C/H configuration for BSW modules and the RTE: `SwProject/Source/GenData/` (per-module `*_Cfg.h`, e.g. `Ap_Assist_Cfg.h`, `Adc_Cfg.h`), `GenDataRte/` (RTE implementation), `GenDataOS/` (OS objects). The master configuration is the DaVinci project in `Chrysler_LWR_EPS_TMS570/Tools/AsrProject` (`EPS.dcf`).


## Contents

`GenData/` currently holds 187 file(s), including:

- `Adc2_Cfg.h`
- `Adc_Cfg.h`
- `Ap_AbsHwPosScom_Cfg.h`
- `Ap_ActivePull_Cfg.h`
- `Ap_ApXcp_Cfg.c`
- `Ap_ApXcp_Cfg.h`
- `Ap_ArbLmt_Cfg.h`
- `Ap_AssistFirewall_Cfg.h`
- `Ap_Assist_Cfg.h`
- `Ap_AstLmt_Cfg.h`
- `Ap_AvgFricLrn_Cfg.h`
- `Ap_BVDiag_Cfg.h`
- `Ap_BatteryVoltage_Cfg.h`
- `Ap_CtrldDisShtdn_Cfg.h`
- `Ap_CurrCmd_Cfg.h`
- `Ap_CurrParamComp_Cfg.h`
- `Ap_DampingFirewall_Cfg.h`
- `Ap_Damping_Cfg.h`
- `Ap_DigPhsReasDiag_Cfg.h`
- `Ap_EOTActuatorMng_Cfg.h`
- `Ap_ElePwr_Cfg.h`
- `Ap_FrqDepDmpnInrtCmp_Cfg.h`
- `Ap_Gsod_Cfg.h`
- `Ap_HaLFTO_Cfg.h`
- `Ap_HiLoadStall_Cfg.h`
- `Ap_HighFreqAssist_Cfg.h`
- `Ap_HwPwUp_Cfg.h`
- `Ap_HystComp_Cfg.h`
- `Ap_LmtCod_Cfg.h`
- `Ap_LrnEOT_Cfg.h`
- `Ap_MtrTempEst_Cfg.h`
- `Ap_PAwTO_Cfg.h`
- `Ap_PICurrCntrl_Cfg.h`
- `Ap_PeakCurrEst_Cfg.h`
- `Ap_Polarity_Cfg.h`
- `Ap_PwrLmtFuncCr_Cfg.h`
- `Ap_QuadDet_Cfg.h`
- `Ap_ReturnFirewall_Cfg.h`
- `Ap_Return_Cfg.h`
- `Ap_SignlCondn_Cfg.h`
- …and 147 more.

## Usage

Include the matching `*_Cfg.h` from application or CDD code; regenerate via DaVinci whenever the Electronic Control Unit configuration changes. Related visualisation: the [WdgM supervision graph](../../general/vector-config/doc-wdgm-graph/).
