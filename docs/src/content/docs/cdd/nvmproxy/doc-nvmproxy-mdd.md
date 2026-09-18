---
title: "Non-Volatile Memory Proxy (NvMProxy)"
description: "Converted from NvMProxy_MDD.docx"
---

> **Source:** `NvMProxy/doc/NvMProxy_MDD.docx` (753,913 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module  -- NvM Proxy


# High-Level Description

(Description must be within 8-10 lines.)


# Figures


## Diagram – Function Data Sharing

This diagram depicts the physical memory allocation for the various parts of the NvM Proxy system. 3 application RAM areas are shown for illustrative purposes, however, this module can handle any number of application RAM areas.

The memory stack components below the NvM are not shown in this diagram to promote clarity.

The NvMProxy_CmdQueue is required to be allocated to global shared memory to provide write access to the Proxy server function that is designed to be called from any application.


### Diagram – NvM Data Initialization

Depiction of the Nv Data initialization sequence from the perspective of which application is active (i.e. MPU configuration at the time of operation execution)

Only pertinent initialization functions and steps are shown to promote clarity.


### Diagram – NvM Runtime

Following is a depiction of the write Motor Position EOL calibrations via diagnostic service request.  The MtrPos component is assumed to be running in the ASIL D application and its server runnable for processing an EOL motor cal write request is assumed to invoke the NvM_WriteBlock operation.

The lifelines in this diagram represent execution within the Os or an application.  The details of the diagnostic service request are omitted from this diagram for clarity purposes.


# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.


## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.


### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.


# Constant Data Dictionary


## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.


## Configuration Constants

This section lists the configuration constants used by the module.  For details on configuration constants, refer to the Module User Guide.  The values are set by the integration project specific configuration files Cd_NvMProxy_Cfg.h and Cd_NvMProxy_PBcfg.c


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


## Data Hiding Functions

NvM_WriteAll()

NvM_WriteBlock()

NvM_SetRamBlockStatus()

NvM_GetErrorStatus()

SchM_Enter_NvMProxy()

SchM_Exit_NvMProxy()


## Global Functions/Macros Defined by this Module


### NvMProxy_WriteAll


#### Description

This function implements the AUTOSAR standard API for the NvM BSW WriteAll service.  The interface must adhere to the AUTOSAR standard to allow mapping service port needs of SWC’s located in outside the QM application to this component’s service interface via the Rte.


### NvMProxy_WriteBlock


#### Description

This function implements the AUTOSAR standard API for the NvM BSW WriteBlock service.  The interface must adhere to the AUTOSAR standard to allow mapping service port needs of SWC’s located in outside the QM application to this component’s service interface via the Rte.


### NvMProxy_GetErrorStatus


#### Description

This function implements the AUTOSAR standard API for the NvM BSW GetErrorStatus service.  The interface must adhere to the AUTOSAR standard to allow mapping service port needs of SWC’s located in outside the QM application to this component’s service interface via the Rte.


### NvMProxy_SetRamBlockStatus


#### Description

This function implements the AUTOSAR standard API for the NvM BSW SetRamBlockStatus service.  The interface must adhere to the AUTOSAR standard to allow mapping service port needs of SWC’s located in outside the QM application to this component’s service interface via the Rte.


## Local Functions/Macros Used by this MDD only


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: NvMProxy_Init


#### Design Rationale

Transfer the data from the unsecured Nv Data memory buffer to the secured Nv Data memory buffer and initialize the block status shadow to the values returned by the NvM API.


#### Module Outputs


#### Module Internal

NvMPWriteRqst_Cnt_M_Str = 0*

NvMPSetRBSRqst_Cnt_M_Str = 0*

** Cleared by memory **clear function and not** explicitly **cleared **in **this **init function*


## Periodic Functions


### Per: NvMProxy_MainFunction


#### Design Rationale

This function is responsible for forwarding the queued NvM requests to the NvM driver in a SchM task running the NvM BSW.

This function copies the secured data area to the unsecured data area


#### Program Flow Start

None


#### Store Module Inputs to Local copies

None


#### Processing of function


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

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

NvMProxy_Init must be scheduled after to NvM_ReadAll is completed.  Additionaly NvMProxy_Init must be executed as a trusted function to grant rights for initializing the secured memory.  This would typically be accomplished via an Os trusted function call API.

NvMProxy_MainFunction should be scheduled prior to NvM_MainFunction.  This provides the minimal amount of lag in forwarding and processing NvM service requests.


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| Configured by NvMProxyCfg | Configured by NvMProxyCfg | None |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| NvMPWriteRqst_Cnt_M_Str[D_NUMPRXYBLOCKS_CNT_U16] | See NvMPWriteBuff_Type | See NvMPWriteBuff_Type | See NvMPWriteBuff_Type | NVMPROXY_START_SEC_VAR_CLEARED_UNSPECIFIED |
| NvMPSetRBSRqst_Cnt_M_Str[D_NUMPRXYBLOCKS_CNT_U16] | See NvMPSetRBSBuff_Type | See NvMPSetRBSBuff_Type | See NvMPSetRBSBuff_Type | NVMPROXY_START_SEC_VAR_CLEARED_UNSPECIFIED |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| NvMProxyCfg_Type | NvMBlock | NvM_BlockIdType | 0 | FULL |
|  | unsecurePtr | constant uint8* to data | NA | NA |
|  | securePtr | constant uint8* to variable data | NA | NA |
|  | secureSize | uint16 | 0 | FULL |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
| NvMPWriteBuff_Type | Pend | boolean | 0 | FULL |
|  | BlkStatus | NvM_RequestResultType | 0 | FULL |
|  | SrcPtr | uint8* | NA | NA |
| NvMPSetRBSBuff_Type | Pend | boolean | 0 | FULL |
|  | BlockChanged | boolean | NA | NA |


**Table 4**

| Constant Name |
| --- |
| <None> |
|  |


**Table 5**

| Constant Name | Type |
| --- | --- |
| NvMProxyCfg [D_NUMPRXYBLOCKS_CNT_U16] | NvMProxyCfg_Type |


**Table 6**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_NUMPRXYBLOCKS_CNT_U16 | 1 | Count | Configured in integration project |
| NVMPROXY_EXCLUSIVE_AREA_0 | NA | NA | Generated by SchM |
|  |  |  |  |


**Table 7**

| Constant Name |
| --- |
| <None> |
|  |


**Table 8**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 9**

| Function Name | NvMProxy_WriteAll | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
| Return Value | N one |  |  |  |  |


**Table 10**

| Function Name | NvMProxy_WriteBlock | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Block | NvM_BlockIdType |  |  |  |
|  | SrcPtr | uint8 |  |  |  |
| Return Value | result | Std_ReturnType |  |  |  |


**Table 11**

| Function Name | NvMProxy_GetErrorStatus | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Block | NvM_BlockIdType |  |  |  |
|  | RequestResultPtr | uint8* |  |  |  |
| Return Value | N one |  |  |  |  |


**Table 12**

| Function Name | NvMProxy_SetRamBlockStatus | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Block | NvM_BlockIdType |  |  |  |
|  | BlockChanged | boolean |  |  |  |
| Return Value | N one |  |  |  |  |


**Table 13**

| Data | Value |
| --- | --- |
| <None> |  |


**Table 14**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| NvMProxy_Init | Once during startup | COLD INIT |
| NvMProxy_MainFunction | Same as NvM_MainFunction | Same as NvM_MainFunction |


**Table 15**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |


**Table 16**

| Name of Sub Module | Software Segment |
| --- | --- |
| NvMProxy_Init | NVMPROXY_START_SEC_CODE |
| NvMProxy_MainFunction | NVMPROXY_START_SEC_CODE |
| NvMProxy_WriteAll | NVMPROXY_START_SEC_CODE |
| NvMProxy_WriteBlock | NVMPROXY_START_SEC_CODE |
| NvMProxy_SetRamBlockStatus | NVMPROXY_START_SEC_CODE |
| NvMProxy_GetErrorStatus | NVMPROXY_START_SEC_CODE |


**Table 17**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 18**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 |  | Initial creation | 21-Mar-12 | JJW |
| 2 |  | Corrected anomaly 4437 in NvMProxy init routine | 01-Mar-13 | KJS |
| 3 |  |  | 30-May-13 | JJW |
|  |  |  |  |  |
