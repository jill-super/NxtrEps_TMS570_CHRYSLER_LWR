---
title: "Thermal Duty Cycle"
description: "Converted from Thermal_Duty_Cycle_MDD.docx"
---

> **Source:** `ThrmDutyCycle/doc/Thermal_Duty_Cycle_MDD.docx` (736,094 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module computes a duty cycle limit based on system temperatures.  It also outputs a unity scalar value to scale the assist command and a value representing the percentage of reduction.


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


## Program (fixed) Constants


### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.


#### Local


#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.


### Module specific Lookup Tables Constants


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

TableSize_m

FPM_FixedToFloat_m

FPM_FloatToFixed_m

LPF_KUpdate_f32_m

LPF_OpUpdate_f32_m

Abs_f32_m

IntplVarXY_u16_s16Xu16Y_Cnt

IntplVarXY_u16_u16Xu16Y_Cnt

Max_m

Min_m

Limit_m

DiagPStep_m

DiagNStep_m

DiagFailed_m


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only


### Local Function #1


#### Description


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: _Init1


#### Design Rationale

None


#### Module Outputs

None


#### Store Module Inputs to Local copies

IgnTimeOff_Sec_T_u32 = Rte_IRead_ThrmlDutyCycle_Init1_IgnTimeOff_Cnt_u32()

VehTimeValid_Cnt_T_lgc = Rte_IRead_ThrmlDutyCycle_Init1_VehTimeValid_Cnt_lgc()


#### Module Internal


## Periodic Functions


### Per: _Per1


#### Design Rationale

None


#### Program Flow Start

Rte_Call_ThrmlDutyCycle_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

CuTempEst_DegC_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_CuTempEst_DegC_f32()

FiltMeasTemp_DegC_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_FiltMeasTemp_DegC_f32()

FiltPkCurr_AmpSq_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_FilteredPkCurr_AmpSq_f32()

MagTempEst_DegC_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_MagTempEst_DegC_f32()

MotorVelCRF_MtrRadpS_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_MotorVelCRF_MtrRadpS_f32()

MtrPkCurr_AmpSq_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_MtrPkCurr_AmpSq_f32()

SiTempEst_DegC_T_f32 = Rte_IRead_ThrmlDutyCycle_Per1_SiTempEst_DegC_f32()

DefeatDutySvc_Cnt_T_lgc = Rte_IRead_ThrmlDutyCycle_Per1_DefeatDutySvc_Cnt_lgc_Cnt_lgc();

PrevAbsTempLimit_MtrNm_T_f32 = AbsTempLimit_MtrNm_M_f32

AbsMotorVelCRF_MtrRadpS_T_f32 = Abs_f32_m(MotorVelCRF_MtrRadpS_T_f32)

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_Thermistor, &DiagStsDefTemp_Cnt_T_lgc)


#### Temperature Selection


#### Load Limiting – Multiplier


#### Load Limiting – Max Filter Percentage


#### Load Limiting – Thermal Load Limit


#### Temperature Limiting


#### Temperature Limiting Status


#### Store Local copy of outputs into Module Outputs

AbsTempLimit_MtrNm_M_f32 = AbsTempLimitSlew_MtrNm_T_f32

Mult12Temp_DegC_D_f32 = Mult12Temp_DegC_T_f32

Mult36Temp_DegC_D_f32 = Mult36Temp_DegC_T_f32

MaxOut_AmpSq_D_u16p0 = MaxOut_Uls_T_u16p0

ThermLim_MtrNm_D_f32 = ThermalLoadLmt_MtrNm_T_f32

Mult1_Uls_D_u3p13 = Mult1_Uls_T_u3p13

Mult2_Uls_D_u3p13 = Mult2_Uls_T_u3p13

Mult3_Uls_D_u3p13 = Mult3_Uls_T_u3p13

Mult4_Uls_D_u3p13 = Mult4_Uls_T_u3p13

Mult5_Uls_D_u3p13 = Mult5_Uls_T_u3p13

Mult6_Uls_D_u3p13 = Mult6_Uls_T_u3p13

LastTblVal_MtrNm_D_u9p7 = LastTblValRaw_MtrNm_T_u9p7

LastTblValSlew_MtrNm_D_u9p7 = LastTblVal_MtrNm_T_u9p7

AbsTempLimit_MtrNm_D_f32 = AbsTempLimit_MtrNm_T_f32

