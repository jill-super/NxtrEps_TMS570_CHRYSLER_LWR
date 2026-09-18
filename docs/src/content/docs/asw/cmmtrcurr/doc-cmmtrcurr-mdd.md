---
title: "Current-Mode Motor Current Sensing (CmMtrCurr)"
description: "Converted from CmMtrCurr_MDD.docx"
---

> **Source:** `CmMtrCurr/doc/CmMtrCurr_MDD.docx` (1,502,767 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module -- CmMtrCurr


# High-Level Description

The Current Measurement function is responsible for measuring the motor phase currents used as feedback by the Motor Control FDD. Two motor phase currents are measured using a shunt resistor and a differential amplifier circuitry, and along with the motor position are transformed into direct (D) and quadrature (Q) axes currents using the combined Clarke/Park transform

UNIT Test Notes:

Unit  test should be done with enabling one of the six predefned macro  MTRCURRPHASEBC, MTRCURRPHASECB, MTRCRRPHASECA, MTRCURRPHASEAB, MTRCURRPHASEAC, MTRCURRPHASEBA. Hence it should have six UTP results (one for each Macro enabled).


# Figures


## Component diagram


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

(This is for lookup tables (arrays) with fixed values, same name as other tables)


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Cosf

Sinf

Limit_m

Abs_f32_m

TableSize_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

IntplVarXY_s16_s16Xs16Y_Cnt

LPF_SvUpdate_u16InFixKTrunc_m

LPF_OpUpdate_u16InFixKTrunc_m

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m


## Data Hiding Functions

CmMtrCurr_Read_MRFMtrVel_MtrRadpS_f32

CmMtrCurr_Read_Vecu_Volt_f32

CmMtrCurr_Read_Phs1Curr_Cnt_u16

CmMtrCurr_Read_Phs2Curr_Cnt_u16

CmMtrCurr_Read_DCPhsAComp_Cnt_u16

CmMtrCurr_Read_DCPhsBComp_Cnt_u16

CmMtrCurr_Read_DCPhsCComp_Cnt_u16

CmMtrCurr_Read_MtrCurr1TempOffset_Volt_f32

CmMtrCurr_Read_MtrCurr2TempOffset_Volt_f32

CmMtrCurr_Read_MtrElecPol_Cnt_s08

CmMtrCurr_Read_MtrPosElec_Rev_u0p16

CmMtrCurr_Write_ElecPosDelayComp_Rad_f32

CmMtrCurr_Write_MtrCurrQax_Amp_f32

CmMtrCurr_Write_MtrCurrDax_Amp_f32

CmMtrCurr_Write_CorrMtrPosElec_Rev_f32

CmMtrCurr_Write_MtrCurrK1_Amps_f32

CmMtrCurr_Write_MtrCurrK2_Amps_f32

CmMtrCurr_Write_MtrCurr1_Volts_f32

CmMtrCurr_Write_MtrCurr2_Volts_f32


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only

None


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: CmMtrCurr_Init


#### Design Rationale

None


#### Module Outputs

None


#### Module Internal


## IF ((Rte_Pim_ShCurrCal()->EOLMtrCurrVcalCmd_VoltCnts_f32) >= FLT_EPSILON)


## MtrCurr1OffDelta_VoltpVoltCnts_M_f32=((Rte_Pim_ShCurrCal()->EOLMtrCurr1OffsetDiff_Volts_f32)/(Rte_Pim_ShCurrCal()->EOLMtrCurrVcalCmd_VoltCnts_f32))


## MtrCurr2OffDelta_VoltpVoltCnts_M_f32=((Rte_Pim_ShCurrCal()->EOLMtrCurr2OffsetDiff_Volts_f32)/(Rte_Pim_ShCurrCal()->EOLMtrCurrVcalCmd_VoltCnts_f32))

ELSE

MtrCurr1OffDelta_VoltpVoltCnts_M_f32 = D_ZERO_ULS_F32

MtrCurr2OffDelta_VoltpVoltCnts_M_f32 = D_ZERO_ULS_F32

END


## Periodic Functions


### Per: CmMtrCurr_Per1


#### Design Rationale

None


#### Program Flow Start

Rte_Call_CmMtrCurr_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

*FiltCntrlTemp_DegC_T_f32=Rte_IRead_CmMtrCurr_Per1_FiltCntrlTemp_DegC_**f32()*


#### Processing


#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_CmMtrCurr_Per1_MtrCurr1TempOffset_Volt_f32(MtrCurr1TempOffset_Volts_T_f32)

Rte_Iwrite_CmMtrCurr_Per1_MtrCurr2TempOffset_Volt_f32(MtrCurr2TempOffset_Volts_T_f32)


#### Program Flow End

Rte_Call_CmMtrCurr_Per1_CP1_CheckpointReached()


### Per: CmMtrCurr_Per2


#### Design Rationale

None


#### Program Flow Start

Rte_Call_CmMtrCurr_Per2_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

MtrCurrAlpha_Rev_T_f32=Rte_Iread_CmMtrCurr_Per2_MtrCurrAngle_ Rev_f32()

CorrMtrPosElec_Rev_T_f32=Rte_Iread_CmMtrCurr_Per2_CorrMtrCurrPosition_Rev_f32()

MtrCurrK1_Amps_T_f32=Rte_Iread_CmMtrCurr_Per2_MtrCurrK1_Amp_f32()

MtrCurrK2_Amps_T_f32=Rte_Iread_CmMtrCurr_Per2_MtrCurrK2_Amp_f32()

ADCMtrCurr1_Volts_T_f32=Rte_Iread_CmMtrCurr_Per2_ADCMtrCurr1_Volts_f32()

ADCMtrCurr2_Volts_T_f32=Rte_Iread_CmMtrCurr_Per2_ADCMtrCurr2_Volts_f32()


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

Rte_Call_CmMtrCurr_Per2_CP1_CheckpointReached()


### Per: CmMtrCurr_Per3


#### Design Rationale

None


#### Program Flow Start

Rte_Call_CmMtrCurr_Per3_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

ADCMtrCurr1_Volts_T_f32=Rte_Iread_CmMtrCurr_Per3_ADCMtrCurr1_Volts_f32();

ADCMtrCurr2_Volts_T_f32=Rte_Iread_CmMtrCurr_Per3_ADCMtrCurr2_Volts_f32();

Vecu_Volt_T_f32=Rte_Iread_CmMtrCurr_Per3_Vecu_Volt_f32();

MtrVel_MtrRadpS_T_f32 = Rte_Iread_CmMtrCurr_Per3_MtrVel_MtrRadpS_f32();

VehSpd_Kph_T_f32= Rte_Iread_CmMtrCurr_Per3_VehSpd_Kph_f32();

VhSpdValid_Cnt_T_lgc= Rte_Iread_CmMtrCurr_Per3_VhSpdValid_Cnt_lgc();

SrlComSvcDft_Cnt_T_b32=Rte_Iread_CmMtrCurr_Per3_SrlComSvcDft_Cnt_b32();

CurroffProcessFlag_T_enum=CurroffProcessFlag_M_enum;


#### Processing


#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_CmMtrCurr_Per3_ComOffset_Cnt_u16(ComOffset_Cnt_T_u16)


#### Program Flow End

Rte_Call_CmMtrCurr_Per3_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions


### CurrDQPer1


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local Copies

CmMtrCurr_Read_MRFMtrVel_MtrRadpS_f32(&MRFMtrVel_MtrRadpS_T_f32);

CmMtrCurr_Read_Vecu_Volt_f32(&Vecu_Volt_T_f32);

CmMtrCurr_Read_Phs1Curr_Cnt_u16(&Phs1Curr_Cnt_T_u16);

CmMtrCurr_Read_Phs2Curr_Cnt_u16(&Phs2Curr_Cnt_T_u16);

CmMtrCurr_Read_MtrCurr1TempOffset_Volt_f32(&MtrCurr1TempOffset_Volt_T_f32);

CmMtrCurr_Read_MtrCurr2TempOffset_Volt_f32(&MtrCurr2TempOffset_Volt_T_f32);

CmMtrCurr_Read_MtrElecPol_Cnt_s08(&MtrElecPol_Cnt_T_s08);

CmMtrCurr_Read_MtrPosElec_Rev_u0p16(&MtrPosElec_Rev_T_u0p16);


#### Processing


#### Store Local copy of outputs into Module Outputs

CmMtrCurr_Write_ElecPosDelayComp_Rad_f32(ElecPosDelayComp_Rad_T_f32);

CmMtrCurr_Write_MtrCurrQax_Amp_f32(MtrCurrFinalQax_Amps_T_f32);

CmMtrCurr_Write_MtrCurrDax_Amp_f32(MtrCurrFinalDax_Amps_T_f32);

CmMtrCurr_Write_CorrMtrPosElec_Rev_f32(CorrMtrPosElec_Rev_T_f32);

CmMtrCurr_Write_MtrCurrK1_Amps_f32(MtrCurrK1_Amps_T_f32);

CmMtrCurr_Write_MtrCurrK2_Amps_f32(MtrCurrK2_Amps_T_f32);

CmMtrCurr_Write_MtrCurr1_Volts_f32(Phs1Curr_Volts_T_f32);

CmMtrCurr_Write_MtrCurr2_Volts_f32(Phs2Curr_Volts_T_f32);


#### Program Flow End

N/A


## Serial Communication Functions


### Scomm: CmMtrCurrTempOffset_Scom_Get


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### Scomm: CmMtrCurrTempOffset_Scom_Set


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### Scomm: CmMtrCurr_Scom_CalGain


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

Rte_Read_MtrVel_MtrRadpS_f32(&MtrVel_MtrRadpS_T_f32)

Rte_Read_VehSpd_Kph_f32(&VehSpd_Kph_T_f32)

Rte_Read_VhSpdValid_Cnt_lgc(&VhSpdValid_T_Cnt_lgc)


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### Scomm: CmMtrCurr_Scom_CalOffset


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

Rte_Read_MtrVel_MtrRadpS_f32(&MtrVel_MtrRadpS_T_f32)

Rte_Read_VehSpd_Kph_f32(&VehSpd_Kph_T_f32)

Rte_Read_VhSpdValid_Cnt_lgc(&VhSpdValid_T_Cnt_lgc)


#### Processing


#### Store Local copy of outputs into Module Outputs

Rte_Write_CurrentGainSvc_Cnt_lgc(CurrentGainSvc_Cnt_M_lgc)


#### Program Flow End

None


### Scomm: CmMtrCurr_Scom_MtrCurrOffReadStatus


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### Scomm: CmMtrCurr_Scom_ReadMtrCurrCals


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

None


### Scomm: CmMtrCurr_Scom_SetMtrCurrCals


#### Design Rationale

None


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

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
| FiltCntrlTemp_DegC_f32 | FiltCntrlTemp_DegC_f32 | MtrCurr1TempOffset_Volt_f32 |
| MtrCurrAngle_Rev_f32 | MtrCurrAngle_Rev_f32 | MtrCurr2TempOffset_Volt_f32 |
|  |  | ComOffset_Cnt_u16 |
| CorrMtrPosElec_Rev_f32 | CorrMtrPosElec_Rev_f32 | CDD_ElecPosDelayComp_Rad_G_f32 |
| MtrCurrK1_Amp_f32 | MtrCurrK1_Amp_f32 | CDD_MtrElecPol_Cnt_G_s8 |
| MtrCurrK2_Amp_f32 | MtrCurrK2_Amp_f32 | CDD_MtrCurrQax_Amp_G_f32[] |
| ADCMtrCurr1_Volts_f32 | ADCMtrCurr1_Volts_f32 | CDD_MtrCurrDax_Amp_G_f32[] |
| ADCMtrCurr2_Volts_f32 | ADCMtrCurr2_Volts_f32 | CDD_CorrMtrPosElec_Rev_G_f32[] |
| Vecu_Volt_f32 | Vecu_Volt_f32 | CDD_MtrCurrK1_Amps_G_f32[] |
| MtrVel_MtrRadpS_f32 | MtrVel_MtrRadpS_f32 | CDD_MtrCurrK2_Amps_G_f32[] |
| VehSpd_Kph_f32 | VehSpd_Kph_f32 | CDD_MtrCurr1_Volts_G_f32[] |
| VhSpdValid_Cnt_lgc | VhSpdValid_Cnt_lgc | CDD_MtrCurr2_Volts_G_f32[] |
| SrlComSvcDft_Cnt_b32 | SrlComSvcDft_Cnt_b32 | CorrMtrCurrPosition_Rev_f32 |
| MEC_Cnt_enum | MEC_Cnt_enum | CurrentGainSvc_Cnt_lgc |
| CDD_MRFMtrVel_MtrRadpS_G_f32[] | CDD_MRFMtrVel_MtrRadpS_G_f32[] |  |
| CDD_Vecu_Volt_G_f32[] | CDD_Vecu_Volt_G_f32[] |  |
| DCPhsBComp_Cnt _u16 | DCPhsBComp_Cnt _u16 |  |
| DCPhsCComp_Cnt_u16 | DCPhsCComp_Cnt_u16 |  |
| DCPhsCComp_Cnt_G_u16 | DCPhsCComp_Cnt_G_u16 |  |
| CDD_MtrCurr1TempOffset_Volt_G_f32[] | CDD_MtrCurr1TempOffset_Volt_G_f32[] |  |
| CDD_MtrCurr2TempOffset_Volt_G_f32[] | CDD_MtrCurr2TempOffset_Volt_G_f32[] |  |
| CDD_MtrPosElec_Rev_G_u0p16[] | CDD_MtrPosElec_Rev_G_u0p16[] |  |
| CDD_CDDDataAccessBfr_Cnt_G_u16 | CDD_CDDDataAccessBfr_Cnt_G_u16 |  |
| CDD_AppDataFwdPthAccessBfr_Cnt_G_u16 | CDD_AppDataFwdPthAccessBfr_Cnt_G_u16 |  |
| CorrMtrCurrPosition_Rev_f32 | CorrMtrCurrPosition_Rev_f32 |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| MtrCurr1OffDelta_VoltpVoltCnts_M_f32 | Single precision float | 0.0000125 | 750 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2OffDelta_VoltpVoltCnts_M_f32 | single precision float | 0.0000125 | 750 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1LpFltrSV_Volts_M_u3p29 | 2^-29 | 0 | 5 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2LpFltrSV_Volts_M_u3p29 | 2^-29 | 0 | 5 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| FiltMtrCurr1_Volts_M_f32 | single precision float | 0 | 5 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| FiltMtrCurr2_Volts_M_f32 | single precision float | 0 | 5 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
|  |  |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_ |
|  |  |  |  |  |
|  |  |  |  |  |
| CurroffProcessFlag_M_enum | single precision float | n/a | n/a | CMMTRCURR_START_SEC_VAR_CLEARED_ UNSPECIFIED |
| CurrOffTrimFlag_M_lgc | BOOLEAN | True | False | CMMTRCURR_START_SEC_VAR_CLEARED_BOOLEAN |
| CurrOffState_ULS_M_enum | N/A | N/A | N/A | CMMTRCURR_START_SEC_VAR_CLEARED_UNSPECIFIED |
| MtrCurr1SumHi_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2SumHi_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| VecuSum_Volt_M_f32 | single precision float | -20 | 20 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CurrOffAvgCounter_Cnt_M_u16 | 1 | 0 | 2^16 | CMMTRCURR_START_SEC_VAR_CLEARED_16 |
| MtrCurr1OffsetHi_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2OffsetHi_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurrValCmd_VoltCnts_M_f32 | single precision float | 0 | 80000 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1SumLo_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2SumLo_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1OffsetLo_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2OffsetLo_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1SumZero_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2SumZero_Volt_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1OffsetZero_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2OffsetZero_Volts_M_f32 | single precision float | 1.0 | 3.0 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1offsetDiff_Volt_D_f32 | single precision float | -0.046875 | 0.046875 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2offsetDiff_Volt_D_f32 | single precision float | -0.046875 | 0.046875 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| Duty1Cnts_Cnt_D_f32 | single precision float | 0 | 80000 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| Duty2Cnts_Cnt_D_f32 | single precision float | 0 | 80000 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr1Offset_Volt_D_f32 | single precision float | -0.046875 | 0.046875 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurr2Offset_Volt_D_f32 | single precision float | -0.046875 | 0.046875 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CorrMtrCurr1_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CorrMtrCurr2_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CorrMtrPosElec_Rev_D_f32 | single precision float | 0 | 1 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurrK1_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| MtrCurrK2_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CurrVectPosition_Rev_D_f32 | single precision float | 0 | 1 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| VectPosCosTheta_Uls_D_f32 | single precision float | -1 | 1 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| VectPosSinTheta_Uls_D_f32 | single precision float | -1 | 1 | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CurrCorrDiag_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| FiltCurrCorrDiag_Amps_D_f32 | single precision float |  |  | CMMTRCURR_START_SEC_VAR_CLEARED_32 |
| CurrentGainSvc_Cnt_M_lgc | Boolean | 0 | 1 | CMMTRCURR_START_SEC_VAR_CLEARED_BOOLEAN |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| CurrTempOffsetType | CurrTempOffsetX_DegC_s10p5 | CurrTempOffsetTblType | -50 | 150 |
|  | CurrOffsetY1_Volts_s4p11 | CurrTempOffsetTblType | -0.026 | 0.026 |
|  | CurrOffsetY2_Volts_s4p11 | CurrTempOffsetTblType | -0.026 | 0.026 |
| PhaseCurrCal_DataType | EOLMtrCurrVcalCmd_VoltCnts_f32 | float | 0 | 80000 |
|  | EOLPhscurr1Gain_AmpspVolt_f32 | float | 20 | 125 |
|  | EOLMtrCurr2OffsetDiff_Volts_f32 | float | 1.0 | 3.0 |
|  | EOLMtrCurr1OffsetDiff_Volts_f32 | float | 1.0 | 3.0 |
|  | EOLMtrCurr1OffsetLo_Volts_f32 | float | 1.0 | 3.0 |
|  | EOLMtrCurr2OffsetLo_Volts_f32 | float | 1.0 | 3.0 |
|  | EOLPhscurr2Gain_AmpspVolt_f32 | float | 20 | 125 |
| CurrTempOffsetTblType[16] |  | Sint16 | Full | Full |


**Table 4**

| Constant Name |
| --- |
| k_CurrOffGainKn_Cnt_u16 |
| k_CurrCorrErrFilt |
| k_MaxCurrOffMtrVel_RadpS_f32 |
| k_MtrCurrEOLMaxOffset_Volts_f32 |
| k_MtrCurrEOLMinOffset_Volts_f32 |
| k_MtrCurrEOLMaxGain_AmpspVolts_f32 |
| k_MtrCurrEOLMinGain_AmpspVolts_f32 |
| k_MtrPosComputDelay_Sec_f32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_MTRCURROFFHICOMOFF_CNT_U16 | 1 | Counts | 4000 |
| D_CURROFFNOOFAVG_CNT_U16 | 1 | Counts | 64 |
| D_MTRCURROFFLOCOMOFF_CNT_U16 | 1 | Counts | 500 |
| D_MTRCURROFFZEROCOMOFF_CNT_U16 | 1 | Counts | 0 |
| D_REVWITHROUND_ULS_F32 | single precision float | Unitless | 65536.5 |
| D_SCALERADTOCNTS_ULS_F32 | single precision float | Unitless | 10430.3783505 |
| D_ROUND_ULS_F32 | single precision float | Unitless | 0.5 |
| D_CNVRTP29TOP13_CNT_U16 | 1 | Counts | 16 |
| D_POSITIVEONE_CNT_S8 | 1 | Counts | 1 |
| D_ONEDIVSQRT3_F32 | single precision float | Unitless | 0.57735 |


**Table 6**

| Constant Name |
| --- |
| D_2PI_ULS_F32 |
| D_FALSE_CNT_LGC |
| D_VECUMIN_VOLTS_F32 |
| D_ZERO_ULS_F32 |
| D_ZERO_CNT_U16 |
| D_ZERO_CNT_U32 |
| D_MTRPOLESDIV2_CNT_U8 |
|  |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Data | Value |
| --- | --- |
| Rte_InitValue_ADCMtrCurr1_Volts_f32 | 0 |
| Rte_InitValue_ADCMtrCurr2_Volts_f32 | 0 |
| Rte_InitValue_ComOffset_Cnt_u16 | 0 |
| Rte_InitValue_ CorrMtrCurrPosition _Rev_f32 | 0 |
| Rte_InitValue_FiltCntrlTemp_DegC_f32 | 0 |
| Rte_InitValue_MEC_Cnt_enum | 0 |
| Rte_InitValue_MtrCurr1TempOffset_Volt_f32 | 0 |
| Rte_InitValue_MtrCurr2TempOffset_Volt_f32 | 0 |
| Rte_InitValue_MtrCurrAngle _Rev_f32 | 0 |
|  | 0 |
| Rte_InitValue_MtrCurrK1_Amp_f32 | 0 |
| Rte_InitValue_MtrCurrK2_Amp_f32 | 0 |
| Rte_InitValue_MtrVel_MtrRadpS_f32 | 0 |
| Rte_InitValue_SrlComSvcDft_Cnt_b32 | 0 |
| Rte_InitValue_Vecu_Volt_f32 | 5 |
| Rte_InitValue_VehSpd_Kph_f32 | 0 |
| Rte_InitValue_VhSpdValid_Cnt_lgc | FALSE |
| Rte_InitValue_ CurrentGainSvc_Cnt_lgc | FALSE |


**Table 9**

| Function Name | CmMtrCurrTempOffset_Scom_Get | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | CurrTempOffCal | CurrTempOffsetType * |  |  |  |
| Return Value | void | NA | NA | NA |  |


**Table 10**

| Function Name | CmMtrCurrTempOffset_Scom_Set | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | CurrTempOffCal | CurrTempOffsetType * |  |  |  |
| Return Value | void | NA | NA | NA |  |


**Table 11**

| Function Name | CmMtrCurr_Scom_CalGain | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None | None |  |  |  |
| Return Value | RetrunValue | Std_ReturnType |  |  |  |


**Table 12**

| Function Name | CmMtrCurr_Scom_CalOffset | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None | None |  |  |  |
| Return Value | RetrunValue | Std_ReturnType |  |  |  |


**Table 13**

| Function Name | CmMtrCurr_Scom_MtrCurrOffReadStatus | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | CurrOffStatus | MtrCurrOffProcessFlag * |  |  |  |
| Return Value | void | NA | NA | NA |  |


**Table 14**

| Function Name | CmMtrCurr_Scom_ReadMtrCurrCals | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | ShCurrCalPtr | PhaseCurrCal_DataType * |  |  |  |
| Return Value | void | NA | NA | NA |  |


**Table 15**

| Function Name | CmMtrCurr_Scom_SetMtrCurrCals | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | ShCurrCalPtr | PhaseCurrCal_DataType * |  |  |  |
| Return Value | void | NA | NA | NA |  |


**Table 16**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| CmMtrCurr_Init | On Init | Init |
| CmMtrCurr_Per1 | 100ms | All |
| CmMtrCurr_Per2 | 2ms | Operate |
| CmMtrCurr_Per3 | 2ms | Operate |
| CurrDQPer1 | 125us (MtrCtrl ISR) | All |


**Table 17**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| CmMtrCurr_Scom_CalGain |  |
| CmMtrCurr_Scom_CalOffset |  |
| CmMtrCurr_Scom_MtrCurrOffReadStatus |  |
| CmMtrCurr_Scom_ReadMtrCurrCals |  |
| CmMtrCurr_Scom_SetMtrCurrCals |  |
| CmMtrCurrTempOffset_Scom_Get |  |
| CmMtrCurrTempOffset_Scom_Set |  |
|  |  |


**Table 18**

| Name of Sub Module | Software Segment |
| --- | --- |
| CmMtrCurr_Init | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Per1 | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Per2 | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Per3 | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CurrDQPer1 |  |
| CmMtrCurr_Scom_CalGain | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Scom_CalOffset | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Scom_MtrCurrOffReadStatus | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Scom_ReadMtrCurrCals | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurr_Scom_SetMtrCurrCals | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurrTempOffset_Scom_Get | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |
| CmMtrCurrTempOffset_Scom_Set | RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |


**Table 19**

| Name of Sub Module | Software Segment |
| --- | --- |
|  |  |


**Table 20**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1.0 | Initial Version (FDD 01 C Ver 005) | 01-Dec-12 | Selva |
| 2.0 | Configured global read/write macros for global data (anomaly 4696) | 23-Mar-13 | OT |
| 3.0 | Fixes for Anamoly 5561 and A5566 added | 4-Sep-13 | Selva |
| 4.0 | Updated to FDD 01C Ver 006 | 07-Oct-13 | VK |
| 5.0 | Anomaly 5967 and 5873 | 06-Nov-13 | SP |
| 6.0 | Range corrections for ‘MtrCurr1OffDelta_VoltpVoltCnts_M_f32’ and ‘MtrCurr2OffDelta_VoltpVoltCnts_M_f32’ | 9-Nov-13 | SR |
|  |  |  |  |
