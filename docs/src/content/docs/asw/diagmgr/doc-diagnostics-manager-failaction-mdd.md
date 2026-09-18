---
title: "Diagnostics Manager FailAction"
description: "Converted from Diagnostics_Manager_FailAction_MDD.docx"
---

> **Source:** `DiagMgr/doc/Diagnostics_Manager_FailAction_MDD.docx` (151,203 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module --  Fail Action


# High-Level Description


# Figures


## Component Diagram


# Variable Data Dictionary


## Module Internal Variables


### User defined typedef definition/declaration


# Constant Data Dictionary


## Calibration Constants


## Program(fixed) Constants


### Embedded Constants


#### Local


#### Global


### Module specific Lookup Tables Constants


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

TableSize_m()


## Data Hiding Functions

<None>


## Global Functions/Macros Defined by this Module


### Diagnostic Manager Periodic 1


#### Description


## Local Functions/Macros Used by this MDD only


### Read Bits


#### Description

IF  (Data & BitMask) = 0

Return (FALSE)

ELSE
	Return(TRUE)

END IF


# Software Module Implementation


## Runtime Environment (RTE) Initial Values


## Initialization Functions

None


## Periodic Functions

None


## Fault Recovery Functions

None


## Shutdown Functions

None


## Interrupt Functions

None


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


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Global and Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

(Item #1)


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
|  |  | DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |
|  |  | DiagStsCtrldDisRmpPres_Cnt_lgc |
|  |  | DiagStsRecRmpToZeroFltPres_Cnt_lgc |
|  |  | DiagStsHWASbSystmFltPres_Cnt_lgc |
|  |  | DiagStsDefVehSpd_Cnt_lgc |
|  |  | DiagStsDefTemp_Cnt_lgc |
|  |  | DiagStsScomHWANotValid_Cnt_lgc |
|  |  | DiagStsWIRDisable_Cnt_lgc |
|  |  | DiagRampRate_XpmS_f32 |
|  |  | DiagRampValue_Uls_f32 |
|  |  | DiagRmpToZeroActive_Cnt_lgc |


**Table 2**

| Variable Name | Datatype | Resolution | Legal Range (min) | Legal Range (max) | Software Segment {Data Type} |
| --- | --- | --- | --- | --- | --- |
| DiagSts#_Cnt_M_b16[2] |  |  |  |  |  |
|  |  |  |  |  |  |
| ActiveRmpRate_UlspmS_M_f32[2] |  |  |  |  |  |
|  |  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
|  |
|  |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
|  |  |  |  |


**Table 6**

| Constant Name |
| --- |
| DIAGMGR_NUMAPPS |
| D_DIAGSTSNONRECRMPTOZEROBIT_CNT_B16 |
| D_DIAGSTSRECRMPTOZEROBIT_CNT_B16 |
| D_DIAGSTSCTRLDDISRMPBIT_CNT_B16 |
| D_DIAGSTSHWASBSYSTMFLTBIT_CNT_B16 |
| D_DIAGSTSDEFVEHSPDBIT_CNT_B16 |
| D_DIAGSTSDEFTEMPBIT_CNT_B16 |
| D_DIAGSTSSCOMHWANOTVALIDBIT_CNT_B16 |
| D_DIAGSTSWIRDISABLEBIT_CNT_B16 |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| T_DiagMgrDiagSts_Ptr_b16[] | N/A |  | AP_DIAGMGR_CONST |
| T_DiagMgrRmpRate_Ptr_f32[] | N/A |  | AP_DIAGMGR_CONST |
|  |  |  |  |


**Table 8**

| Function Name | DiagMgr_Per1 | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | none |  |  |  |
| Return Value | none |  |  |  |


**Table 9**

| Function Name | ReadBit_u16 | Type | Min | Max |
| --- | --- | --- | --- | --- |
| Arguments Passed | Data | Uint16 | 0 | FULL |
|  | BitMask | Uint16 | 0 | FULL |
| Return Value |  | Boolean | FALSE | TRUE |


**Table 10**

| Data | Value |
| --- | --- |
|  |  |


**Table 11**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
|  |  |  |


**Table 12**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
|  |  |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
|  |  |


**Table 14**

| Name of Sub Module | Software Segment |
| --- | --- |
| DiagMgr_Per1 | AP_DIAGMGR_CODE |
| ReadBit_u16 | AP_DIAGMGR_CODE |


**Table 15**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1 | Initial MDD version | 14-Feb-13 | VK |
|  |  |  |  |
