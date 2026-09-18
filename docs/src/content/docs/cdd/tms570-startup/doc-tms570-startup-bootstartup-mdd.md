---
title: "TMS570 Startup BootStartup"
description: "Converted from TMS570_Startup_BootStartup_MDD.docx"
---

> **Source:** `TMS570_Startup/doc/TMS570_Startup_BootStartup_MDD.docx` (120,511 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module  --


# High-Level Description

This module outlines the functionality of the system startup functions of the TMS570.  This code is intended to be run starting after the sys startup routine in the boot project.


# Figures


## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the module.

No Shared Data


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

<None>


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

(Note: For multiple init functions, insert new headers at the “Header 2” level – subset of “5.1 Initialization Functions” and follow the same sub-section design shown below)


### Init: BootStartup


#### Design Rationale

This function is designed to be called at the end of the sys_startup initialization routine.  Note that most of this initialization code (for initializing copy table, global variables, and constructors) was taken from Texas Instruments’ startup code example implementation.


#### Processing


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


# Execution Requirements


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

(Item #1)


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
|  |  |  |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| <None> |  |  |  |  |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | Value |
| --- | --- | --- |
|  |  |  |


**Table 4**

| Constant Name |
| --- |
| <None> |
|  |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
|  |  |  |  |


**Table 6**

| Constant Name |
| --- |
|  |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | (Exact name used) | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | (if none, write None) |  |  |  |  |
|  | (Insert more rows for additional passed arguments) |  |  |  |  |
| Return Value | (if no value returned, write N/A) |  |  |  |  |


**Table 9**

| Function Name | (Exact name used) | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | (if none, write None) |  |  |  |  |
|  | (Insert more rows for additional passed arguments) |  |  |  |  |
| Return Value | (if no value returned, write N/A) |  |  |  |  |


**Table 10**

| Data | Value |
| --- | --- |
| <None> |  |


**Table 11**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| BootStartup() | called by sys_startup initialization code | N/A |


**Table 12**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
| BootStartup() |  |


**Table 14**

| Name of Sub Module | Software Segment |
| --- | --- |
|  |  |


**Table 15**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1 | Initial creation | 05/14/12 | LWW |
