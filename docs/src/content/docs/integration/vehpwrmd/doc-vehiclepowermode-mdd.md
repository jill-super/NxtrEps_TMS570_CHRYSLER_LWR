---
title: "VehiclePowerMode"
description: "Converted from VehiclePowerMode_MDD.docx"
---

> **Source:** `Chrysler_LWR_EPS_TMS570/SwProject/VehPwrMd/doc/VehiclePowerMode_MDD.docx` (145,275 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module  -- VehiclePwrMode


# High-Level Description

This module determines the vehicle level power moding signal for the EPS system


# Figures


## Diagram – Function Data Sharing


### Diagram – Function (Name)


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

<None>


## Data Hiding Functions

Rte_Call_EpsEn_OP_GET


## Global Functions/Macros Defined by this Module


### Global Function #1


#### Description

(Place flowchart/design for local function)


## Local Functions/Macros Used by this MDD only


### Local Function #1


#### Description

(Place flowchart/design for local function)


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: _Init1


#### Design Rationale


#### Module Outputs

Rte_IWrite_VehPwrMd_Init1_OperRampRate_XpmS_f32(k_RampDnRt_UlspmS_f32)

Rte_IWrite_VehPwrMd_Init1_OperRampValue_Uls_f32(D_ZERO_ULS_F32)


#### Module Internal

(Initialize all module internal variables in this section)


## Periodic Functions


### Per: _Per1


#### Design Rationale

There are a set of inputs that are read in but not used.  This is because these inputs are likely to be used in the final design.  The current implementation does not meet final design requirements.


#### Program Flow Start


#### Rte_Call_VehPwrMd_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

*EngONSrlComSvcDft_Cnt_T_lgc** *= Rte_IRead_VehPwrMd_Per1_EngONSrlComSvcDft_Cnt_lgc()

Rte_Call_EpsEn_OP_GET(&*EPSEn_Cnt_T_lgc*)

*EngRPM_Cnt_T_u16 = Rte_IRe**ad_VehPwrMd_Per1_EngRPM_Cnt_**u16()*

*VehSpdValid_Cnt_T_lgc** *= Rte_IRead_VehPwrMd_Per1_VehSpdValid_Cnt_lgc()

*VehSpd_Kph_T_f32 = *Rte_IRead_VehPwrMd_Per1_VehSpd_Kph_f32()

*EssEngStop_Cnt_T_lgc** = Rte_IRead_VehPwrMd_Per1_EssEngStop_Cnt_**lgc()*

*SpStPrsnt_Cnt_T_lgc** = Rte_IRead_VehPwrMd_Per1_SpStPrsnt_Cnt_**lgc()*

*NmState_Cnt_T_u8 = **NmGetStatus**()*


#### Processing


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_VehPwrMd_Per1_OperRampRate_XpmS_f32(*OperRampRate_XpmS_T_f32*)

Rte_IWrite_VehPwrMd_Per1_OperRampValue_Uls_f32(*OperRampValue_Uls_T_f32*)

Rte_IWrite_VehPwrMd_Per1_ATermActive_Cnt_lgc(*ATermActive_Cnt_T_lgc*)

Rte_IWrite_VehPwrMd_Per1_CTermActive_Cnt_lgc(*CTermActive_Cnt_**M**_lgc*)


#### Program Flow End

Rte_Call_VehPwrMd_Per1_CP1_CheckpointReached()


## Fault Recovery Functions


## Shutdown Functions


## Interrupt Functions


## Serial Communication Functions


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

Inline functions defined in GlobalMacro.h are not unit tested


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| EngRPM_Cnt_u16 | EngRPM_Cnt_u16 | ATermActive_Cnt_lgc |
| EngONSrlComSvcDft_Cnt_lgc | EngONSrlComSvcDft_Cnt_lgc | CTermActive_Cnt_lgc |
| VehSpd_Kph_f32 | VehSpd_Kph_f32 | OperRampRate_XpmS_f32 |
| VehSpdValid_Cnt_lgc | VehSpdValid_Cnt_lgc | OperRampValue_Uls_f32 |
| EssEngStop_Cnt_lgc | EssEngStop_Cnt_lgc |  |
| SpStPrsnt_Cnt_T_lgc | SpStPrsnt_Cnt_T_lgc |  |
| DefaultVehSpd | DefaultVehSpd |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| CTermActive_Cnt_M_lgc | 1 | FALSE | TRUE | VEHPWRMD_START_SEC_VAR_CLEARED_BOOLEAN |
|  |  |  |  |  |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| k_RampDnRt_UlspmS_f32 |
| k_RampUpRtLoSpd_UlspmS_f32 |
| k_VehSpdAstLmt_Kph_f32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_ENGONRPM_CNT_U16 | 1 | RPM | 300 |
| D_ENGRPMINVLD_CNT_U16 | 1 | Counts | 0xFFFF |
|  |  |  |  |


**Table 6**

| Constant Name |
| --- |
| D_ZERO_ULS_F32 |
| D_ONE_ULS_F32 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | N/A | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | (if none, write None) |  |  |  |
|  | (Insert more rows for additional passed arguments) |  |  |  |
| Return Value | (if no value returned, write N/A) |  |  |  |


**Table 9**

| Function Name | N/A | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | (if none, write None) |  |  |  |
|  | (Insert more rows for additional passed arguments) |  |  |  |
| Return Value | (if no value returned, write N/A) |  |  |  |


**Table 10**

| Data | Value |
| --- | --- |
| ATermActive_Cnt_lgc | TRUE |
| CTermActive_Cnt_lgc | FALSE |
| EngRPM_Cnt_u16 | 0 |
| EngONSrlComSvcDft_Cnt_lgc | FALSE |
| VehSpd_Kph_f32 | 0 |
| VehSpdValid_Cnt_lgc | FALSE |
| OperRampRate_XpmS_f32 | 0 |
| OperRampValue_Uls_f21 | 0 |


**Table 11**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| VehPwrMd_Init1 | Executed once after the RTE is started | COLDINIT |
| VehPwrMd_Per1 | 2ms | ALL |


**Table 12**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
| VehPwrMd_Init1 |  |
| VehPwrMd_Per1 |  |


**Table 14**

| Name of Sub Module | Software Segment |
| --- | --- |
|  |  |


**Table 15**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1.0 | Initial MDD | 23May11 | LWW |
| 2.0 | Initial Chrysler version for VehPwrMode | 31JUL12 | SAH |
| 3.0 | Update per SER Rev 2B | 3JAN13 | BWL |
| 4.0 | Updated per SER Rev 2G and anomaly 4761 | 12Apr13 | M. Story |
| 5.0 | Add TWaitBusSleep check for shutdown | 21Jun13 | M. Story |
| 6.0 | Anomaly 5586 NetWork management changes | 02OCT13 | M. Story |
| 7.0 | Anomaly 5911 NM changes | 31OCT13 | M. Story |
| 9 | Updated for L version 02.00.00 and WR 01.0.04 | 20NOV13 | M. Story |
| 10 | Anomaly 6131 Cterm changes | 05DEC13 | M. Story |
|  |  |  |  |
