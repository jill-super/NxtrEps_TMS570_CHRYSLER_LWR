---
title: "ePWM 1"
description: "Converted from ePWM_1_MDD.docx"
---

> **Source:** `ePWM/doc/ePWM_1_MDD.docx` (2,344,414 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module –


# High-Level Description

This module implements functionality with respect to the EPWM module.  This module implements the requirements other than the EPWM output direction control, which is implemented in the diverse path as required.


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

None


## Data Hiding Functions

None


## Global Functions/Macros Defined by this Module


### Global Functions #1 (For detailed info regarding values assigned to registers refer Reference Pdf attached below)


#### Description

**EPWM1**

**EPWM2**

**EPWM3**

**EPWM4**

**EPWM7**


### Global Functions #2


#### Description

For detailed info regarding values assigned to registers refer Reference Pdf attached below


## Local Functions/Macros Used by this MDD only


### Local Macro #1


#### Description

Disables the EPWM registers (Refer the included register reference for more details of register)

ePWM1->AQCSFRC = 5U

ePWM1->DBCTL &= 0xFFFFFFFCU

ePWM2->AQCSFRC = 5U

ePWM2->DBCTL &= 0xFFFFFFFCU

ePWM3->AQCSFRC = 5U

ePWM3->DBCTL &= 0xFFFFFFFCU


### Local Macro #2


#### Description

Enables the EPWM registers (Refer the included register reference for more details of register)

ePWM1->AQCSFRC = 0U;

ePWM1->DBCTL |= 3U;

ePWM2->AQCSFRC = 0U;

ePWM2->DBCTL |= 3U;

ePWM3->AQCSFRC = 0U;

ePWM3->DBCTL |= 3U;


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
| CDD_PWMPeriod_Cnt_G_u16 | CDD_PWMPeriod_Cnt_G_u16 | None |
| CDD_DCPhsComp_Cnt_G_u16[3] | CDD_DCPhsComp_Cnt_G_u16[3] |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | User Defined Type | Legal Range (min) | Legal Range (max) |
| --- | --- | --- | --- | --- |
| etpwmBASE_t | TBSTS TBCTL TBPHS TBPHSHR TBPRD TBCTR CMPCTL TBPRDHR CMPA CMPAHR AQCTLA CMPB AQSFRC AQCTLB DBCTL AQCSFRC DBFED DBRED TZDCSEL TZSEL TZEINT TZCTL TZCLR TZFLG ETSEL TZFRC ETFLG ETPS ETFRC ETCLR rsvd_1 PCCTL HRPWR HRCNFG rsvd_3 rsvd_2 rsvd_5 rsvd_4 rsvd_6 HRMSTEP rsvd_7 HRPCTL TBPRDM TBPRDHRM CMPAM CMPAHRM DCACTL DCTRIPSEL DCFCTL DCBCTL DCFOFFSET DCCAPCTL DCFWINDOW DCFOFFSETCNT DCCAP DCFWINDOWCNT | Uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 uint16 | FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL | FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL FULL |


**Table 4**

| Constant Name |
| --- |
| k_ADCTrig1Offset_Cnt_s16 |
| k_PwmDeadBand_Cnt_u16 k_PwmRelay_Cnt_u16 |


**Table 5**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| ePWM1 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM2 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM3 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM4 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM5 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM6 | etpwmBASE_t | FULL | FULL | ePWM Register |
| ePWM7 | etpwmBASE_t | FULL | FULL | ePWM Register |


**Table 6**

| Constant Name |
| --- |
| None |


**Table 7**

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 8**

| Function Name | ePWM_Init1 | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | None |  |  |  |  |


**Table 9**

| Function Name | ePWM_Per1 | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | None |  |  |  |  |


**Table 10**

| Function Name | ePWM_DisableOutputs | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | None |  |  |  |  |


**Table 11**

| Function Name | ePWM_EnableOutputs | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | None |  |  |  |  |


**Table 12**

| Data | Value |
| --- | --- |
| None |  |


**Table 13**

| Global Function Name | Calling Frequency | Function in which the function is called |
| --- | --- | --- |
| ePWM_Init1 | On Event | ECU start up |
| ePWM_Per1 | On Event | Motor Control ISR subroutine |


**Table 14**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |


**Table 15**

| Name of Sub Module | Software Segment |
| --- | --- |
| ePWM_Init1 | EPWM_START_SEC_CODE |
| ePWM_Per1 | EPWM_START_SEC_CODE |


**Table 16**

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |


**Table 17**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1.0 | Initial Version ( FDD 34B) –Shutdown Mech not included | 18-Feb-13 | Selva |
|  |  |  |  |