ThrmLoadLmtTblYVal_MtrNm_D_f32 = DivFactor_MtrNm_T_f32

Rte_IWrite_ThrmlDutyCycle_Per1_DutyCycleLevel_Uls_f32(MaxSlowFilt_Uls_T_f32)

Rte_IWrite_ThrmlDutyCycle_Per1_ThermLimitPerc_Uls_f32(ThermLimitPerc_Uls_T_f32)

Rte_IWrite_ThrmlDutyCycle_Per1_ThermalLimit_MtrNm_f32(ThermalLimit_MtrNm_T_f32)


#### Program Flow End

Rte_Call_ThrmlDutyCycle_Per1_CP1_CheckpointReached()


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
| MtrPkCurr_AmpSq_f32 | MtrPkCurr_AmpSq_f32 | ThermalLimit_MtrNm_f32 |
| FilteredPkCurr_AmpSq_f32 | FilteredPkCurr_AmpSq_f32 | DutyCycleLevel_Uls_f32 |
| MotorVelCRF_MtrRadpS_f32 | MotorVelCRF_MtrRadpS_f32 | ThermLimitPerc_Uls_f32 |
| FiltMeasTemp_DegC_f32 | FiltMeasTemp_DegC_f32 |  |
| SiTempEst_DegC_f32 | SiTempEst_DegC_f32 |  |
| MagTempEst_DegC_f32 | MagTempEst_DegC_f32 |  |
| CuTempEst_DegC_f32 | CuTempEst_DegC_f32 |  |
| DiagStsDefTemp _Cnt_lgc | DiagStsDefTemp _Cnt_lgc |  |
| DefeatDutySvc_Cnt_lgc | DefeatDutySvc_Cnt_lgc |  |
| IgnTimeOff_Cnt_u32 | IgnTimeOff_Cnt_u32 |  |
| VehTimeValid_Cnt_lgc | VehTimeValid_Cnt_lgc |  |


**Table 2**

