---
title: "Motor Position 2"
description: "Converted from Motor_Position_2_MDD.docx"
---

> **Source:** `MtrPos/doc/Motor_Position_2_MDD.docx` (1,238,466 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module implements the learning and diagnostic portions of MtrPos, as well as part of the motor position determination sub function.


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

Abs_f32_m

sinf

cosf

DiagPStep_m

DiagNStep_m

DiagFailed_m

LPF_SvUpdate_s16InFixKTrunc_m

Limit_m


## Data Hiding Functions

Rte_Pim_MtrPosSnsr_EOLData

Rte_Call_NxtrDiagMgr_GetNTCFailed


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only


### Offset Initialization


#### Description


### Run Time Filter


#### Description


### Calculate Offset from Min/Max


#### Description


### Calculate Sine AmpRec


#### Description


### Calculate Cosine AmpRec


#### Description


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: _Init1


#### Design Rationale

None


#### Calculate Ratios


#### Check Correction Terms


#### Calculate Limits and Initialize RT Offsets


#### Initialize AmpRec


## Periodic Functions


### Per: _Per1


#### Design Rationale

This function should be run before MtrPos3_Per1, as the comparisons (in both the main and diverse paths) on the generated signals assume that this order will be followed.


#### Program Flow Start

Rte_Call_MtrPos2_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

CorrectedMtrPos_Rev_T_f32 =

Cos1Scaled_Volt_T_f32 =

DiagCorrectedMtrPos_Rev_T_f32 =

MechMtrPos_Rev_T_f32 =

MotorVelMRF_MtrRadpS_T_f32 = Rte_IRead_MtrPos2_Per1_MotorVelMRF_MtrRadpS_f32()

Sin1Scaled_Volt_T_f32 =

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriMSB_SinCosCorr, &MtrPosFault1_Cnt_T_lgc)

Rte_Call_NxtrDiagMgr_GetNTCFailed(NTC_Num_PriVsSec_SinCosCorr, &MtrPosFault2_Cnt_T_lgc)

Sin1Offset_Volts_T_f32 = FPM_FixedToFloat_m(->Sin1Offset_Volts_u3p13, u3p13_T)

Cos1Offset_Volts_T_f32 = FPM_FixedToFloat_m(->Cos1Offset_Volts_u3p13, u3p13_T)

Sin1AmpRec_Uls_T_f32 = FPM_FixedToFloat_m(->Sin1AmpRec_Uls_u3p13, u3p13_T)


#### Motor Position Measurement


#### Run Time Learning


#### Back EMF Diagnostic


#### Correlation Diagnostic


#### Validity Diagnostic


#### Store Local copy of outputs into Module Outputs

PrevCorrectedMtrPos_Rev_M_f32 = CorrectedMtrPos_Rev_T_f32

= CorrelationDelta_Rev_T_f32

MtrPosValidErr_VoltsSqrd_D_f32 = ValidErr_VoltsSqrd_T_f32


#### Program Flow End

Rte_Call_MtrPos2_Per1_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


## Serial Communication Functions


### SCom: _SCom_ReadEOLMtrCals


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Processing of function


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

N/A


### SCom: _SCom_SetEOLMtrCals


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Processing of function


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_MtrPos2_SCom_SetEOLMtrCals_EOLBEMF_Rev_f32(FPM_FixedToFloat_m(Rte_Pim_MtrPosSnsr_EOLData()->BEMFCal_Rev_u0p16, u0p16_T))


#### Program Flow End

N/A


# Execution Requirements


## Execution Sequence of the Module

