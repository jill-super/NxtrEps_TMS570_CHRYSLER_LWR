---
title: "Arbiter Limiter Chrysler"
description: "Converted from Arbiter_Limiter_Chrysler_MDD.docx"
---

> **Source:** `ArbLmt/doc/Arbiter_Limiter_Chrysler_MDD.docx` (696,501 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module arbitrates between the HaLF, DST, and PA features to produce the input and output torque overlay signals.  It also provides an output showing which features are enabled.


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

Limit_m

Abs_f32_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

Sign_f32_m

BilinearXMYM_s16_u16XMs16YM_Cnt

TableSize_m


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module

None


## Local Functions/Macros Used by this MDD only


### Abriter Slew Limit


#### Description


### Arbiter Priority


#### Description


### Arbiter Ramping


#### Description


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions

None


## Periodic Functions


### Per: _Per1


#### Design Rationale

None


#### Program Flow Start

Rte_Call_ArbLmt_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

DSTActive_Cnt_T_lgc = Rte_IRead_ArbLmt_Per1_DSTActive_Cnt_lgc()

HaLFActive_Cnt_T_lgc = Rte_IRead_ArbLmt_Per1_HaLFActive_Cnt_lgc()

DSTState_Cnt_T_u08 = Rte_IRead_ArbLmt_Per1_DSTState_Cnt_u08()

DSTTrqOvCmdRqst_HwNm_T_f32 = Rte_IRead_ArbLmt_Per1_DSTTrqOvCmdRqst_HwNm_f32()

HaLFTrqOvCmdRqst_MtrNm_T_f32 = Rte_IRead_ArbLmt_Per1_HaLFTrqOvCmdRqst_MtrNm_f32()

HaLFTOState_Cnt_T_u08 = Rte_IRead_ArbLmt_Per1_HaLFTOState_Cnt_u08()

PATrqOvCmdRqst_HwNm_T_f32 = Rte_IRead_ArbLmt_Per1_PATrqOvCmdRqst_HwNm_f32()

PrkAssistState_Cnt_T_u08 = Rte_IRead_ArbLmt_Per1_PrkAssistState_Cnt_u08()

VehicleSpeed_Kph_T_f32 = Rte_IRead_ArbLmt_Per1_VehicleSpeed_Kph_f32()


#### DST Slew

c


#### HaLF Slew


#### PPPA Slew


#### Priority


#### Ramping


#### Arbiter


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_ArbLmt_Per1_ActiveFunctionBits_Cnt_u08(ActiveFunctionBits_Cnt_T_u08)

Rte_IWrite_ArbLmt_Per1_DSTSlewComplete_Cnt_lgc(DSTSlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_HaLFSlewComplete_Cnt_lgc(HaLFSlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_IpTrqOvr_HwNm_f32(IpTrqOvr_HwNm_T_f32)

Rte_IWrite_ArbLmt_Per1_OpTrqOvr_MtrNm_f32(OpTrqOvr_MtrNm_T_f32)

Rte_IWrite_ArbLmt_Per1_PAReturnSclFct_Uls_f32(PAReturnSclFct_Uls_T_f32)

Rte_IWrite_ArbLmt_Per1_PrkAsstSlewComplete_Cnt_lgc(PPPASlewComplete_Cnt_T_lgc)

Rte_IWrite_ArbLmt_Per1_PICmpDisableLearning_Cnt_lgc(PICmpDisableLearning_Cnt_T_lgc)


#### Program Flow End

Rte_Call_ArbLmt_Per1_CP1_CheckpointReached()


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
| HaLFTrqOvCmdRqst_MtrNm_f32 | HaLFTrqOvCmdRqst_MtrNm_f32 | OpTrqOvr_MtrNm_f32 |
| DSTTrqOvCmdRqst_HwNm_f32 | DSTTrqOvCmdRqst_HwNm_f32 | IpTrqOvr_HwNm_f32 |
| PATrqOvCmdRqst_HwNm_f32 | PATrqOvCmdRqst_HwNm_f32 | ActiveFunctionBits_Cnt_u08 |
| HaLFActive_Cnt_lgc | HaLFActive_Cnt_lgc | DSTSlewComplete_Cnt_lgc |
| DSTActive_Cnt_lgc | DSTActive_Cnt_lgc | HaLFSlewComplete_Cnt_lgc |
| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 | PPPASlewComplete_Cnt_lgc |
| DSTState_Cnt_u08 | DSTState_Cnt_u08 | PAReturnSclFct_Uls_f32 |
| HalfTOState_Cnt_u08 | HalfTOState_Cnt_u08 | PICmpDisableLearning_Cnt_lgc |
| PrkAssistState_Cnt_u08 | PrkAssistState_Cnt_u08 |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| DSTScalarSlew_Uls_M_f32 | Single Precision Float` | 0 | 1 | ARBLMT_START_SEC_VAR_CLEARED_32 |
| HaLFScalarSlew_Uls_M_f32 | Single Precision Float` | 0 | 1 | ARBLMT_START_SEC_VAR_CLEARED_32 |
| DSTSlew_HwNm_M_f32 | Single Precision Float | 0 | 1 | ARBLMT_START_SEC_VAR_CLEARED_32 |
| HaLFSlew_MtrNm_M_f32 | Single Precision Float | 0 | 1 | ARBLMT_START_SEC_VAR_CLEARED_32 |
| PPPASlew_HwNm_M_f32 | Single Precision Float | 0 | 1 | ARBLMT_START_SEC_VAR_CLEARED_32 |
| DSTLowSpdPri_Cnt_M_lgc | boolean |  |  |  |
| PrevDSTActive_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PrevDSTRampActive_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PrevHaLFRampActive_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PPPAPriority_Cnt_D_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| SlewActive_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PrevDSTSlewState_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PrevHaLFSlewState_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| PrevPPPASlewState_Cnt_M_lgc | boolean | FALSE | TRUE | ARBLMT_START_SEC_VAR_CLEARED_BOOLEAN |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_PPPAPriorityVehSpd_Kph_f32 |
| k_RateLimit_UlspS_f32 |
| k_DSTSlewRate_NmpS_f32 |
| k_HaLFSlewRate_NmpS_f32 |
| k_PPPASlewRate_NmpS_f32 |
| t2_AsstY0_MtrNm_s4p11[][] |
| t2_HwtX0_HwNm_u8p8[][] |
| t_PPPAVehSpd_Kph_u9p7[] |
| k_HalFPICmpThresh_MtrNm_f32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_4MS_S_F32 | Single Precision Float | S | 0.004 |
| D_PPPAFUNCBIT_CNT_U08 | 1 | Counts | 1 |
| D_DSTFUNCBIT_CNT_U08 | 1 | Counts | 2 |
| D_HALFFUNCBIT_CNT_U08 | 1 | Counts | 4 |
| D_PPPALOLMT_MTRNM_F32 | Single Precision Float | MtrNm | -0.1 |
| D_PPPAHILMT_MTRNM_F32 | Single Precision Float | MtrNm | 8.8 |


**Table 6**

| Constant Name |
| --- |
| D_ONE_ULS_F32 |
| D_ZERO_ULS_F32 |
| D_ZERO_CNT_U8 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | ArbiterSlewLimit | Type | Min | Max | UT Tolerance |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | TrqOvCmdRqst_HwNm_T_f32 | Float32 | -10 | 10 | N/A |
|  | SlewState_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | SlewRate_NmpS_T_f32 | Float32 | 0 | 2 | N/A |
|  | TrqOvCmdOut_HwNm_T_f32 | *Float32 | -10 | 10 | 3.05E-05 |
|  | SlewComplete_Cnt_T_lgc | *Boolean | FALSE | TRUE | N/A |
|  | CmdActive_Cnt_T_lgc | *Boolean | FALSE | TRUE | N/A |
|  | Slew_Uls_T_f32 | *Float32 | -10 | 10 | 3.05E-05 |
|  | PrevSlewState_Cnt_T_lgc | *Boolean | FALSE | TRUE | N/A |
| Return Value | None |  |  |  |  |


**Table 9**

| Function Name | ArbiterPriority | Type | Min | Max | UT Tolerance |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | VehSpd_Kph_T_f32 | Float32 | 0 | 511 | N/A |
|  | DSTCmdActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | PPPACmdActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | HaLFCmdActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | HaLFPriActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | PPPAPriActive_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | DSTPriActive_Cnt_T_lgc | boolean | FALSE | TRUE | N/A |
| Return Value | None |  |  |  |  |


**Table 10**

| Function Name | ArbiterRamping | Type | Min | Max | UT Tolerance |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | DSTEnable_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | DSTSlewComplete_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | HaLFEnable_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | HaLFSlewComplete_Cnt_T_lgc | Boolean | FALSE | TRUE | N/A |
|  | DSTScalar_Uls_T_f32 | Float32 | 0 | 1 | 3.05E-05 |
|  | HaLFScalar_Uls_T_f32 | Float32 | 0 | 1 | 3.05E-05 |
| Return Value | None |  |  |  |  |


**Table 11**

| Data | Value |
| --- | --- |
| Rte_InitValue_ActiveFunctionBits_Cnt_u08 | 0 |
| Rte_InitValue_DSTActive_Cnt_lgc | FALSE |
| Rte_InitValue_DSTSlewComplete_Cnt_lgc | FALSE |
| Rte_InitValue_DSTState_Cnt_u08 | 0 |
| Rte_InitValue_DSTTrqOvCmdRqst_HwNm_f32 | 0 |
| Rte_InitValue_HaLFActive_Cnt_lgc | FALSE |
| Rte_InitValue_HaLFSlewComplete_Cnt_lgc | FALSE |
| Rte_InitValue_HaLFTOState_Cnt_u08 | 0 |
| Rte_InitValue_HaLFTrqOvCmdRqst_MtrNm_f32 | 0 |
| Rte_InitValue_IpTrqOvr_HwNm_f32 | 0 |
| Rte_InitValue_OpTrqOvr_MtrNm_f32 | 0 |
| Rte_InitValue_PAReturnSclFct_Uls_f32 | 1 |
| Rte_InitValue_PATrqOvCmdRqst_HwNm_f32 | 0 |
| Rte_InitValue_PrkAssistState_Cnt_u08 | 0 |
| Rte_InitValue_PrkAsstSlewComplete_Cnt_lgc | FALSE |
| Rte_InitValue_VehicleSpeed_Kph_f32 | 0 |


**Table 12**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| ArbLmt_Per1 | 4 ms | ALL |


**Table 13**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 14**

| Name of Sub Module | Software Segment |
| --- | --- |
| ArbLmt_Per1 | RTE_START_SEC_AP_ARBLMT_APPL_CODE |


**Table 15**

| Name of Sub Module | Software Segment |
| --- | --- |
| ArbiterSlewLimit | N/A |
| ArbiterPriority | N/A |
| ArbiterRamping | N/A |


**Table 16**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version | 29-Oct-12 | OT |
| 2 | 2.0 | Anomaly 4668 | 22-Mar-13 | M. Story |
| 3 | 3.0 | Update to FDD ver 003 | 15-May-13 | Jared |
| 4 | 4.0 | UTP corrections | 30-May-13 | Jared |
| 5 | 5.0 | Updated to FDD ver 004 | 10-Jul-13 | SP |
|  |  |  |  |  |