| Variable Name | Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- | --- |
| TrqCmdTblYRam_MtrNm_M_u9p7[8] | TrqCmdTblYRam_MtrNm_M_u9p7[8] | 2-7 | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| AbsTempFltAcc_Cnt_M_u16 | AbsTempFltAcc_Cnt_M_u16 | 1 | FULL | FULL | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Filter1KSV_M_str | Filter1KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 31250 |  |
|  | K_Uls_f32 | Single Precision Float | 0.326433727109184 | 0.326433727109184 |  |
| Filter2KSV_M_str | Filter2KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 31250 |  |
|  | K_Uls_f32 | Single Precision Float | 0.0387462804956383 | 0.0387462804956383 |  |
| Filter3KSV_M_str | Filter3KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 31250 |  |
|  | K_Uls_f32 | Single Precision Float | 0.0039438912246419 | 0.0039438912246419 |  |
| Filter4KSV_M_str | Filter4KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 31250 |  |
|  | K_Uls_f32 | Single Precision Float | 0.0020922033873435 | 0.0020922033873435 |  |
| Filter5KSV_M_str | Filter5KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 125000 |  |
|  | K_Uls_f32 | Single Precision Float | 0.000395090818303087 | 0.000395090818303087 |  |
| Filter6KSV_M_str | Filter6KSV_M_str | LPF32KSV_Str |  |  | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_UNSPECIFIED |
|  | SV_Uls_f32 | Single Precision Float | 0 | 125000 |  |
|  | K_Uls_f32 | Single Precision Float | 0.000157067296319927 | 0.000157067296319927 |  |
| AbsTempLimit_MtrNm_M_f32 | AbsTempLimit_MtrNm_M_f32 | Single Precision Float | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| Mult12Temp_DegC_D_f32 | Mult12Temp_DegC_D_f32 | Single Precision Float | -50 | 150 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| Mult36Temp_DegC_D_f32 | Mult36Temp_DegC_D_f32 | Single Precision Float | -50 | 150 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| MaxOut_AmpSq_D_u16p0 | MaxOut_AmpSq_D_u16p0 | 1 | 0 | 200 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| ThermLim_MtrNm_D_f32 | ThermLim_MtrNm_D_f32 | Single Precision Float | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| Mult1_Uls_D_u3p13 | Mult1_Uls_D_u3p13 | 2-13 | 0 | 0.5 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Mult2_Uls_D_u3p13 | Mult2_Uls_D_u3p13 | 2-13 | 0 | 0.5 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Mult3_Uls_D_u3p13 | Mult3_Uls_D_u3p13 | 2-13 | 0 | 0.5 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Mult4_Uls_D_u3p13 | Mult4_Uls_D_u3p13 | 2-13 | 0 | 0.5 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Mult5_Uls_D_u3p13 | Mult5_Uls_D_u3p13 | 2-13 | 0 | 2 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| Mult6_Uls_D_u3p13 | Mult6_Uls_D_u3p13 | 2-13 | 0 | 2 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| LastTblVal_MtrNm_D_u9p7 | LastTblVal_MtrNm_D_u9p7 | 2-7 | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| LastTblValSlew_MtrNm_D_u9p7 | LastTblValSlew_MtrNm_D_u9p7 | 2-7 | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_16 |
| AbsTempLimit_MtrNm_D_f32 | AbsTempLimit_MtrNm_D_f32 | Single Precision Float | 0 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| ThrmLoadLmtTblYVal_MtrNm_D_f32 | ThrmLoadLmtTblYVal_MtrNm_D_f32 | Single Precision Float | 0.01 | 8.8 | THRMLDUTYCYCLE_START_SEC_VAR_CLEARED_32 |
| eFilter3Value | eFilter3Value | 1 | 0 | 200 | THRMLDUTYCYCLE_START_SEC_VAR_SAVED_ZONEH_8 |
| eFilter4Value | eFilter4Value | 1 | 0 | 200 | THRMLDUTYCYCLE_START_SEC_VAR_SAVED_ZONEH_8 |
| eFilter5Value | eFilter5Value | 1 | 0 | 200 | THRMLDUTYCYCLE_START_SEC_VAR_SAVED_ZONEH_8 |
| eFilter6Value | eFilter6Value | 1 | 0 | 200 | THRMLDUTYCYCLE_START_SEC_VAR_SAVED_ZONEH_8 |
|  |  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_EOCCtrlTemp_DegC_f32 |
| k_CtrlTempSlc_Cnt_lgc |
| k_MtrPrTempSlc_Cnt_lgc |
| k_AbsMtrVelBkt_MtrRadps_f32 |
| t_MultTblX_DegC_s15p0[5] |
| t_Mult1NSTblY_Uls_u3p13[5] |
| t_Mult2NSTblY_Uls_u3p13[5] |
| t_Mult3NSTblY_Uls_u3p13[5] |
| t_Mult4NSTblY_Uls_u3p13[5] |
| t_Mult5NSTblY_Uls_u3p13[5] |
| t_Mult6NSTblY_Uls_u3p13[5] |
| t_Mult1STblY_Uls_u3p13[5] |
| t_Mult2STblY_Uls_u3p13[5] |
| t_Mult3STblY_Uls_u3p13[5] |
| t_Mult4STblY_Uls_u3p13[5] |
| t_Mult5STblY_Uls_u3p13[5] |
| t_Mult6STblY_Uls_u3p13[5] |
| t_LastTblValNS_MtrNm_u9p7[5] |
| t_LastTblValS_MtrNm_u9p7[5] |
| k_TrqCmdSlewDown_MtrNm_u9p7 |
| k_TrqCmdSlewUp_MtrNm_u9p7 |
| k_SlowFltTempSlc_Cnt_lgc |
| t_AbsTmpTblX_DegC_s15p0[2] |
| t_AbsTmpTblY_MtrNm_u9p7[2] |
| k_AbsTmpTrqSlewLmt_MtrNm_f32 |
| k_MultTempSlc_Cnt_lgc |
| k_AbsTempDiag_Cnt_str |
| k_DutyCycFltTrshld_AmpSq_u16p0 |
| t_ThrmLoadLmtTblX_AmpSq_u16p0[8] |
| t_ThrmLoadLmtTblY_MtrNm_u9p7[8] |
|  |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_FILT1LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*1.59) |
| D_FILT2LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*15.9) |
| D_FILT3LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*159) |
| D_FILT4LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*300) |
| D_FILT5LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*1590) |
| D_FILT6LPFKN_HZ_F32 | Single Precision Float | Hz | 1/(2*pi*4000) |
| D_1PERC_ULS_F32 | Single Precision Float | Unitless | 0.01 |
| D_FILTOUTLIM_ULS_F32 | Single Precision Float | Unitless | 200.0 |
| D_DEFEATDUTYCYCLELEVEL_ULS_F32 | Single Precision Float | Unitless | 0.0 |
| D_DEFEATTHERMLIMITPERC_ULS_F32 | Single Precision Float | Unitless | 0.0 |
| D_DEFEATTHERMLIMIT_MTRNM_F32 | Single Precision Float | MtrNm | 8.8 |
| D_TAU3_SEC_F32 | Single Precision Float | Sec | 159 |
| D_TAU4_SEC_F32 | Single Precision Float | Sec | 300 |
| D_TAU5_SEC_F32 | Single Precision Float | Sec | 1590 |
| D_TAU6_SEC_F32 | Single Precision Float | Sec | 4000 |