See section 6.3.1.1 for details on task ordering.


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
| MotorVelMRF_MtrRadpS_f32 | MotorVelMRF_MtrRadpS_f32 |  |
|  |  |  |
|  |  |  |
|  |  | Sin |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| ValidityFltAcc_Cnt_M_u16 | 1 | 0 | 65535 | MTRPOS2_START_SEC_VAR_CLEARED_16 |
| CorrFltAcc_Cnt_M_u16 | 1 | 0 | 65535 | MTRPOS2_START_SEC_VAR_CLEARED_16 |
| PrevCorrectedMtrPos_Rev_M_f32 | Single Precision Float | 0 | 0.99998 | MTRPOS2_START_SEC_VAR_CLEARED_32 |
|  |  |  |  |  |
|  |  |  |  |  |
| PrevSin1RTOffset_Volts_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| PrevCos1RTOffset_Volts_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Sin1OffsetCorr_Volts_M_f32 | Single Precision Float |  | 0. | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Cos1OffsetCorr_Volts_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Sin1GainCorr_Uls_M_f32 | Single Precision Float | 0. | 1.2 | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Cos1GainCorr_Uls_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| CosSin1NomRatio_Uls_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| SinCos1NomRatio_Uls_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| RTToNomHighLmt_Uls_M_f32 | Single Precision Float | 1 | 1.02 | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| RTToNomLowLmt_Uls_M_f32 | Single Precision Float | 0.98 | 1 | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Cos1RTAmpRec_Uls_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Cos1RTOffset_Volt_M_f32 | Single Precision Float | 1. | .8 | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Sin1RTAmpRec_Uls_M_f32 | Single Precision Float |  |  | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Sin1RTOffset_Volt_M_f32 | Single Precision Float |  | .8 | MTRPOS2_START_SEC_VAR_NOINIT_32 |
| Cos1MaxSV_Volts_M_s2p29 | 2-29 | 0.25 |  | MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32 |
| Cos1MinSV_Volts_M_s2p29 | 2-29 | - | -5 | MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32 |
| Sin1MaxSV_Volts_M_s2p29 | 2-29 | 0.25 | .5 | MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32 |
| Sin1MinSV_Volts_M_s2p29 | 2-29 |  |  | MTRPOS2_START_SEC_VAR_SAVED_ZONEH_32 |
|  |  |  |  |  |
| MtrPosValidErr_VoltsSqrd_D_f32 | Single Precision Float | 0 | 4.5 | MTRPOS2_START_SEC_VAR_CLEARED_32 |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| MtrPosCal_DataType | BEMFCal_Rev_u0p16 R_BEMFCal_Rev_u0p16 Sin1Offset_Volts_u3p13 Sin1AmpRec_Uls_u3p13 Cos1Offset_Volts_u3p13 Cos1AmpRec_Uls_u3p13 SinDelta1_Uls_s2p13 CosDelta1Rec_Uls_u3p13 Sin1OffCorr_Volts_s2p13 Sin1GainCorr_Uls_u1p15 Cos1OffCorr_Volts_s2p13 Cos1GainCorr_Uls_u1p15 SinHarTbl_Cnt_sm6p13[144] CosHarTbl_Cnt_sm6p13[144] |  | 0 0 .2 0. .2 0. -0.0174524 0.99985 -0.5 0.8 -0.5 0.8 -0.0155 -0.0155 | 1 1 .8 .8 0.0174524 1 0.5 1.2 0.5 1.2 0.0155 0.0155 |


**Table 4**

| Constant Name |
| --- |
| k_RTOffVelThr_MtrRadpS_f32 |
| k_RTFiltEnThresh_Uls_f32 |
| k_RTOffFiltKn_Cnt_u16 |
| k_RTOffsetLmt_Volts_f32 |
| k_AmpRecVarLmt_Uls_f32 |
| k_RTToNomRatioVar_Uls_f32 |
| k_CorrelationError_Rev_f32 |
| k_MtrPosCorrDiag_Cnt_str |
| k_ValMinError_VoltsSqrd_f32 |
| k_ValMaxError_VoltsSqrd_f32 |
| k_MtrPosValDiag_Cnt_str |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_DEGPERREV_ULS_F32 | Single Precision Float | Unitless | 360 |
| D_OFFSETCORRTHRESH_VOLTS_F32 | Single Precision Float | Volts | 0.02 |
| D_AMPCORRTHRESH_ULS_F32 | Single Precision Float | Unitless | 0.02 |
| D_MAXAMPLITUDE_VOLTS_F32 | Single Precision Float | Volts | .5 |
| D_MINAMPLITUDE_VOLTS_F32 | Single Precision Float | Volts | 0.25 |
| D_HALF_ULS_F32 | Single Precision Float | Unitless | 0.5 |
| D_TWO_ULS_F32 | Single Precision Float | Unitless | 2 |
| D_WORDMASK_CNT_U16 | 1 | Counts | 0xFFFF |


**Table 6**

| Constant Name |
| --- |
| D_ZERO_ULS_F32 |
| D_ONE_ULS_F32 |
| D_2PI_ULS_F32 |
| D_ZERO_CNT_U16 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | OffsetInit | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | EOLAmpRec_Uls_T_f32 | float32 |  |  |  |
|  | EOLOffset_Volts_T_f32 | float32 | .2 | .8 |  |
|  | StateVarMaxPtr_Volts_T_s2p29 | sint32 * | 0.25 |  | 2-13 |
|  | StateVarMinPtr_Volts_T_s2p29 | sint32 * |  |  | 2-13 |
| Return Value | RTOffset_Volts_T_f32 | float32 |  |  | 2-13 |


