---
title: "Motor Position"
description: "Converted from Motor_Position_MDD.docx"
---

> **Source:** `MtrPos/doc/Motor_Position_MDD.docx` (560,661 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module --


# High-Level Description

This module calculates the cumulative and corrected motor positions.  It also outputs the sine and cosine position signals used for diagnostics and motor electrical and mechanical position.


# Figures


#### Component Diagram


# Variable Data Dictionary


## Module Internal Variables


### User defined typedef definition/declaration


# Constant Data Dictionary


## Calibration Constants


## Program(fixed) Constants


### Embedded Constants


#### Local


#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.


### Module specific Lookup Tables Constants


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

_atan2_asm_

Limit_m

Sign_s16_m


## Data Hiding Functions

Adc2_GetSinTheta1_Cnt_u16_m

Adc2_GetCosTheta1_Cnt_u16_m

Rte_Pim_MtrPosSnsr_EOLData


## Global Functions/Macros Defined by this Module

1. MtrPos_Per1

## Local Functions/Macros Used by this MDD only


### Signal Correction


#### Design Rationale

This function is responsible for scaling and correcting the motor sense board sine and cosine signals based upon End Of Line calibrations.  The correction uses the sensor calibrations to subtract the DC offset and normalize each signal to a nominal amplitude of +/- 1.


#### Description


### Quadrature Correction


#### Design Rationale

This function is responsible for adjusting the cosine signal for any quadrature error between the sine and cosine signals.  Ideally, the sine and cosine signals are exactly 90 degrees out of phase of eachother.  This function will adjust the cosine signal based upon sensor calibrations to correct for any error from the ideal 90 degree phase difference.

The Quadrature correction should follow the following algorithm per requirements…

However, “” becomes a small enough number that the cos() term becomes close enough to “1” to have a negligible effect on the signal.  Therefore, in order to reduce throughput of this algorithm, the application of 1/cos() is omitted.


#### Description


### Round and Shift by 13 Bits


#### Design Rationale

This function will perform a rounding before applying a shift of 13 bits on the variable passed to the function.  The function will use the sign bit of the input to help determine the value to be added to the signal before performing the shift operation.  For a positive value, the value to be added is simply half of 2^[#bits to shift]… for this function, 13 bits are shifted off so 2^12 should be added to the signal before the shift is performed.  However, for negative numbers, the value to be added is 2^[#bits to shift] -1.  Therefore, the sign bit of the input is subtracted from 2^[#bits to shift], and this will result in the correct value for both positive and negative numbers.

Note that this function is designed to produce identical results to the **FPM_FixWithRound_m** that will cause a shift of 13 bits, but has a restricted input range as shown above.


#### Description

**return** (((x)+(D_HALFPREC13_CNT_S32-((x)>>D_SIGNBITSHIFT32_CNT_U16)))>>D_SHIFT13_CNT_S16)


### Get Sine Voltage Macro Function


#### Design Rationale

The actual implementation of this function is in macro form. When called, the function (macro) will return the ADC reading for the corresponding analog input.


### Get Cosine Voltage Macro Function


#### Design Rationale

The actual implementation of this function is in macro form. When called, the function (macro) will return the ADC reading for the corresponding analog input.


# Software Module Implementation


## Runtime Environment (RTE) Initial Values


## Initialization Functions


### Init: _Init1


#### Design Rationale

None


#### Module Internal and Outputs


## Periodic Functions


### Per: _Per1


#### Design Rationale

The computation of AlignedCumMtrPosMRF_Rev_M_s15p16 is optimized to take advantage of the fact that the relative position is sized to be a modulo 65536 value (i.e. rolls over at the16 bit value boundary).  The operation specified to the compiler is to:

1. Perform an unsigned subtraction of the z-1 and current position
1. Explicitly mask the subtraction result to 16bits to ensure, that in the event that the compiler determines that a 32 bit subtraction is appropriate, the result is masked to only provide the lower 16 bits of the result.
1. Cast the unsigned result of the mask as a signed 16 bit value so that rollovers occurring in the subtraction correctly indicate the integer amount of change.
1. Finally cast the expression up to this point to a signed 32 bit number to promote the signed 16 integer and sign extend it to allow it to be added properly to the 32 bit accumulator,  AlignedCumMtrPosMRF_Rev_M_s15p16
The above method eliminates any need for a conditional branch expression to handle the rollover points, thus avoiding the branching penalty.


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies


#### Signal Processing


#### Store Local copy of outputs into Module Outputs


#### Program Flow End

N/A


### Per: _Per2


#### Design Rationale

This function accesses the AlignedCumMtrPosMRF_Rev_M_s15p16 signal produced by Per1 which is running in the MtrCtrl ISR.  Ther is no concern for data consistency in this case because the signal is 32 bits wide and it is assumed that the target processor supports atomic 32 data accesses (i.e as is the case for the TMS570).

This function should be run before MtrPos3_Per1, as the comparisons (in both the main and diverse paths) on the generated signals assume that this order will be followed.


#### Program Flow Start

Rte_Call_MtrPos2_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

AssistAsmPolarity_T_f32 = Rte_IRead_MtrPos_Per2_AssistAssemblyPolarity_Cnt_s08()


#### Processing of function


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_MtrPos_Per2_AlignedCumMtrPosMRF_Deg_f32(AlignedCumMtrPosMRF_Deg_T_f32)

Rte_IWrite_MtrPos_Per2_CumMtrPosMRF_Deg_f32(CumMtrPosMRF_Deg_T_f32)

Rte_IWrite_MtrPos_Per2_SysCCumMtrPosMRF_Deg_f32(CumMtrPosMRF_Deg_T_f32)

Rte_IWrite_MtrPos_Per2_CumMtrPosCRF_Deg_f32(CumMtrPosMRF_Deg_T_f32 * AssistAsmPolarity_T_f32)

Rte_IWrite_MtrPos_Per2_SysCCumMtrPosCRF_Deg_f32(CumMtrPosMRF_Deg_T_f32 * AssistAsmPolarity_T_f32)


#### Program Flow End

N/A


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


### SCom: _SCom_SetEOLMtrCals


#### Design Rationale


#### Provide exclusive area around EOL Data update to ensure the data stays consistent.  If the BEMF R/C check, for example, pre-empts this update while the BEMF and R_BEMF values are inconsistent, a false failure will be detected.  For simplicity, this implementation of the exclusive area protection does not provide a configurable type of protection, but rather always uses Suspend/Resume interrupts.  If the need arises in the future this design can be updated.


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Processing of function


#### Store Local copy of outputs into Module Outputs

N/A


#### Program Flow End

N/A


# Execution Requirements


## Execution Rates for sub-modules called by the Scheduler


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

INLINE functions in GlobalMacro.h are not unit tested


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
|  |  | MtrPos_MechMtrPos_Rev_G_u0p16 |
|  |  | MtrPos_CorrectedMtrPos_Rev_G_u0p16 |
|  |  | MtrPos_SinTheta1_Volts_G_s2p13 |
|  |  | MtrPos_CosTheta1_Volts_G_s2p13 |
|  |  | MtrPos_SampleTime_uS_G_u32 |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| SinTheta2_Uls_D_s2p13 | 2-13 | - |  | MTRPOS_START_SEC_VAR_CLEARED_16 |
| MtrPos_CorrectedMtrPos_Rev_M_u0p16 [D_MTRPOSDBLBUFFSZ_CNT_U08] | 2-16 | 0 |  | MTRPOS_START_SEC_VAR_CLEARED_16 |
| MtrPos_Cos1Scaled_Volts_M_u3p13 [D_MTRPOSDBLBUFFSZ_CNT_U08] | 2-13 |  |  | MTRPOS_START_SEC_VAR_CLEARED_16 |
| MtrPos_Sin1Scaled_Volts_M_u3p13 [D_MTRPOSDBLBUFFSZ_CNT_U08] | 2-13 |  |  | MTRPOS_START_SEC_VAR_CLEARED_16 |
| MtrPos_MechMtrPos_Rev_M_u0p16 [D_MTRPOSDBLBUFFSZ_CNT_U08] | 2-16 |  |  | MTRPOS_START_SEC_VAR_CLEARED_16 |
| MtrPos_CumMtrPosOff_Deg_M_f32 |  |  |  | MTRPOS_START_SEC_VAR_NOINIT_32 |
| MtrPos_CumMtrPosInputBfr_Cnt_M_u08 | 1 | 0 | 1 | MTRPOS_START_SEC_VAR_CLEARED_8 |
| MtrPos_CumMtrPosOffComplete_Cnt_M_lgc | N/A | FALSE | TRUE | MTRPOS_START_SEC_VAR_CLEARED_BOOLEAN |
| tempAlignedCumMtrPosMRF_Rev_M_s15p16 | 2-16 |  |  | MTRPOS_START_SEC_VAR_NOINIT_32 |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| MtrPosCal_DataType | BEMFCal_Rev_u0p16 R_BEMFCal_Rev_u0p16 Sin1Offset_Volts_u3p13 Sin1AmpRec_Uls_u3p13 Cos1Offset_Volts_u3p13 Cos1AmpRec_Uls_u3p13 SinDelta1_Uls_s2p13 CosDelta1Rec_Uls_u3p13 Sin1OffCorr_Volts_s2p13 Sin1GainCorr_Uls_u1p15 Cos1OffCorr_Volts_s2p13 Cos1GainCorr_Uls_u1p15 SinHarTbl_Cnt_sm6p13[144] CosHarTbl_Cnt_sm6p13[144] | u0p16_T u0p16_T u3p13_T u3p13_T u3p13_T u3p13_T s2p13_T u3p13_T s2p13_T u1p15_T s2p13_T u1p15_T sm6p13_T sm6p13_T |  |  |


**Table 4**

| Constant Name |
| --- |
| None |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_ADCREF_VOLTS_F32 | floating point | Volts | 5 |
| D_ADCFULLSCALE_CNTS_U16 | 1 | Counts | 4095 |
| D_CNVRTP29TOP13_CNT_U16 | 1 | Counts | 16 |
| D_SCALE_VOLTSPERCOUNT_U3P29 | 2-29 | Volts per Count | D_ADCREF_VOLTS_F32/D_ADCFULLSCALE_CNTS_U16 |
| D_SIGCORRLOLMT_ULS_S5P26 | 2-26 | Unitless | -3 |
| D_SIGCORRHILMT_ULS_S5P26 | 2-26 | Unitless | 3 |
| D_SINCOSHILMT_ULS_S2P13 | 2-13 | Unitless | 2 |
| D_SINCOSLOLMT_ULS_S2P13 | 2-13 | Unitless | -2 |
| D_HARPOSROUNDFACTOR_ULS_U0P16 | 2-16 | Counts | 0.003472222222 |
| D_HALFPREC13_CNT_S32 | 1 | Counts | 4096 |
| D_SHIFT13_CNT_S16 | 1 | Counts | 13 |
| D_SIGNBITSHIFT32_CNT_U16 | 1 | Counts | 31 |
| D_HARTBLSIZE_CNT_U16 | 1 | Counts | 144 |
| D_PIREV_REV_U1P15 | 2-15 | Rev | 0.5 |
| D_MASK16BITS_CNT_U16 | 1 | Counts | 0xFFFF |


**Table 6**

| Constant Name |
| --- |
| None |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| MtrPos_EOLDataPtr_Cnt_M_Str | N/A | Constant Pointer to Rte_Pim_MtrPosSnsr_EOLData() | MTRPOS_START_SEC_CONST_UNSPECIFIED |


**Table 8**

| Function Name | SignalCorrect | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | Signal_Volts_T_u3p13 | u3p13_T | 0 |  |
|  | Offset_Volts_T_u3p13 | u3p13_T |  | .8 |
|  | AmpRec_Uls_T_u3p13 | u3p13_T |  |  |
| Return Value | Signal_Uls_T_s2p13 | s2p13_T | -3 | 3 |


**Table 9**

| Function Name | QuadCorrect | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | CorrSin_Uls_T_s2p13 | s2p13_T | -3 | 3 |
|  | CorrCos_Uls_T_s2p13 | s2p13_T | -3 | 3 |
|  | SinDelta_Uls_T_s2p13 | s2p13_T | -0.0174524 | 0.0174524 |
| Return Value | CorrCos_Uls_T_s2p13 | s2p13_T | -3 | 3 |


**Table 10**

| Function Name | RoundAndShift13_s32 | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | x | sint32 | -2^31 | (2^31)-(2^12)-1 |
| Return Value | See Function |  |  |  |


**Table 11**

| Function Name | Adc2_GetSinTheata1_Cnt_u16_m | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |
| Return Value | SinSignal_Volts_T_u3p13 | U16 | 0 | 4095 |


**Table 12**

| Function Name | Adc2_GetCosTheata1_Cnt_u16_m | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |
| Return Value | CosSignal_Volts_T_u3p13 | U16 | 0 | 4095 |


**Table 13**

| Data | Value |
| --- | --- |
| Rte_InitValue_AlignedCumMtrPosMRF_Deg_f32 | 0 |
| Rte_InitValue_CumMtrPosMRF_Deg_f32 | 0 |
| Rte_InitValue_CumMtrPosCRF_Deg_f32 | 0 |
| Rte_InitValue_SysCCumMtrPosMRF_Deg_f32 | 0 |
| Rte_InitValue_SysCCumMtrPosCRF_Deg_f32 | 0 |


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
| _Init1 | Once | COLD_INIT |
| _Per1 | 62.5 us | ALL |
| _Per2 | 1 ms | ALL |


**Table 17**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| MtrPos2_SCom_ReadEOLMtrCals |  |
| MtrPos2_SCom_SetEOLMtrCals |  |


**Table 18**

| Name of Sub Module | Software Segment |
| --- | --- |
| _Init1 | RTE_START_SEC_SA_MTRPOS_APPL_CODE |
| _Per1 |  |
| _Per2 |  |


**Table 19**

| Name of Sub Module | Software Segment |
| --- | --- |
| SignalCorrect |  |
| QuadCorrect |  |
| RoundAndShift13_s32 |  |


**Table 20**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1 | Initial MDD version. | 11 Jul 12 | JWJ |
| 2 | 2 | Added missing input/output/module internal variables | 13 Jul 12 | JWJ |
| 3 | 3 | Implemented FDD 06B v004 | 23-Oct-12 | OT |
| 4 | 4 | UTP Updates | 21-Nov-12 | OT |
| 5 | 5 | Updated Component design methodology to encapsulate component internal data flow outside of the Rte. | 20-Feb-13 | JJW |
| 6 | 6 | Changed cumulative position algorithm to eliminate the rollover synchronization issue between the atan and rollover detection methods. | 20-Mar-13 | JJW |
|  |  |  |  |  |
