---
title: "Steering Damping Control (Damping)"
description: "Converted from Damping_MDD.docx"
---

> **Source:** `Damping/doc/Damping_MDD.docx` (575,850 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module --


# High-Level Description

Damping function computes the Total damping Torque. The total damping command is calculated from two terms, Active Damping Term and the HPS Damping Command.


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

FPM_FixedToFloat_m

FPM_FloatToFixed_m

1. Limit_m
1. Abs_f32_m
1. Abs_s16_m
1. Sign_f32_m
1. IntplVarXY_u16_u16Xu16Y_Cnt
1. IntplVarXY_u16_s16Xu16Y_Cnt
1. TableSize_m
1. LPF_KUpdate_f32_m
1. LPF_OpUpdate_f32_m

## Data Hiding Functions

<None>


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only


### MtrVelDepDampScale


#### Description


### HPSDampingFn


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

LPF_KUpdate_f32_m(k_QddHwTrqDampKn_Hz_f32, D_2MS_SEC_F32, &QDDHwTorqueLPFKSV_Cnt_M_str)

LPF_KUpdate_f32_m(k_QddMtrVelDampKn_Hz_f32, D_2MS_SEC_F32, &QDDMtrVelLPFKSV_Cnt_M_str)

LPF_KUpdate_f32_m(k_QddSfLFPKn_Hz_f32, D_2MS_SEC_F32, &QDDStFilt_Cnt_M_str)

LPF_KUpdate_f32_m(k_MtrVelDampLPFKn_Hz_f32, D_2MS_SEC_F32, &MtrVelLPFKSV_Cnt_M_str)


## Periodic Functions


### Per: _Per1


#### Design Rationale

None


#### Program Flow Start

Rte_Call_Damping_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

AssistMechTempEst_DegC_T_f32 = Rte_IRead_Damping_Per1_AssistMechTempEst_DegC_f32()

BaseAssistStCmp_MtrNm_T_f32 = Rte_IRead_Damping_Per1_AssistCm_MtrNm_f32()

DampingDDFactor_Uls_T_f32 = Rte_IRead_Damping_Per1_DampingDDFactor_Uls_f32()

DefeatDampingSvc_Cnt_T_lgc = Rte_Iread_Damping_Per1_DefeatDampingSvc_Cnt_lgc()

HwTorque_HwNm_T_f32 = Rte_Iread_Damping_Per1_HwTorque_HwNm_f32()

MotorVelCRF_MtrRadpS_T_f32 = Rte_Iread_Damping_Per1_MotorVelCRF_MtrRadpS_f32()

VehicleSpeed_Kph_T_f32 = Rte_Iread_Damping_Per1_VehicleSpeed_Kph_f32()


#### Calculate Damping Command


#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_Damping_Per1_DampingCmd_MtrNm_f32(DampingCmd_MtrNm_T_f32)


#### Program Flow End

Rte_Call_Damping_Per1_CP1_CheckpointReached()


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

INLINE functions in GlobalMacro.h are not unit tested


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| MotorVelCRF_MtrRadpS_f32 | MotorVelCRF_MtrRadpS_f32 | DampingCmd_MtrNm_f32 |
| HwTorque_HwNm_f32 | HwTorque_HwNm_f32 |  |
| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |
| DampingDDFactor_Uls_f32 | DampingDDFactor_Uls_f32 |  |
| AssistMechTempEst_DegC_f32 | AssistMechTempEst_DegC_f32 |  |
| AssistCmp_MtrNm_f32 | AssistCmp_MtrNm_f32 |  |
| DefeatDampingSvc_Cnt_lgc | DefeatDampingSvc_Cnt_lgc |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| QDDHwTorqueLPFKSV_Cnt_M_str | LPF32KSV_Str |  |  | DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED |
| QDDMtrVelLPFKSV_Cnt_M_str | LPF32KSV_Str |  |  | DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED |
| QDDStFilt_Cnt_M_str | LPF32KSV_Str |  |  | DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED |
| MtrVelLPFKSV_Cnt_M_str | LPF32KSV_Str |  |  | DAMPING_START_SEC_VAR_CLEARED_UNSPECIFIED |
| QDDHwTrqBkLash_HwNm_M_f32 | Single Precision Float |  |  | DAMPING_START_SEC_VAR_CLEARED_32 |
| QDDMtrVelBckLash_MtrRadpS_M_f32 | Single Precision Float |  |  | DAMPING_START_SEC_VAR_CLEARED_32 |
| QDDStFilt_Uls_D_f32 | Single Precision Float |  |  | DAMPING_START_SEC_VAR_CLEARED_32 |
| DampTrqScale_Uls_D_u1p15 | 2^-15 | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _16 |
| DampTempScale_Uls_D_u4p12 | 2^-12 | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _16 |
| DampMtrVelDmp_MtrNm_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |
| DampHPSDmp_MtrNm_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |
| DampHPSc1_Uls_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |
| DampHPSc2_Uls_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |
| DampHPSc3_Uls_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |
| DampHPSc4_Uls_D_f32 | Single Precision Float | FULL | FULL | DAMPING_STOP_SEC_VAR_CLEARED _32 |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_MtrVelDampLPFKn_Hz_f32 |
| t_HwTrqDmpTblX_HwNm_u8p8 [] |
| t_VSpdDmpTblBS_Kph_u9p7 [] |
| t_HwTrqDmpTblY_Uls_u1p15[ ] |
| t2_MtrVelDmpTblX_MtrRadpS_u12p4[ ] [ ] |
| t2_MtrVelDmpTblY_MtrNm_u5p11[ ] [ ] |
| t_TempScaleX_DegC_s8p7[ ] |
| t_TempScaleY_Uls_u4p12[ ] |
| t_HPSscaleC1Y_Uls_u4p12[ ] |
| t_HPSscaleC2Y_Uls_u4p12[ ] |
| t_HPSscaleC3Y_Uls_u4p12[ ] |
| t_HPSscaleC4Y_Uls_u4p12[ ] |
| t_HPSAsstLimY_MtrNm_u4p12[ ] |
| k_HPSOutLimit_MtrNm_f32 |
| k_Quad13DmpMult_Uls_f32 |
| k_Quad24DmpMult_Uls_f32 |
| k_QddHwTrqDampKn_Hz_f32 |
| k_QddMtrVelDampKn_Hz_f32 |
| k_QDDHwTrqBckLash_HwNm_f32 |
| k_QDDMtrVelBckLash_MtrRadpS_f32 |
| k_QddSfLFPKn_Hz_f32 |
| k_HPSbaseC1_MtrNmpMtrRadpS_f32 |
| k_HPSbaseC2_MtrNmpMtrRadpS_f32 |
| k_HPSbaseC3_MtrNmpMtrRadpS_f32 |
| k_HPSbaseC4_MtrNmpMtrRadpS_f32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_DAMPINGCMDMIN_MTRNM_F32 | Single Precision Floating Point | MtrNm | -8.8 |
| D_DAMPINGCMDMAX_MTRNM_F32 | Single Precision Floating Point | MtrNm | 8.8 |


**Table 6**

| Constant Name |
| --- |
| BC_DAMPING_FAULTINJECTIONPOINT |
| STD_ON |
| FLTINJ_DAMPING |
| D_2MS_SEC_F32 |
| D_ZERO_ULS_F32 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | MtrVelDepDampScale | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | MotorVelCRF_MtrRadpS_T_f32 | Float32 | - |  |  |
|  | VehicleSpeed_Kph_T_f32 | Float32 | 0 | 512 |  |
|  | HwTorque_HwNm_T_f32 | Float32 | -10 | 10 |  |
|  | TempScale_Uls_T_f32 | Float32 | 0 | 10 |  |
| Return Value | ActiveDamping_MtrNm_T_f32 | Float32 | -8.8 | 8.8 | 4.89E-4 |


**Table 9**

| Function Name | HPSDampingFn | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | MotorVelCRF_MtrRadpS_T_f32 | Float32 | - |  |  |
|  | TempScale_Uls_T_f32 | Float32 | 0 | 10 |  |
|  | VehicleSpeed_Kph_T_f32 | Float32 | 0 | 512 |  |
|  | BaseAssistStCmp_MtrNm_T_f32 | Float32 | -8.8 | 8.8 |  |
| Return Value | DampingForce_MtrNm_T_f32 | Float32 | -8.8 | 8.8 | 4.89 e-4 |


**Table 10**

| Data | Value |
| --- | --- |
| MotorVelCRF_MtrRadpS_f32 | 0 |
| HwTorque_HwNm_f32 | 0 |
| VehicleSpeed_Kph_f32 | 0 |
| DampingCmd_MtrNm_f32 | 0 |
| AssistMechTempEst_DegC_f32 | 0 |
| BaseAssistStCmp_MtrNm_f32 | 0 |
| DampingDDFactor_Uls_f32 | 1 |
| DefeatDampingSvc_Cnt_lgc | FALSE |


**Table 11**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| Damping_Init1 | On Event | On Init |
| Damping_Per1 | 2ms | ALL STATES |


**Table 12**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
| Damping_Init1 | RTE_START_SEC_AP_DAMPING_APPL_CODE |
| Damping_Per1 | RTE_START_SEC_AP_DAMPING_APPL_CODE |


**Table 14**

| Name of Sub Module | Software Segment |
| --- | --- |
| MtrVelDepDampScale |  |
| HPSDampingFn |  |


**Table 15**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial MDD | 20May11 | NRAR |
| 2 | 2 | Included scaling from driving dynamics. | 02-Jun-11 | YY |
| 3 | 3 | Added Rolling Assist Damping and Filter Kp Blending Interface | 14-Jul-11 | LWW |
| 4 | 4 | Made changes to match FDD SF#03 001a | 18-Nov-11 | VK |
| 5 | 5 | Changes done as per FaultInjectionTechnique | 1-May-12 | NRAR |
| 6 | 6 | Software segment for internal variable used in the module addd | 19-Sep-12 | SSK |
| 7 | 7 | Implemented SF-03 v006 | 25-Oct-12 | OT |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