**Table 9**

| Function Name | RunTimeFilter | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | SigEst_Uls_T_f32 | float32 | -1 | 1 |  |
|  | SigCorr_Volts_T_f32 | float32 | - |  |  |
|  | OffsetDelta_Volts_T_f32 | float32 | - | . |  |
|  | StateVarPtr_Volts_T_s2p29 | s2p29_T | - | .5 |  |
| Return Value | Output_Volts_T_f32 | float32 |  |  | 2-13 |


**Table 10**

| Function Name | CalcOffsetFromMinMax | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Min_Volts_T_f32 | float32 |  |  |  |
|  | Max_Volts_T_f32 | float32 | 0.25 | .5 |  |
|  | EOLOffset_Volts_T_f32 | float32 | .2 | .8 |  |
| Return Value | RTOffset_Volts_T_f32 | float32 |  | . | 2-13 |


**Table 11**

| Function Name | CalcSinAmpRec | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | TotSinAmp_Volts_T_f32 | float32 | 0.5 |  |  |
|  | EOLSinAmpRec_Uls_T_f32 | float32 | 0. | 5 |  |
| Return Value | SinRTAmpRec_Uls_T_f32 | float32 |  |  | 2-13 |


**Table 12**

| Function Name | CalcCosAmpRec | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | TotSinAmp_Volts_T_f32 | float32 | 0.5 |  |  |
|  | TotCosAmp_Volts_T_f32 | float32 | 0.5 |  |  |
|  | SinRTAmpRec_Uls_T_f32 | float32 |  |  |  |
|  | SinCosNomRatio_Uls_T_f32 | float32 |  | 1 |  |
|  | CosSinNomRatio_Uls_T_f32 | float32 |  |  |  |
|  | RTToNomLowLmt_Uls_T_f32 | float32 | 0.98 | 1 |  |
|  | RTToNomHighLmt_Uls_T_f32 | float32 | 1 | 1.02 |  |
| Return Value | CosRTAmpRec_Uls_T_f32 | float32 | . |  | 2-13 |


**Table 13**

| Data | Value |
| --- | --- |
|  |  |
| Rte_InitValue_CorrectedMtrPos_Rev_f32 | 0 |
| Rte_InitValue_Cos1RTAmpRec_Uls_f32 | 0 |
| Rte_InitValue_Cos1RTOffset_Volt_f32 | 0 |
|  |  |
|  |  |
| Rte_InitValue_DiagCorrectedMtrPos_Rev_f32 | 0 |
|  |  |
| Rte_InitValue_MechMtrPos_Rev_f32 | 0 |
| Rte_InitValue_MotorVelMRF_MtrRadpS_f32 | 0 |
|  |  |
|  |  |
| Rte_InitValue_Sin1RTOffset_Volt_f32 | 0 |
|  |  |
|  |  |


**Table 14**

| Arguments Passed | Type |
| --- | --- |
| MtrCalDataPtr | MtrPosCal_DataType * |


**Table 15**

| Arguments Passed | Type |
| --- | --- |
| MtrCalDataPtr | MtrPosCal_DataType * |


**Table 16**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| MtrPos2_Init1 | On Event | On Init |
| MtrPos2_Per1 | 2 ms | ALL |


**Table 17**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| MtrPos2_SCom_ReadEOLMtrCals |  |
| MtrPos2_SCom_SetEOLMtrCals |  |


**Table 18**

| Name of Sub Module | Software Segment |
| --- | --- |
| MtrPos2_Init1 | RTE_START_SEC_SA_MTRPOS2_APPL_CODE |
| MtrPos2_Per1 | RTE_START_SEC_SA_MTRPOS2_APPL_CODE |


**Table 19**

| Name of Sub Module | Software Segment |
| --- | --- |
| OffsetInit |  |
| RunTimeFilter |  |
| CalcOffsetFromMinMax |  |
| CalcSinAmpRec |  |
| CalcCosAmpRec |  |


**Table 20**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version | 23-Oct-12 | OT |
| 2 | 2.0 | UTP updates | 18-Dec-12 | OT |
|  |  |  |  |  |
