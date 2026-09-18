---
title: "Analog-to-Digital Converter Driver (Adc)"
description: "Converted from Adc_MDD.docx"
---

> **Source:** `Adc/doc/Adc_MDD.docx` (246,272 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module -- ADC


# High-Level Description

The ADC module shall control sampling and conversion of voltages from the hardware layer into digital signals. The ADC Register definition has been captured from the TMS570LS31x/21x 16/32-Bit RISC Flash Microcontroller Technical Reference Manual (SPNU499 – September 2011).


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

None


## Data Hiding Functions

<None>


## Global Functions/Macros Defined by this Module


### ADC Init

This function is used to initialize each of the ADC1 Groups (Event, Group1, and Group2).


#### Initialize Module Internal Variables

None


#### Register Configuration


### Setup Result Buffer

This function is the Adc group result buffer setup service. It is responsible for setting up the result buffer pointer of the group.

This Api is provided to support for the standard Autosar API, however the design of this driver does not buffer an intermediate copy of the results and therefore does not require a result buffer.  The hardware provides a sufficient Adc results buffer.

For optimization purposes, this function could be defined as a macro.


#### Setup Group’s Result Buffer

return E_OK


### Start Group Conversion

This function starts a software triggered conversion of all channels of the requested Adc channel group.

In order to provide optimized execution of this single line function, this API should be defined as a macro, however, due to timing it is at the moment defined as a function.  The need for minimal runtime is driven by a Nexteer use case which executes this in the context of the MtrCtrl ISR in some EPS systems.


#### Select Channels to Convert

adcREG1->GxSEL[Group] = T_Adc1GroupConfigData_Cnt_Str[Group].ChannelSelect


### Get Group Status

Returns the conversion status of the requested ADC1 channel group.


#### Get Status


### Read Group Conversions

Reads the group conversion result of the last completed conversion round of the requested group and

stores the channel values starting at the DataBufferPtr address. The group channel values are stored in ascending channel number order (in contrast to the storage layout of the result buffer if streaming access is configured).

Per the design direction in FDD33, direct ADC result buffer acces is used instead of using the hardware FIFO access register.


#### Read Group


## Local Functions/Macros Used by this MDD only


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

None


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


## Serial Communication Functions

None


## Transition Functions

None


# Execution Requirements


## Execution Sequence of the Module

Adc_Init should be called after SystemTime_Init due to the use of the uS System Time.

Adc_Init should be called prior to IoHwAb_Init to ensure registers are configured prior to triggering initial conversions.


## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

INLINE functions defined in “GlobalMacro.h” are not unit tested


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs |
| --- | --- |
| None | None |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| Adc_GroupType | N/A | uint8 | 0 | 2 |
| Adc_GroupConfigDataType | uint8 NumOfChannels, uint32 ChannelSelect, uint32* ResultBuf | struct | FULL | FULL |
| Adc_StatusType | ADC_IDLE, ADC_BUSY, ADC_COMPLETED, ADC_STREAM_COMPLETED | enum | 0 | 3 |
| Adc_ValueGroupType | N/A | uint16 | 0 | 4095 |
| Adc_ValueGroupType | N/A | uint16* | FULL | FULL |


**Table 4**

| Constant Name |
| --- |
| k_VbattOVTransIntConfig_Cnt_u32 |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_NUMOFGROUPS_CNT_U8 | 1 | Counts | 3 |
| D_GROUPEV_CNT_U8 | 1 | Counts | 0 |
| D_GROUP1_CNT_U8 | 1 | Counts | 1 |
| D_GROUP2_CNT_U8 | 1 | Counts | 2 |
| D_NUMOFADCCALREADS_CNT_U8 | 1 | Counts | 8 |
| D_NTCPARMBIT0_CNT_U8 | 1 | Counts | 1 |
| D_NTCPARMBIT1_CNT_U8 | 1 | Counts | 2 |
| D_NTCPARMBIT2_CNT_U8 | 1 | Counts | 4 |
| D_ADC1RSLTBASEADR_CNT_U32 | 1 | Counts | 0xFF3E0000U |
| D_ADC1NUMRSLTBUF_CNT_U08 | 1 | Counts | 64 |
|  |  |  |  |
| D_ADC1MAGINTMASK1_CNT_U16 | 1 | Counts | 0/0 |
| D_ADC1MAGINTASET_CNT_U16 | 1 | Counts | 1/0 |
| D_ADC1MAGINTCR1_CNT_U32 | 1 | Counts | k_VbattOVTransIntConfig_Cnt_u32/ 0 |
| D_ADC1THRINTENACLR_CNT_U16 | 1 | Counts | 6/7 |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |


**Table 6**

| Constant Name |
| --- |
| T_Adc1GroupConfigData_Cnt_Str[D_NUMOFGROUPS_CNT_U8] |
|  |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | Adc_Init_FixedCfg ( macro aliased is Adc_Init(x) ) | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None | N/A | N/A | N/A |  |
| Return Value | N/A |  |  |  |  |


**Table 9**

| Function Name | Adc_SetupResultBuffer | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Group | Adc_GroupType | 0 | 2 |  |
|  | DataBufferPtr | Adc_ValueGroupRefType | FULL | FULL |  |
| Return Value | N/A | Std_ReturnType | 0 | 0 | 0 |


**Table 10**

| Function Name | Adc_StartGroupConversion | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Group | Adc_GroupType | 0 | 2 |  |
|  | DataBufferPtr | Adc_ValueGroupRefType | FULL | FULL |  |
| Return Value | N/A | Std_ReturnType | 0 | 0 | 0 |


**Table 11**

| Function Name | Adc_GetGroupStatus | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Group | Adc_GroupType | 0 | 2 |  |
| Return Value | ReturnVal_Cnt_T_Enum | Adc_StatusType | 0 | 3 | 0 |


**Table 12**

| Function Name | Adc_ReadGroup | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | Group | Adc_GroupType | 0 | 2 |  |
| Return Value | ReturnVal_Cnt_T_Enum | Adc_StatusType | 0 | 3 | 0 |


**Table 13**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| Adc_Init | Once (at initialization) | STARTUP |


**Table 14**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| N/A |  |


**Table 15**

| Name of Sub Module | Software Segment |
| --- | --- |
| Adc_Init | ADC_START_SEC_CODE |
| Adc_SetupResultBuffer | ADC_START_SEC_CODE |
| Adc_StartGroupConversion | ADC_START_SEC_CODE |
| Adc_ReadGroup | ADC_START_SEC_CODE |
| Adc_GetGroupStatus | ADC_START_SEC_CODE |
| ADCOffsetCalibration | ADC_START_SEC_CODE |


**Table 16**

| Name of Sub Module | Software Segment |
| --- | --- |
|  |  |


**Table 17**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial version based on FDD 33C rev 006 | 05Nov12 | LN |
| 2 | 2 | Constant confiuguration tables renamed to start with “T_” Rewored Adc_ReadGroup to provide direct fixed memory access as required in the FDD | 15Jan13 | JJW |
| 3 | 3 | Updated FDD 33C rev 007 and FDD33E rev2 | 25-April-13 | Selva |
