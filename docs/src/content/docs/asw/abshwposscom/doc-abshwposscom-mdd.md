---
title: "Absolute Hardware Position Serial Communication (AbsHwPosScom)"
description: "Converted from AbsHwPosSCom_MDD.docx"
---

> **Source:** `AbsHwPosScom/doc/AbsHwPosSCom_MDD.docx` (1,258,254 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module -- AbsHwPosScom

This module determines the handwheel position representing the angle of the output shaft without using a  physical column position sensor.

The function uses the Motor Position to provide an estimate of the handwheel position. In addition this function also uses the absolute hw position transmitted on the serial communication interface to provide and estimate of the HwPos. value.


# High-Level Description

(Description must be within 8-10 lines.)


# Figures


## Diagram – Function Data Sharing


### Diagram – Function (Name)


# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)


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

(This is for lookup tables (arrays) with fixed values, same name as other tables)


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

FPM_FloatToFixed_m

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m

Limit_m

FPM_FixedToFloat_m

Min_m

Max_m

LPF_SvInit_s16InFixKTrunc_m


## Data Hiding Functions

Rte_Call_NxtrDiagMgr_SetNTCStatus


## Global Functions/Macros Defined by this Module


### Global Function #1


#### Description

(Place flowchart/design for local function)


## Local Functions/Macros Used by this MDD only


### Local Function #1


#### Description

(Place flowchart/design for local function)


### Local Function #2


#### Description

(Place flowchart/design for local function)


### Local Function #3


#### Description

(Place flowchart/design for local function)


### Local Function #4


#### Description

(Place flowchart/design for local function)


### Local Function #5


#### Description

(Place flowchart/design for local function)


### Local Function #6


#### Description


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions

(Note: For multiple init functions, insert new headers at the “Header 2” level – subset of “5.1 Initialization Functions” and follow the same sub-section design shown below)


### Init: AbsHwPosScom_Init1


### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)


#### Module Outputs

(Initialize all module outputs in this section)


## Periodic Functions


### Per: AbsHwPosScom_Per1


#### Design Rationale


#### Program Flow Start


#### Rte_Call_AbsHwPosScom_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies


#### Processing


#### Store Local copy of outputs into Module Outputs


#### Program Flow End

Rte_Call_AbsHwPosScom_Per1_CP1_CheckpointReached()


### Per: _Per2


#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)


#### Program Flow Start


#### Rte_Call_AbsHwPosScom_Per2_CP0_CheckpointReached()Store Module Inputs to Local copies


#### Program Flow End

Rte_Call_AbsHwPosScom_Per2_CP1_CheckpointReached()


### Per: _Per3


#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)


#### Program Flow Start


#### Rte_Call_AbsHwPosScom_Per3_CP0_CheckpointReached()Store Module Inputs to Local copies


#### Program Flow End

Rte_Call_AbsHwPosScom_Per3_CP1_CheckpointReached()


## Fault Recovery Functions


## Shutdown Functions


## Interrupt Functions


## Serial Communication Functions


### AbsHwPosScom_Scom_HwPosSrvSetToZero


#### Design Rationale


#### Program Flow Start


#### Store Module Inputs to Local copies

N/A


#### Processing

HwPosSrvSetToZero_Cnt_M_lgc = Par


#### Store Local Copy Of Outputs into Module Outputs

N/A


#### Program Flow End

N/A


### AbsHwPosScom_Scom_HwPosSrvRead


#### Design Rationale


#### Program Flow Start


#### Store Module Inputs to Local copies

N/A


#### Processing

*Par = HwPosSrvSetToZero_Cnt_M_lgc


#### Store Local Copy Of Outputs into Module Outputs

N/A


#### Program Flow End

N/A


# Execution Requirements


## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design


# Note1: Deviation from FDD: Cal k_MtrToHw_Res_Conversion is not used for Scaled_MtrPos calculations in this software. Refer FDD- 05D section 5.1.2.2.(This cal was for a fixedtype implementation).Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| CRFCumMtrPos_Deg_f32 | CRFCumMtrPos_Deg_f32 | HwPosAuthority_Uls_f32 |
| CRFMtrTrqCmd_MtrNm_f32 | CRFMtrTrqCmd_MtrNm_f32 | HwPos_HwDeg_f32 |
| CRFMtrVel_MtrRadpS_f32 | CRFMtrVel_MtrRadpS_f32 |  |
| DiagStsHwPosDis_Cnt_lgc | DiagStsHwPosDis_Cnt_lgc |  |
| HwTrq_HwNm_f32 | HwTrq_HwNm_f32 |  |
| SComInpHwAValid_Cnt_lgc | SComInpHwAValid_Cnt_lgc |  |
| SComInpHwA_HwDeg_f32 | SComInpHwA_HwDeg_f32 |  |
| VehicleSpeedValid_Cnt_lgc | VehicleSpeedValid_Cnt_lgc |  |
| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |
| KinIntDiagSrlComSvcDft_Cnt_lgc | KinIntDiagSrlComSvcDft_Cnt_lgc |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| HwPFilter1En_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| HwPFilter2En_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| VehDynTrgtAngle_HwDeg_M_f32 | Single precision floating point | -1575164.8 | 1575164.8 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| VehDynTrgtAuth_Uls_M_f32 | Single precision floating point | 0 | 1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPHighSpdAC_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| PinTrqFiltSV_HwNm_M_Str | N/A | N/A | N/A | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED |
| PinTrqFiltSV_HwNm_M_Str .K_Uls_f32 | Single precision floating point | 8.04215E-05 | 0.039414597 |  |
| PinTrqFiltSV_HwNm_M_Str.SV_Uls_f32 | Single precision floating point | -318 | 318 |  |
| HwPMtrVelT1Cal_MtrRadpS_M_f32 | Single precision floating point | 0 | 700 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPVSpdT1Cal_Kph_M_f32 | Single precision floating point | 0 | 255 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPPinTrqT1Cal_HwNm_M_f32 | Single precision floating point | 0 | 10 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPTimer1Max_ms_M_u16 | 1 | 0 | 60000 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_16 |
| HwPWindowCal_HwDeg_M_f32 | Single precision floating point | 0 | 100 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPFilter1Kn_Hz_M_f32 | Single precision floating point | 0.0002 | 0.1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPFilter2Kn_Hz_M_f32 | Single precision floating point | 0.0002 | 0.1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| AutoCntrTrgtAuth_Uls_M_f32 | Single precision floating point | 0 | 1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPTimer2Max_ms_M_u16 | 1 | 0 | 60000 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_16 |
| HwPAutoCenter_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| HwPFilter1Init_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| HwPFilter2Init_Cnt_M_lgc | BOOLEAN | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| HwPFilter1Prev_HwDeg_M_f32 | Single Precision Floating point | -787558.4 | 787606.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPFilter1Out_HwDeg_M_f32 | Single Precision Floating point | -787558.4 | 787606.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPFilter1SV_HwDeg_M_Str | N/A | N/A | N/A | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED |
| HwPFilter1SV_HwDeg_M_Str.K_Uls_f32 | Single Precision Floating point | 8.04215E-05 | 0.039414597 |  |
| HwPFilter1SV_HwDeg_M_Str.SV_Uls_f32 | Single Precision Floating point | -787558.4 | 787606.4 |  |
| HwPFilter2Out_HwDeg_M_f32 | Single Precision Floating point | -787558.4 | 787606.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPFilter2SV_HwDeg_M_Str | N/A | N/A | N/A | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED |
| HwPFilter2SV_HwDeg_M_Str .K_Uls_f32 | Single Precision Floating point | 8.04215E-05 | 0.039414597 |  |
| HwPFilter2SV_HwDeg_M_Str *SV_Uls_f32 | Single Precision Floating point | -787558.4 | 787606.4 |  |
| HwPTimer1_ms_M_u32 | 1 | FULL | FULL | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPTimer2_ms_M_u32 | 1 | FULL | FULL | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| HwPTimer4_ms_M_u32 | 1 | FULL | FULL | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
|  |  |  |  |  |
| ScaledMtrPos_HwDeg_M_f32 | Float32 | -787558.4 | 787606.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| MtrComplErr_HwDeg_M_f32 | Float32 | -1126.4 | 1126.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| TempHwPos_HwDeg_M_f32 | Float32 | -1575164.8 | 1575164.8 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| RelHwPos_HwDeg_M_f32 | Float32 | -787558.4 | 787606.4 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| FiltPinionTrq_HwNm_M_f32 | single precision floating point | -318 | 318 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| FinHwPosLPFOp_HwDeg_M_f32 | single precision floating point | -1620 | 1620 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| FinHwAuth_Uls_M_f32 | single precision floating point | 0 | 1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| FinHwPosFiltSV_HwDeg_M_Str | N/A | N/A | N/A | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_UNPECIFIED |
| FinHwPosFiltSV_HwDeg_M_Str.K_Uls_f32 | single precision floating point | 0 | 0.999984637 |  |
| FinHwPosFiltSV_HwDeg_M_Str.SV_Uls_f32 | single precision floating point | -1575164.8 | 1575164.8 |  |
| RelToSComOffset_HwDeg_M_f32 | Float32 | -789654 | 789606.3 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| StabilitySyncTimer_mS_M_u32 | UINT32 | FULL | FULL | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| NewScomInpHwA_HwDeg_M_f32 | Single precison floating point | -1578812.8 | 1578812.738 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| ScomHwPosAuth_Uls_M_f32 | Single precison floating point | 0 | 1 | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_32 |
| VdynToScomErrorThy_HwDeg_M_f32 | Single precison floating point | -1600 | 1600 | ABSHWPOSSCOM_START_SEC_VAR_SAVED_ZONEH_32 |
| HwPosSrvSetToZero_Cnt_M_lgc | n/a | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |
| RelToScomOfstFound_Cnt_M_lgc | n/a | FALSE | TRUE | ABSHWPOSSCOM_START_SEC_VAR_CLEARED_BOOLEAN |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| (Name given for the user defined typdef of type struct/union) (Variable name qualified similar to all other variables) | (Variable name qualified similar to all other variables) | as other variables |  |  |
|  | (Variable name qualified similar to all other variables) |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_AutoCtrMtrVelT1L_MtrRadpS_f32 |
| k_AutoCtrVehSpdT1L_Kph_f32 k_AutoCtrPinTrqT1L_HwNm_f32 k_HwPTimer1MaxL_ms_u16 k_AutoCtrWindowL_HwDeg_f32 k_AutoCtrFiltOneCoeffkL_Hz_f32 k_AutoCtrFiltTwoCoeffkL_Hz_f32 k_VDAuthL_Uls_f32 k_AutoCtrTimer2LSpd_ms_u16 k_InvGearRatio_Uls_f32 k_AutoCtrPinTrqLPFCoeffK_Hz_f32 k_MtrVelTmr4H_MtrRadpS_f32 k_VehSpdTmr4H_kph_f32 k_PinTrqTmr4H_HwNm_f32 k_Tmr4CntrWindowH_HwDeg_f32 k_AutoCtrTimer4H_ms_u16 k_HwPMtrVelT1H_MtrRadpS_f32 k_HwPVehSpdT1H_Kph_f32 k_HwPPinionTrqT1H_HwNm_f32 k_HwPTimer1MaxH_ms_u16 k_HwPWindowCalH_HwDeg_f32 k_HwPFilter1KnH_Hz_f32 k_HwPFilter2KnH_Hz_f32 k_HiSpdAcAuth_Uls_f32 k_HwPTmr2MaxHiSpd_ms_u16 t_MtrPosComplTblX_MtrNm_u8p8[6] t_MtrPosComplTblY_HwDegpMtrNm_u6p10[6] k_RbstPosLPFKn_Hz_f32 k_KinmIntDiagMaxRackLmt_HwDeg_f32 k_HwPosOpLPFError_HwDeg_f32 k_HwPosAuthorityStep_Uls_f32 |
| k_ScomHwPosAuth_Uls_f32 |
| k_HwPosVehStabilityTime_mS_u16 |
| k_HwPosVehStabilityTrqCmd_MtrNm_f32 |
| k_HwPosVehStabilityHwTrq_HwNm_f32 |
| k_HwPosVehStabilityMtrVel_MtrRadpS_f32 |
| k_VdynToScomMaxErr_HwDeg_f32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_ABSPOSLOLMT_HWDEG_F32 | Single precision floating point | HWDEG | -1620 |
| D_ABSPOSHILMT_HWDEG_F32 | Single precision floating point | HWDEG | 1620 |
| D__SEC_F32 | Single precision floating point | SEC | 0. |


**Table 6**

| Constant Name |
| --- |
| D_2MS_SEC_F32 |
| D_ONE_ULS_F32 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | (Exact name used) | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | (if none, write None) |  |  |  |
|  | (Insert more rows for additional passed arguments) |  |  |  |
| Return Value | (if no value returned, write N/A) |  |  |  |


**Table 9**

| Function Name | HwPosSLFilter1 | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | MtrPos_HwDeg_T_f32 | float32 | -787558.4 | 787606.4 |
|  | FilterEn | boolean | FALSE | TRUE |
| Return Value | (if no value returned, write N/A) |  |  |  |


**Table 10**

| Function Name | HwPosSLFilter2 | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | MtrPos_HwDeg_T_f32 | float32 | -787558.4 | 787606.4 |
|  | FilterEn | boolean | FALSE | TRUE |
| Return Value | (if no value returned, write N/A) |  |  |  |


**Table 11**

| Function Name | Filter1Enable | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | CRFMtrVel_MtrRadpS_T_f32 | float32 | -1118 | 1118 |
|  | VehSpd_Kph_T_f32 | float32 | 0 | 512 |
|  | VSpdValid _Cnt_T_lgc | boolean | FALSE | TRUE |
|  | PinionTrq_HwNm_T_f32 | float32 | -318 | 318 |
| Return Value | HwPFilter1En_Cnt_T_lgc | boolean | FALSE | TRUE |


**Table 12**

| Function Name | Filter2Enable | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | MtrPos_HwDeg_T_f32 | float32 | -787558.4 | 787606.4 |
|  | HwPFilter1En_Cnt_T_lgc | boolean | FALSE | TRUE |
| Return Value | HwPFilter2En_Cnt_T_lgc | boolean | FALSE | TRUE |


**Table 13**

| Function Name | CalSwitchTimer | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | CRFMtrVel_MtrRadpS_T_f32 | float32 | -1118 | 1118 |
|  | VehSpd_Kph_T_f32 | float32 | 0 | 512 |
|  | VSpdValid _Cnt_T_lgc | boolean | FALSE | TRUE |
|  | PinionTrq_HwNm_T_f32 | float32 | -318 | 318 |
|  | HwPFilter1En_Cnt_T_lgc | boolean | FALSE | TRUE |
|  | HwPFilter2En_Cnt_T_lgc | boolean | FALSE | TRUE |
| Return Value | None |  |  |  |


**Table 14**

| Function Name | ScomHwPosAuth | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |
| Return Value | None |  |  |  |


**Table 15**

| Data | Value |
| --- | --- |
| CRFCumMtrPos_Deg_f32 | 0 |
| CRFMtrTrqCmd_MtrNm_f32 | 0 |
| CRFMtrVel_MtrRadpS_f32 | 0 |
| DiagStsHwPosDis_Cnt_lgc | FALSE |
| HwTrq_HwNm_f32 | 0 |
| SComInpHwAValid_Cnt_lgc | FALSE |
| SComInpHwA_HwDeg_f32 | 0 |
| VehicleSpeedValid_Cnt_lgc | FALSE |
| VehicleSpeed_Kph_f32 | 0 |
| KinIntDiagSrlComSvcDft_Cnt_lgc | FALSE |
| HwPosAuthority_Uls_f32 | 0 |
| HwPos_HwDeg_f32 | 0 |


**Table 16**

| Function Name | AbsHwPosScom_Scom_HwPosSrvSetToZero | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | Par | Boolean | False | True |
| Return Value | None |  |  |  |


**Table 17**

| Function Name | AbsHwPosScom_Scom_ HwPosSrvRead | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | Par | Ptr to Boolean | False | True |
| Return Value | None |  |  |  |


**Table 18**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| AbsHwPosScom_Init1 | Once at startup | ColdInit |
| AbsHwPosScom_Per1 | 2ms | All states except ColdInit |
| AbsHwPosScom_Per2 | ms | All states except Cold Init |
| AbsHwPosScom_Per3 | ms | All states except Cold Init |


**Table 19**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| AbsHwPosScom_Scom_HwPosSrvRead |  |
| AbsHwPosScom_Scom_HwPosSrvSetToZero |  |


**Table 20**

| Name of Sub Module | Software Segment |
| --- | --- |
| AbsHwPosScom_Init1 | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per1 | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per2 | RTE_AP_ABSHWPOSSCOM_APPL_CODE |
| AbsHwPosScom_Per3 | RTE_AP_ABSHWPOSSCOM_APPL_CODE |


**Table 21**

| Name of Sub Module | Software Segment |
| --- | --- |
| HwPosSLFilter1 | AP_ ABSHWPOSSCOM_CODE |
| HwPosSLFilter2 | AP_ ABSHWPOSSCOM_CODE |
| Filter1Enable | AP_ ABSHWPOSSCOM_CODE |
| Filter2Enable | AP_ ABSHWPOSSCOM_CODE |
| CalSwitchTimer | AP_ ABSHWPOSSCOM_CODE |


**Table 22**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial AutoSAR Release | 24-April-12 | NRAR |
| 2 | 2.0 | Text format changes | 25-April-12 | NRAR |
| 3 | 3.0 | HandWheelPosition range is changed from +/-1440.11 to +/-1620HwDeg | 26-April-12 | NRAR |
| 4 | 4.0 | Anom 3257 Fix | 4-May-12 | NRAR |
| 5 | 5.0 | FDD 5D updates as per Ver002 | 27-June-12 | NRAR |
| 6 | 6.0 | FDD 5D updates as per ver 003,Ver002 and Anom 3382 is ignored as now s/w is implemented in floating type. | 05-July-12 | NRAR |
| 6 | 6 | Version of thisMDD is still lshown as 6 to match up with Synergy version In per1, Typo fix for global inputs | 19-July-12 | NRAR |
| 7 | 7.0 | FDD 5D updates per Ver006 | 10-Aug-12 | BWL |
| 8 | 8.0 | Update per UTP review. | 5-Sept-12 | BWL |
| 9 | 9.0 | Added checkpoints and memmap software segment is updated for static variables | 26-Sep-12 | Selva |
|  |  |  |  |  |