**Table 6**

| Constant Name |
| --- |
| D_MTRTRQCMDHILMT_MTRNM_F32 |
| D_ZERO_ULS_F32 |
| D_ONE_ULS_F32 |
| D_100MS_SEC_F32 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | StepVarXY_u16_s16Xu16Y_Cnt | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | TableX | sint16* | -32,768 | 32,767 | N/A |
|  | TableY | uint16* | 0 | 6553 | N/A |
|  | Size | uint16 |  |  | N/A |
|  | input | sint16 | -32,768 | 32,767 | N/A |
| Return Value | See description | uint16 | 0 | 6553 | 0 |


**Table 9**

| Data | Value |
| --- | --- |
| Rte_InitValue_CuTempEst_DegC_f32 | 0 |
| Rte_InitValue_DutyCycleLevel_Uls_f32 | 0 |
| Rte_InitValue_FiltMeasTemp_DegC_f32 | 0 |
| Rte_InitValue_FilteredPkCurr_AmpSq_f32 | 0 |
| Rte_InitValue_MagTempEst_DegC_f32 | 0 |
| Rte_InitValue_MotorVelCRF_MtrRadpS_f32 | 0 |
| Rte_InitValue_MtrPkCurr_AmpSq_f32 | 0 |
| Rte_InitValue_SiTempEst_DegC_f32 | 0 |
| Rte_InitValue_ DiagStsDefTemp _Cnt_lgc | FALSE |
| Rte_InitValue_ThermLimitPerc_Uls_f32 | 0 |
| Rte_InitValue_ThermalLimit_MtrNm_f32 | 8.8 |
| Rte_InitValue_DefeatDutySvc_Cnt_lgc | FALSE |
| Rte_InitValue_ IgnTimeOff_Cnt_u32 | 0 |
| Rte_InitValue_ VehTimeValid_Cnt_lgc | FALSE |


**Table 10**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| ThrmlDutyCycle_Init1 | On Event | On Init |
| ThrmlDutyCycle_Per1 | 100 ms | ALL |


**Table 11**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 12**

| Name of Sub Module | Software Segment |
| --- | --- |
| ThrmlDutyCycle_Init1 | RTE_START_SEC_AP_THRMLDUTYCYCLE_APPL_CODE |
| ThrmlDutyCycle_Per1 | RTE_START_SEC_AP_THRMLDUTYCYCLE_APPL_CODE |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 14**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version (implements SF-09 v001) | 21-May-12 | OT |
| 2 | 2.0 | Updated initial value of AssistThermScalar output, added limit on maxout terms to prevent overflow per new FDD design | 30-May-12 | LWW |
| 3 | 3.0 | Updated values of 6 filter embedded data constants- Anom 3445 | 16-June-12 | NRAR |
| 4 | 4.0 | Updated to SF-09 v003 | 09-Jul-12 | OT |
| 5 | 5.0 | Updated to SF-09 v004 | 09-Aug-12 | BWL |
| 6 | 6.0 | MDD fixes per unit test review. | 10-Aug-12 | BWL |
| 7 | 7.0 | Added checkpoints and memmap software segment is updated for static variables | 24-Sep-12 | Selva |
| 8 | 8.0 | Replaced multiplier interpolation with step function. | 16-Oct-12 | BWL |
| 9 | 9.0 | Updated to SF-09 v006 | 29-Jan-13 | Selva |
| 10 | 10 | Corrected Diag_Status reading function | 31-Jan-13 | Selva |
| 11 | 11 | Updated to SF-09 v007 | 20-Feb-13 | SP |
| 12 | 12 | Fix Anomoly 4517 | 28-Feb-13 | Selva |
|  |  |  |  |  |
