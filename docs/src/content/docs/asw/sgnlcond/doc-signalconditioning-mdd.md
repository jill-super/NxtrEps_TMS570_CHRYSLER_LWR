---
title: "SignalConditioning"
description: "Converted from SignalConditioning_MDD.docx"
---

> **Source:** `SgnlCond/doc/SignalConditioning_MDD.docx` (386,376 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module – Signal Conditioning


# High-Level Description

This function conditions a signal received from SER prior to its distribution to other functions. Typical conditioning methods may include filters, slew rates, gain values or limits.


# Figures


## Diagram – Function Data Sharing


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


## Lookup Table Definitions


# Software Module Implementation


## Initialization Functions

None


## Periodic Functions


### Per: SignlCondn _Per1


#### Design Rationale

NOTE: For “starttime” calculations there is tendency for underflow and this is expected in s/w design. So for unittesting, VBA model should be implemented

such that it handles underflow and behaves like source code design.


#### Program Flow Start


#### Rte_Call_SignlCondn_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

SrlComVehSpd_Kph_T_f32 = RteRte_IRead_SignlCondn_Per1_SrlComVehSpeed_Kph_f32


#### Signal Conditioning


#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_SignlCondn_Per1_VehicleSpeed_Kph_f32 (CurrSrlComVehSpd_Kph_M_f32)


#### Program Flow End

Rte_Call_SignlCondn_Per1_CP1_CheckpointReached()


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


## Serial Communication Functions


# Requirements


## Execution Sequence of the Module


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

INLINE functions defined in globalmacro.h are not unit tested


# Revision Control Log


**Table 1**

| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |
| --- | --- |
| SrlComVehSpd_Kph_f32 | VehSpd_Kph_f32 |
|  |  |


**Table 2**

| Variable Name | Resolution | (min) | (max) | Software Segment |
| --- | --- | --- | --- | --- |
| CurrSrlComVehSpd_Kph_M_f32 | Single precision floating point | 0 | 350 | SIGNLCONDN_START_SEC_VAR_NOINIT_32 |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | (min) | (max) |
| --- | --- | --- | --- | --- |


**Table 4**

| Constant Name |
| --- |
| k_VehSpdSlewRate_KphpSec_f32 |
|  |


**Table 5**

| Constant Name | Resolution | Value |
| --- | --- | --- |
|  |  |  |


**Table 6**

| Constant Name |
| --- |
| D_2MS_SEC_F32 |
| BC_SIGNLCONDN_FAULTINJECTIONPOINT |
| FLTINJ_SRLCOMVEHSPD_SGNLCOND |
|  |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | Calling Frequency | in which the function is called |
| --- | --- | --- |
| SignlCondn_Per1 | 2 ms | ALL States |
|  |  |  |


**Table 9**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 10**

| Name of Sub Module | Software Segment |
| --- | --- |
| SignlCondn_Per1 |  |
|  |  |


**Table 11**

| Name of Sub Module | Software Segment |
| --- | --- |


**Table 12**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial release | 14-May-12 | NRAR |
| 2 | 2.0 | Updated as per FDDVer002, FaultInjectionPoint added to SrlComVehSpeed signal | 20-Aug-12 | NRAR |
| 3 | 3.0 | Corrected Fault Injection function call | 05-Sep-12 | NRAR |
| 4 | 4.0 | Added checkpoints and memmap software segment is updated for static variables | 25-Sep-12 | Selva |
|  |  |  |  |  |
