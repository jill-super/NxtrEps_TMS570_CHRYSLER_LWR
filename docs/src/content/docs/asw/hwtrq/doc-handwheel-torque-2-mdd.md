---
title: "Handwheel Torque 2"
description: "Converted from Handwheel_Torque_2_MDD.docx"
---

> **Source:** `HwTrq/doc/Handwheel_Torque_2_MDD.docx` (380,511 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module – Handwheel Torque 2


# High-Level Description

This module serves as the implementation of the systematic coverage requirements for the handwheel torque module.  Several signals are calculated in parallel with Handwheel Torque.


# Figures


## Component Diagram


# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.


## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.


### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.


# Constant Data Dictionary


## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.


## Program(fixed) Constants


### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.


#### Local


#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.


### Module specific Lookup Tables Constants


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

FPM_Fix_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

Abs_f32_m

Abs_s16_m

Limit_m

IntplVarXY_u16_u16Xu16Y_Cnt

TableSize_m

DiagPStep_m

DiagNStep_m

DiagFailed_m

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only

None


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: _Init1


#### Design Rationale

None


#### Module Outputs

None


#### Module Internal

=


## Periodic Functions


### Per: _Per1


#### Design Rationale

None


#### Program Flow Start

Rte_Call_HwTrq2_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

SysCT1ADC_Volt_T_f32 = Rte_IRead_HwTrq2_Per1_SysCT1ADC_Volt_f32()

SysCT2ADC_Volt_T_f32 = Rte_IRead_HwTrq2_Per1_SysCT2ADC_Volt_f32()


#### Compute Alternate Diff Torque


#### Store Local copy of outputs into Module Outputs

SysCHwTorqueSqd_HwNmSq_M_f32 = SysCHwTorqueSqd_HwNmSq_T_f32

Rte_IWrite_HwTrq2_Per1_SysCHwTorqueSqd_HwNmSq_f32(SysCHwTorqueSqd_HwNmSq_T_f32)


#### Program Flow End

Rte_Call_HwTrq2_Per1_CP1_CheckpointReached()


### Per: _Per2


#### Design Rationale

None


#### Program Flow Start

Rte_Call_HwTrq2_Per2_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

AnaHwTorque_HwNm_T_f32 = Rte_IRead_HwTrq2_Per2_AnaHwTorque_HwNm_f32()

Torque1_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_SysCT1ADC_Volt_f32()

Torque2_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_SysCT2ADC_Volt_f32()

SysCHwTorqueSqd_HwNmSq_T_f32 = SysCHwTorqueSqd_HwNmSq_M_f32

T1Trim_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_T1TrimVal_Volt_f32()

T2Trim_Volt_T_f32 = Rte_IRead_HwTrq2_Per2_T2TrimVal_Volt_f32()

CorrDiagFiltOut_Volt_T_s4p11 = SysCCorrDiagFiltOut_Volt_M_s4p11

TDiagFiltSV_Volt_T_s4p27 = SysCTDiagFiltSV_Volt_M_s4p27


#### Systematic Cross Check Hw Diff Torque


#### T1 vs T2 Comparison Diagnostic


#### Store Local copy of outputs into Module Outputs

SysCAnaHwTorqueSqd_HwNmSq_D_f32 = AnaHwTorqueSqd_HwNmSq_T_f32

SysCHWTorqCorrLimDiff_HwNmSq_D_f32 = SysCHwTorqCorrLimDiff_HwNmSq_T_f32

SysCHwTorqCh1vsCh2CorrLim_HwNmSq_D_f32 = SysCHwTorqCh1vsCh2CorrLim_HwNmSq_T_f32


#### Program Flow End

Rte_Call_HwTrq2_Per2_CP1_CheckpointReached()


### Per: _Per3


#### Design Rationale

None


#### Program Flow Start

Rte_Call_HwTrq2_Per3_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

HwTrqComp_Volt_T_f32 = Rte_IRead_HwTrq2_Per3_AnaDiffHwTrq_Volt_f32()

TDiagFiltOut_Volt_T_s4p11 = SysCTDiagFiltOut_Volt_M_s4p11

TrqSum_Volt_T_s4p11 = SysCTrqSum_Volt_M_s4p11

CorrDiagFiltOut_Volt_T_s4p11 = SysCCorrDiagFiltOut_Volt_M_s4p11

SSDiagFiltSV_Volt_T_s4p27 = SysCSSDiagFiltSV_Volt_M_s4p27

CorrDiagFiltSV_Volt_T_s4p27 = SysCCorrDiagFiltSV_Volt_M_s4p27


#### Steady State Fault Detection, Common Mode Compensation Function


#### Store Local copy of outputs into Module Outputs

SysCCorrDiagFiltOut_Volt_M_s4p11 = CorrDiagFiltOut_Volt_T_s4p11


#### Program Flow End

Rte_Call_HwTrq2_Per3_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


## Serial Communication Functions

None


# Execution Requirements


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

INLINE functions defined in GlobalMacro.h are not unit tested.


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| SysCT1ADC_Volt_f32 | SysCT1ADC_Volt_f32 | SysCHwTorqueSqd_HwNmSq_f32 |
| SysCT2ADC_Volt_f32 | SysCT2ADC_Volt_f32 |  |
| AnaHwTorque_HwNm_f32 | AnaHwTorque_HwNm_f32 |  |
| AnaDiffHwTrq_Volt_f32 | AnaDiffHwTrq_Volt_f32 |  |
| HwTrqScaleVal_VoltsPerDeg_f32 | HwTrqScaleVal_VoltsPerDeg_f32 |  |
| T1TrimVal_Volt_f32 | T1TrimVal_Volt_f32 |  |
| T2TrimVal_Volt_f32 | T2TrimVal_Volt_f32 |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| SysCHwTorqueSqd_HwNmSq_M_f32 | Single Precision Float | 0 | 100 | HWTRQ2_START_SEC_VAR_CLEARED_32 |
| SysCTDiagFiltSV_Volt_M_s4p27 | 2-27 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_32 |
| SysCSSDiagFiltSV_Volt_M_s4p27 | 2-27 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_32 |
| SysCHwTorqCorrLimErrAcc_Cnt_M_u16 | 1 | FULL | FULL | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCCorrDiagFiltOut_Volt_M_s4p11 | 2-11 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCTDiagFiltOut_Volt_M_s4p11 | 2-11 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCTrqSum_Volt_M_s4p11 | 2-11 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCSumFltOut_Volt_M_u5p11 | 2-11 | 0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCSSDiagFiltOut_Volt_M_s4p11 | 2-11 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_CLEARED_16 |
| SysCCorrDiagFiltSV_Volt_M_s4p27 | 2-11 | -5.0 | 5.0 | HWTRQ2_START_SEC_VAR_SAVED_ZONEH_32 |
| SysCAnaHwTorqueSqd_HwNmSq_D_f32 | Single Precision Float | 0 | 100 | HWTRQ2_START_SEC_VAR_CLEARED_32 |
| SysCHWTorqCorrLimDiff_HwNmSq_D_f32 | Single Precision Float | 0 | 100 | HWTRQ2_START_SEC_VAR_CLEARED_32 |
| SysCHwTorqCh1vsCh2CorrLim_HwNmSq_D_f32 | Single Precision Float | 0 | 100 | HWTRQ2_START_SEC_VAR_CLEARED_32 |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_TbarStiff_NmpDeg_f32 |
| k_MaxTrqSumLmt_Volts_f32 |
| k_TdiagLim_Volts_u5p11 |
| k_CorrDiagFiltActiv_Volts_u5p11 |
| k_CorrDiagKn_Cnts_u16 |
| k_TdiagCorrLim_Volts_u5p11 |
| k_SSDiagKn_Cnts_u16 |
| k_SSDiagLim_Volts_u5p11 |
| t_TDiagFiltKnTbl_Cnt_u16[] |
| k_SSFiltRecLim_Volt_u5p11 |
| t_TDiagIndptTbl_Volts_u5p11[] |
| t_SysCHwTorqCorrLimXAxis_HwNm_u4p12[] |
| t_SysCHwTorqCorrLimYAxis_HwNmSq_u7p9[] |
| k_SysCHwTorqCorrLimDiag_Cnt_str |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_SSDIAGNFILTSVLMT_VOLT_S4P27 | 2-27 | Volts | FPM_Fix_m((uint32)(k_SSDiagLim_Volts_u5p11 + 1), u21p11_T, s4p27_T) |
| D_TWO_ULS_F32 | Single Precision Float | Unitless | 2 |
| D_HWTRQLMT_HWNMSQ_F32 | Single Precision Float | HWNMSQ | 100 |


**Table 6**

| Constant Name |
| --- |
| D_ZERO_CNT_U16 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Data | Value |
| --- | --- |
| Rte_InitValue_AnaDiffHwTrq_Volt_f32 | 0 |
| Rte_InitValue_AnaHwTorque_HwNm_f32 | 0 |
| Rte_InitValue_HwTrqScaleVal_VoltsPerDeg_f32 | 0 |
| Rte_InitValue_SysCHwTorqueSqd_HwNmSq_f32 | 0 |
| Rte_InitValue_SysCT1ADC_Volt_f32 | 0 |
| Rte_InitValue_SysCT2ADC_Volt_f32 | 0 |
| Rte_InitValue_T1TrimVal_Volt_f32 | 0 |
| Rte_InitValue_T2TrimVal_Volt_f32 | 0 |


**Table 9**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| HwTrq2_Init1 | On Event | On Init |
| HwTrq2_Per1 | 2 ms | ALL |
| HwTrq2_Per2 | 4 ms | ALL |
| HwTrq2_Per3 | 100 ms | ALL |


**Table 10**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 11**

| Name of Sub Module | Software Segment |
| --- | --- |
| HwTrq2_Init1 | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per1 | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per2 | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |
| HwTrq2_Per3 | RTE_START_SEC_SA_HWTRQ2_APPL_CODE |


**Table 12**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 13**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version | 12-Oct-12 | OT |
| 2 | 2.0 | Anomaly 2824 – T1 vs T2 comparison cal usage | 24-Oct-12 | OT |
| 3 | 3.0 | Updates for Trim and Scale values, update for anomaly 3994 | 30-Oct-12 | OT |
| 4 | 4.0 | ICR # 3928: Software range limit applied for SysCHwTorqueSqd_HwNmSq_T_f32 | 06-Feb-13 | SP |
| 5 | 5.0 | ICR #7140: Store the values of steady state filter and Common Mode Compensation | 22-Apr-13 | SP |
|  |  |  |  |  |
