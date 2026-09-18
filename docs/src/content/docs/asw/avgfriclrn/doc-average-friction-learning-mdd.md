---
title: "Average Friction Learning"
description: "Converted from Average_Friction_Learning_MDD.docx"
---

> **Source:** `AvgFricLrn/doc/Average_Friction_Learning_MDD.docx` (1,776,255 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module estimates the gear friction changes from the baseline friction and provides compensation.  It is based on the column torque and handwheel angle.  It is primarily active at higher speeds.


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

TableSize_m

LPF_Init_f32_m

LPF_KUpdate_f32_m

LPF_OpUpdate_f32_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

IntplVarXY_u16_u16Xu16Y_Cnt

Abs_f32_m

Limit_m

Min_m

Max_m


## Data Hiding Functions

Rte_Pim_AvgFricLrnData()

Rte_Call_AvgFricLrnData_WriteBlock()


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only


### Load Buffer


#### Description


### Handwheel Angle Constraint


#### Description


### Handwheel Velocity Constraint


#### Description


### Vehicle Speed Constraint


#### Description


### Friction Learning


#### Friction Learning


#### Range Counter Manager


#### Calculate Average Friction


### Baseline Mode (reset to baseline)


#### Description


### Clear Mode (reset to zero)


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


#### Module Internal


## Periodic Functions


### Per: _Per1


#### Design Rationale

None


#### Program Flow Start


#### Rte_Call_AvgFricLrn_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

HwAngUnfilt_HwDeg_T_f32 = Rte_IRead_AvgFricLrn_Per1_HwAng_HwDeg_f32()

HwPosAuthorityUnfilt_Uls_T_f32 = Rte_IRead_AvgFricLrn_Per1_HwPosAuthority_Uls_f32()

HwTrq_HwNm_T_f32 = Rte_IRead_AvgFricLrn_Per1_HwTrq_HwNm_f32()

HwVelUnfilt_HwRadpS_T_f32 = Rte_IRead_AvgFricLrn_Per1_HwVel_HwRadpS_f32()

LatAccUnfilt_g_T_f32 = Rte_IRead_AvgFricLrn_Per1_LatAcc_g_f32()

MtrTrq_MtrNm_T_f32 = Rte_IRead_AvgFricLrn_Per1_CRFMtrTrq_MtrNm_f32()

TemperatureUnfilt_DegC_T_f32 = Rte_IRead_AvgFricLrn_Per1_Temperature_DegC_f32()

VehSpdUnfilt_Kph_T_f32 = Rte_IRead_AvgFricLrn_Per1_VehSpd_Kph_f32()

VehicleSpeedValid_Cnt_T_lgc = Rte_IRead_AvgFricLrn_Per1_VehicleSpeedValid_Cnt_lgc()

LatAccUnfilt_MpSecSqrd_T_f32 = LatAccUnfilt_g_T_f32 * D_ONEG_MPSECSQRD_F32

HwVelUnfilt_HwDegpS_T_f32 = HwVelUnfilt_HwRadpS_T_f32 * D_180OVRPI_ULS_F32

OpMode_Cnt_T_enum = Rte_Pim_AvgFricLrnData()->OpMode_Cnt_enum


#### DefeatFricLearning_Cnt_T_lgc = Rte_IRead_AvgFricLrn_Per1_DefeatFricLearning_Cnt_lgc()Determine Mode


#### Prep Data


#### Learning Constraint


#### Calibration/Running Modes


#### Fault Injection


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_AvgFricLrn_Per1_FricOffset_HwNm_f32(FricOffsetOut_HwNm_T_f32)

Rte_IWrite_AvgFricLrn_Per1_EstFric_HwNm_f32(EstFric_HwNm_M_f32)

Rte_IWrite_AvgFricLrn_Per1_SatEstFric_HwNm_f32(SatEstFric_HwNm_M_f32)


#### Program Flow End

Rte_Call_AvgFricLrn_Per1_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


## Serial Communication Functions


### SCom: AvgFricLrn_SCom_GetEOLFric


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Read EOLFric Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_ GetOffsetOutputDefeat


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Read Offset Output Defeat Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_ GetSelect


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Read Select Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_InitLearnedTables


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Restore Tables to Baseline Values Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCOM: AvgFricLrn_SCom_ResetToZero


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Reset Tables to Zero Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_SetEOLFric


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Store EOL Friction Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_SetOffsetOutputDefeat


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Defeat Offset Output Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### SCom: AvgFricLrn_SCom_SetSelect


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Select Mode and Enable Service


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


## Transition Functions


### Trns: _Trns1


#### Design Rationale

This function implements the Power Off functions defined in the FDD model.


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Save Learned Friction to NvM


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

N/A


# Execution Requirements


## Execution Sequence of the Module

AvgFricLrn_Per1 executes at a rate of 10 ms.  AvgFricLrn_Trns1 executes on power down.


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
| HwAng_HwDeg_f32 | HwAng_HwDeg_f32 | EstFric_HwNm_f32 |
| HwPosAuthority_Uls_f32 | HwPosAuthority_Uls_f32 | FricOffset_HwNm_f32 |
| HwTrq_HwNm_f32 | HwTrq_HwNm_f32 | SatEstFric_HwNm_f32 |
| HwVel_HwRadpS_f32 | HwVel_HwRadpS_f32 |  |
| LatAcc_g_f32 | LatAcc_g_f32 |  |
| CRFMtrTrq_MtrNm_f32 | CRFMtrTrq_MtrNm_f32 |  |
| Temperature_DegC_f32 | Temperature_DegC_f32 |  |
| VehicleSpeedValid_Cnt_lgc | VehicleSpeedValid_Cnt_lgc |  |
| VehSpd_Kph_f32 | VehSpd_Kph_f32 |  |
| DefeatFricLearning_Cnt_lgc | DefeatFricLearning_Cnt_lgc |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| FiltAvgFric_HwNm_M_f32[4] | Single Precision Float | -10 | 10 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| SatAvgFric_HwNm_M_f32[4] | Single Precision Float | -10 | 10 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| VehBaselineFric_HwNm_M_f32[4] | Single Precision Float | -10 | 10 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| HwAngBuf_HwDeg_M_f32[12] | Single Precision Float | -1440.11 | 1440.11 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| HwVelBuf_HwDegpS_M_f32[12] | Single Precision Float | -1833.465 | 1833.465 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| ColTrqBuf_HwNm_M_f32[6] | Single Precision Float | -20 | 20 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| LearnConstTimer_mS_M_u32 | 1 | FULL | FULL | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| HwVelKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| LatAccKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| HwPosAuthorityKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| VehSpdKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| TemperatureKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| HwAngKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| ColTrqKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| FiltAvgKSV_M_str[4] | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |
| RawAvgFric_HwNm__f32[4] | Single Precision Float | -10 | 10 | AVGFRICLRN_START_SEC_VAR_CLEARED_32 |
| AvgFricChgKSV_M_str | LPF32KSV_Str |  |  | AVGFRICLRN_START_SEC_VAR_SAVED_ZONEH_UNSPECIFIED |
| Rte_Pim_AvgFricLrnData.VehLearnedFric_HwNm_M_f32[4] | Single Precision Float | -10 | 10 |  |
| Rte_Pim_AvgFricLrnData.Theta_HwNm_M_f32[8][4] | Single Precision Float | -10 | 10 |  |
| Rte_Pim_AvgFricLrnData.RangeCounter_Cnt_M_u16[8][3] | 1 | 0 | 65534 |  |
| Rte_Pim_AvgFricLrnData.OpMode_Cnt_M_enum | FricLrnModeType |  |  |  |
| Rte_Pim_AvgFricLrnData.FricOffset_HwNm_f32 | Single Precision Float | -10 | 10 |  |
| Rte_Pim_AvgFricLrnData.EnableFricLearning_Cnt_lgc | Boolean | FALSE | TRUE |  |
| Rte_Pim_AvgFricLrnData.EnableFricOffsetOutput_Cnt_lgc | Boolean | FALSE | TRUE |  |
| DefeatFricOffsetOutput_Cnt_M_lgc | Boolean | FALSE | TRUE |  |
| Rte_Pim_AvgFricLrnData.EOLFric_HwNm_f32 | Float | -10 | 10 |  |
| RunOnce_Cnt_M_lgc | Boolean | FALSE | TRUE | AP_AVGFRICLRN_VAR |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| FricLrnModeType | FRICLRN_CALIBRATION = 0 FRICLRN_NORMAL = 1 FRICLRN_CLEAR = 2 FRICLRN_IDLE = 3 FRICLRN_BASELINE = 4 | uint8 | 0 | 4 |


**Table 4**

| Constant Name |
| --- |
| t_FrHystHwAPts_HwDeg_f32[] |
| t2_VehSpd_Kph_f32[][] |
| t_MskVehSpd_Cnt_lgc[] |
| t_FricChgWeight_Uls_f32[] |
| t_InvRatioX_HwDeg_u11p5[] |
| t_InvRatioY_HwNmpMtrNm_u6p10[] |
| k_LearningGain_Uls_f32 |
| k_LearningThreshold_Cnt_u32 |
| k_RangeCounterLimit_Cnt_u16 |
| k_AvgFricLPFKn_Hz_f32 |
| k_HwPosAuthMin_Uls_f32 |
| k_HwVelConstLimit_HwDegpS_f32 |
| k_HwVelMax_HwDegpS_f32 |
| k_HwVelMin_HwDegpS_f32 |
| k_LatAccMax_MpSecSqrd_f32 |
| k_LatAccMin_MpSecSqrd_f32 |
| k_SatFricChgLim_HwNm_f32 |
| k_FricOffsetLPFKn_Hz_f32 |
| k_TempMin_DegC_f32 |
| k_TempMax_DegC_f32 |
| k_DataPrepLPFKn_Hz_f32 |
| k_IgnCycleFricChgLim_HwNm_f32 |
| k_FricOffsetLimitLow_HwNm_f32 |
| k_FricOffsetLimitHigh_HwNm_f32 |
| t2_BaselineTheta_HwNm_f32[][] |
| t2_BaselineRangeCounter_Cnt_u16[][] |
| t_BaselineFric_HwNm_f32[] |
| k_BaselineEOLFric_HwNm_f32 |
| k_EOLFricDiffScalingFactor_Uls_f32 |
| k_EOLFricDiffLimitLow_HwNm_f32 |
| k_EOLFricDiffLimitHigh_HwNm_f32 |
|  |
|  |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_10MS_SEC_F32 | Single Precision Float | S | 0.01 |
| D_LRNCNSTRTIME_MS_U32 | 1 | mS | 96 |
| D_VEHSPDPTNUMX2_CNT_U16 | 1 | Counts | D_VEHSPDPTNUM_CNT_U16*2 |
| D_VEHSPDPTNUM_CNT_U16 | 1 | Counts | TableSize_m(t2_VehSpd_Kph_f32) |
| D_HWPTNUM_CNT_U16 | 1 | Counts | TableSize_m(t_FrHystHwAPts_HwDeg_f32) |
| D_HWPTNUMSUB1_CNT_U16 | 1 | Counts | D_HWPTNUM_CNT_U16 - D_ONE_CNT_U16 |
| D_BUFSIZE_CNT_U16 | 1 | Counts | 12 |
| D_PHASESHIFTCNT_CNT_U16 | 1 | Counts | 6 |
| D_TWO_CNT_U16 | 1 | Counts | 2 |
| D_TEN_CNT_U16 | 1 | Counts | 10 |
| D_QUARTER_CNT_f32 | Single Precision Float | Counts | 0.25 |
| D_VEHSPDLOIDX_CNT_U16 | 1 | Counts | 0 |
| D_VEHSPDHIIDX_CNT_U16 | 1 | Counts | 1 |
| D_ONEG_MPSECSQRD_F32 | Single Precision Float | MpSecSqrd | 9.81 |


**Table 6**

| Constant Name |
| --- |
| D_ONE_CNT_U16 |
| D_ZERO_CNT_U16 |
| D_ONE_ULS_F32 |
| D_ZERO_CNT_U32 |
| D_180OVRPI_ULS_F32 |
| D_FALSE_CNT_LGC |
| D_TRUE_CNT_LGC |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | LoadBuffer | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Input_Uls_T_f32 | float32 | FULL | FULL |  |
|  | Buffer_Uls_T_f32 | float32 * | FULL | FULL |  |
|  | BufferSize_Cnt_T_u16 | uint16 | FULL | FULL |  |
| Return Value | N/A |  |  |  |  |


**Table 9**

| Function Name | HwAngConstraint | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | HwAng_HwDeg_T_f32 | float32 | -1440.11 | 1440.11 |  |
|  | HwAngOK_Cnt_T_lgc | boolean * | FULL | FULL |  |
|  | SelHwAng_HwDeg_T_f32 | float32 * | -1440.11 | 1440.11 |  |
| Return Value | N/A |  |  |  |  |


**Table 10**

| Function Name | HwVelConstraint | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | HwVel_HwDegpS_T_f32 | float32 | -1833 | 1833 |  |
|  | HwVelOK_Cnt_T_lgc | boolean * | FULL | FULL |  |
|  | Direction_Cnt_T_u16 | uint16 * | 0 | 1 |  |
| Return Value | N/A |  |  |  |  |


**Table 11**

| Function Name | VehSpdConstraint | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | VehSpd_Kph_T_f32 | float32 | 0 | 511 |  |
|  | VehSpdOK_Cnt_T_lgc | boolean * | FULL | FULL |  |
|  | VehSpdIndex_Cnt_T_u16 | uint16 * | 0 | 3 |  |
| Return Value | N/A |  |  |  |  |


**Table 12**

| Function Name | FricLearning | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | HwAng_HwDeg_T_f32 | float32 | -1440.11 | 1440.11 |  |
|  | ColTrq_HwNm_T_f32 | float32 | -20 | 20 |  |
|  | VehSpdIndex_Cnt_T_u16 | uint16 | 0 | 3 |  |
|  | Direction_Cnt_T_u16 | uint16 | 0 | 1 |  |
| Return Value | N/A |  |  |  |  |


**Table 13**

| Function Name | BaselineMode | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | N/A |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 14**

| Function Name | ClearMode | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | N/A |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 15**

| Data | Value |
| --- | --- |
| Rte_InitValue_EstFric_HwNm_f32 | 0 |
| Rte_InitValue_FricOffset_HwNm_f32 | 0 |
| Rte_InitValue_HwAng_HwDeg_f32 | 0 |
| Rte_InitValue_HwPosAuthority_Uls_f32 | 0 |
| Rte_InitValue_HwTrq_HwNm_f32 | 0 |
| Rte_InitValue_HwVel_HwRadpS_f32 | 0 |
| Rte_InitValue_LatAcc_g_f32 | 0 |
| Rte_InitValue_CRFMtrTrq_MtrNm_f32 | 0 |
| Rte_InitValue_SatEstFric_HwNm_f32 | 0 |
| Rte_InitValue_Temperature_DegC_f32 | 0 |
| Rte_InitValue_VehicleSpeedValid_Cnt_lgc | FALSE |
| Rte_InitValue_VehSpd_Kph_f32 | 0 |
| Rte_InitValue_DefeatFrictionLearning_cnt_lgc | FALSE |


**Table 16**

| Function Name | AvgFricLrn_SCom_GetEOLFric | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | *EOLFric_HwNm_f32 | uint8* | 0 | 127 | N/A |
| Return Value | N/A |  |  |  |  |


**Table 17**

| Function Name | AvgFricLrn_SCom_ GetOffsetOutputDefeat | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | * DefeatOffsetOutput_Cnt_lgc | boolean* | FALSE | TRUE | 0 |
| Return Value | N/A |  |  |  |  |


**Table 18**

| Function Name | AvgFricLrn_SCom_ GetSelect | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | * EnableFricLearning_Cnt_lgc | boolean* | FALSE | TRUE | 0 |
|  | *EnableOffsetOutput_Cnt_lgc | boolean* | FALSE | TRUE | 0 |
|  | *OpMode_Uls_u08 | uint8* | 0 | 4 | 0 |
| Return Value | N/A |  |  |  |  |


**Table 19**

| Function Name | AvgFricLrn_SCom_InitLearnedTables | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | N/A |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 20**

| Function Name | AvgFricLrn_SCom_ResetToZero | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | N/A |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 21**

| Function Name | AvgFricLrn_SCom_SetEOLFric | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | EOLFric_HwNm_u08 | uint8 | 0 | 127 |  |
| Return Value | N/A |  |  |  |  |


**Table 22**

| Function Name | AvgFricLrn_SCom_SetOffsetOutputDefeat | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | DefeatOffsetOutput_Cnt_lgc | Boolean | FALSE | TRUE |  |
| Return Value | N/A |  |  |  |  |


**Table 23**

| Function Name | AvgFricLrn_SCom_SetSelect | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | EnableFricLearning_Cnt_lgc | Boolean | FALSE | TRUE |  |
|  | EnableOffsetOutput_Cnt_lgc | Boolean | FALSE | TRUE |  |
|  | OpMode_Uls_u08 | Uint8 | 0 | 4 |  |
| Return Value | N/A |  |  |  |  |


**Table 24**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| AvgFricLrn_Init1 | On Event | On Init |
| AvgFricLrn_Per1 | 10 ms | OPERATE |
| AvgFricLrn_Trns1 | On Event | On Entering OFF |


**Table 25**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |
