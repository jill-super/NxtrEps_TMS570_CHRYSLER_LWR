---
title: "Motor Position 3"
description: "Converted from Motor_Position_3_MDD.docx"
---

> **Source:** `MtrPos/doc/Motor_Position_3_MDD.docx` (359,525 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module – Motor Position 3


# High-Level Description

This module implements the systematic coverage for MtrPos.  This includes calculating an alternate MechMtrPos signal and performing diagnostics.


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

Abs_f32_m

DiagPStep_m

DiagNStep_m

DiagFailed_m


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

None


## Periodic Functions


### Per: MtrPos3_Per1


#### Design Rationale

This function should be run after MtrPos2_Per1, as the comparisons (in both the main and diverse paths) on the generated signals assume that this order will be followed.


#### Program Flow Start

Rte_Call_MtrPos3_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

InvCos2_Volts_T_f32 = Rte_IRead_MtrPos3_Per1_InvCos2Scaled_Volt_f32()

InvSin2_Volts_T_f32 = Rte_IRead_MtrPos3_Per1_InvSin2Scaled_Volt_f32()


#### Compute Alternate Motor Position


#### Store Local copy of outputs into Module Outputs


#### Program Flow End

Rte_Call_MtrPos3_Per1_CP1_CheckpointReached()


### Per: MtrPos3_Per2


#### Design Rationale

None


#### Program Flow Start

Rte_Call_MtrPos3_Per2_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

InvCos2_Volts_T_f32 = Rte_IRead_MtrPos3_Per2_InvCos2Scaled_Volt_f32()

InvSin2_Volts_T_f32 = Rte_IRead_MtrPos3_Per2_InvSin2Scaled_Volt_f32()


#### Correlation Diagnostic


#### Secondary Sensor Validity Diagnostic


#### Store Local copy of outputs into Module Outputs

MtrPos3_SysCErrorTerm_Rev_D_f32 = SysCErrorTerm_Rev_T_f32

MtrPos3_SysCValidErr_VoltsSqrd_D_f32 = SysCValidErr_VoltsSqrd_T_f32


#### Program Flow End

Rte_Call_MtrPos3_Per2_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


## Serial Communication Functions

None


# Execution Requirements


## Execution Sequence of the Module

See section 6.3.1.1 for details on task organization.


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
| InvSin2Scaled_Volt_f32 | InvSin2Scaled_Volt_f32 |  |
| InvCos2Scaled_Volt_f32 | InvCos2Scaled_Volt_f32 |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| MtrPos3_SysCValidityFltAcc_Cnt_M_u16 | 1 | FULL | FULL | MTRPOS3_START_SEC_VAR_CLEARED_16 |
| MtrPos3_SysCCorrFltAcc_Cnt_M_u16 | 1 | FULL | FULL | MTRPOS3_START_SEC_VAR_CLEARED_16 |
| MtrPos3_DiagCorrectedMtrPos_Rev_M_f32 | Single Precision Float | 0 | 1 | MTRPOS3_START_SEC_VAR_CLEARED_32 |
| MtrPos3_DiagMechMtrPos_Rev_M_f32 | Single Precision Float | 0 | 1 | MTRPOS3_START_SEC_VAR_CLEARED_32 |
| MtrPos3_SysCErrorTerm_Rev_D_f32 | Single Precision Float | 0 | 1 | MTRPOS3_START_SEC_VAR_CLEARED_32 |
| MtrPos3_SysCValidErr_VoltsSqrd_D_f32 | Single Precision Float | 0 | 6.25 | MTRPOS3_START_SEC_VAR_CLEARED_32 |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| TaylorATanTblType | offset_f32 slope_s08 SinMinVal_lgc | float32 sint8 boolean | 0 -1 FALSE | 2π 1 TRUE |


**Table 4**

| Constant Name |
| --- |
| k_NominalOffset_Volts_f32 |
| k_CorrelationError_Rev_f32 |
| k_MtrPosCorrDiag_Cnt_str |
| k_SysCValMinError_VoltsSqrd_f32 |
| k_SysCValMaxError_VoltsSqrd_f32 |
| k_SysCMtrPosValDiag_Cnt_str |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| NUMOCTANTS_CNT_u16 | 1 | Counts | 8 |
| D_HALF_ULS_F32 | Single Precision Float | Unitless | 0.5 |
| D_THREE_ULS_F32 | Single Precision Float | Unitless | 3 |
| D_ELECREVPMECHREV_ULS_U16 | 1 | Unitless | 3 |
| D_MASK16BITS_CNT_U32 | 1 | Counts | 0x0000FFFFUL |


**Table 6**

| Constant Name |
| --- |
| D_ZERO_ULS_F32 |
| D_PI_ULS_F32 |
| D_2PI_ULS_F32 |
| D_ONE_ULS_F32 |
| D_ZERO_CNT_U16 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| TaylorATanTbl[NUMOCTANTS_CNT_u16] | TaylorATanTblType | {0, 1, TRUE}, { π/2, -1, FALSE}, { π/2, 1, FALSE}, { π, -1, TRUE}, { π, 1, TRUE}, {3 π/2, -1, FALSE}, {3 π/2, 1, FALSE}, {2 π, -1, TRUE} | MTRPOS3_START_SEC_CONST_UNSPECIFIED |


**Table 8**

| Data | Value |
| --- | --- |
| Rte_InitValue_InvCos2Scaled_Volt_f32 | 0 |
| Rte_InitValue_InvSin2Scaled_Volt_f32 | 0 |


**Table 9**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| MtrPos3_Per1 | 2 ms | ALL |
| MtrPos3_Per2 | 4 ms | ALL |


**Table 10**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 11**

| Name of Sub Module | Software Segment |
| --- | --- |
| MtrPos3_Per1 | RTE_START_SEC_SA_MTRPOS3_APPL_CODE |
| MtrPos3_Per2 | RTE_START_SEC_SA_MTRPOS3_APPL_CODE |


**Table 12**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 13**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version | 23-Oct-12 | OT |
| 2 | 2.0 | MDD catchup matching SRC ver 4 | 14-June-13 | NRAR |
|  |  |  |  |  |
