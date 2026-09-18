---
title: "ePWM 2"
description: "Converted from ePWM_2_MDD.docx"
---

> **Source:** `ePWM/doc/ePWM_2_MDD.docx` (74,439 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module implements the shutdown mechanisms functionality with respect to the EPWM module.  This module implements the requirements specific to the EPWM output direction control, which is implemented in the diverse path as required.


# Figures


## Component Diagram


# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.


## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.


### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

(Refer the included ref for more details of register)


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

ePWM_EnableOutputs

ePWM_DisableOutputs


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module


### Local Macro

None


## Local Functions/Macros Used by this MDD only

None


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: _Init1


#### Design Rationale

None


#### Module Outputs

None


#### Module Internal

None


#### Initialize EPWM Direction Register


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


### Trns: _Trns1


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Set EPWM Direction Register to Output


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

N/A


### Trns: _Trns2


#### Design Rationale

None


#### Program Flow Start

N/A


#### Store Module Inputs to Local copies

None


#### Set EPWM Direction Register to Input


#### Store Local copy of outputs into Module Outputs

None


#### Program Flow End

N/A


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

None


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| None | None | None |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |


**Table 4**

| Constant Name |
| --- |
| None |


**Table 5**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |


**Table 6**

| Constant Name |
| --- |
| None |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Data | Value |
| --- | --- |
| None |  |


**Table 9**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| ePWM2_Trns1 | On Event | On Entering |
| ePWM2_Trns2 | On Event | On |


**Table 10**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 11**

| Name of Sub Module | Software Segment |
| --- | --- |
| ePWM2_Trns1 | RTE_START_SEC_AP_EPWM2_APPL_CODE |
| ePWM2_Trns2 | RTE_START_SEC_AP_EPWM2_APPL_CODE |


**Table 12**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 13**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1.0 | Initial Version (Shutdown Mechs FDD 34B) | 18-Feb-13 | Selva |
|  |  |  |  |
