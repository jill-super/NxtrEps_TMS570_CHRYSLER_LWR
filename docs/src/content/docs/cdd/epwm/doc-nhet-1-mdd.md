---
title: "Nhet 1"
description: "Converted from Nhet_1_MDD.docx"
---

> **Source:** `ePWM/doc/Nhet_1_MDD.docx` (1,646,262 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module – NHET


# High-Level Description

This module implements NHET functionality with respect to the NHET module.


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

Memcpy


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module


### Global Functions #1 (For detailed info regarding values assigned to registers refer Reference Pdf attached below)


#### Description

**NHET**


## Local Functions/Macros Used by this MDD only


### Local Macro #1

None


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init:


#### Design Rationale

None


#### Module Outputs

None


#### Module Internal

None


#### Initialize NHET Direction Register


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


## Execution Rates for sub-modules called by the Subroutine

This table serves as reference for the Scheduler design


## Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

None


# Reference

Register Reference


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| HET_INIT1_PST | HET_INIT1_PST | None |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


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

| Function Name | NHET_Init1 | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | None |  |  |  |  |


**Table 9**

| Data | Value |
| --- | --- |
| None |  |


**Table 10**

| Global Function Name | Calling Frequency | Function in which the function is called |
| --- | --- | --- |
| NHET_Init1 | On Event | ECU start up |
|  |  |  |


**Table 11**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 12**

| Name of Sub Module | Software Segment |
| --- | --- |
| NHET_Init1 | #define NHET_START_SEC_CODE |
|  |  |


**Table 13**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 14**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version ( FDD 34B) |  | Selva |
