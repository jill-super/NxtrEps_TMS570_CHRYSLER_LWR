---
title: "TMS570 Startup SysStartup"
description: "Converted from TMS570_Startup_SysStartup_MDD.docx"
---

> **Source:** `TMS570_Startup/doc/TMS570_Startup_SysStartup_MDD.docx` (1,792,999 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module  --


# High-Level Description

This module outlines the functionality of the system startup functions of the TMS570.  This code is intended to be run starting at the reset vector.


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


### Local Function DiagFailedReset


#### Description


### Local Function resetStartup


#### Description


### Local Function pwronStartup


#### Description


### Local Function afterSTC


#### Description


### Local Function memInitialization


#### Design Rationale

All VIM registers are cleared at the end of the startup initialization routine because the startup routine tests will set some interrupt flags during the testing (CCMSelfCheck).


#### Description


### Local Function cpuSelfTest


#### Description


### Local Function setupPLL


#### Design Rationale

This function configures the PLL settings.  These register settings assume 20MHz oscillator.  Changes to these values will drive changes to these register values.


#### Description


### Local Function efcCheck


#### Description


### Local Function efcStuckZeroTestPassed


#### Description


### Local Function efcSelfTest


#### Description


### Local Function periphInit


#### Description


### Local Function checkEFCSelfTestPassed


#### Description


### Local Function setupFlash


#### Design Rationale

The device ID is checked and if the gladiator revA part ID is detected, pre-emption is disabled.  This is to account for errata DEVICE#145 of revA parts.


#### Description


### Local Function trimLPO


#### Description


### Local Function fmcBus2Check


#### Description


### Local Function fmcECCcheck


#### Description


### Local Function mapClocks


#### Description


### Local Function stcSelfCheck


#### Design Rationale

This function assumes a divide by two on the clock frequency will produce a frequency for the test to run at < 90MHz.  For the current design, the clock frequency is 160MHz which will produce an 80MHz clock for this test.


#### Description


### Local Function ccmSelfCheck


#### Description


### Local Function pbistSelfCheck


#### Design Rationale

This function assumes a divide by two on the clock frequency will produce a frequency for the test to run at < 90MHz.  For the current design, the clock frequency is 160MHz which will produce an 80MHz clock for this test.


#### Description


### Local Function pbistRun


#### Design Rationale

This function assumes a divide by two on the clock frequency will produce a frequency for the test to run at < 90MHz.  For the current design, the clock frequency is 160MHz which will produce an 80MHz clock for this test.


#### Description


### Local Function pbistStop


#### Description


### Local Function Delay


#### Description


### Local Macro GetRamDomian1Enabled


#### Description


### Local Macro GetRamDomian2Enabled


#### Description


### Local Macro GetRamDomian3Enabled


#### Description


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions

(Note: For multiple init functions, insert new headers at the “Header 2” level – subset of “5.1 Initialization Functions” and follow the same sub-section design shown below)


### Init: _c_int00


#### Design Rationale

This function is designed to be placed at the reset vector.


#### TI Recommended Initialization

Texas Instruments had provided a recommended startup sequence which the design was based from.  The document (spna106a.pdf) and accompanying source code (spna106a.zip) are located in the doc folder of this SWC.  Note that SysStartup code primarily handles up to step 35 of spna106a (excluding step 12, 29, 30).  Some of the notable deviations from the document include:

1. Addition of debugger connection detection to allow skipping initialization steps which interfere with debugging
1. Replacement of while(1) loops where failures occurred with Nexteer’s failure strategy summarized in section below
1. Use of configuration template headers to define initialization constants that may change from program to program
1. Handling of resets and use of “ResetCause” variable
1. Moving of mux initialization (Step 12 in spna106a) into application specific code (out of common initialization sequence)
1. Moving of SECDED logic check on RAM and Flash (Step 29, 30) into application specific code (out of common initialization sequence)
1. Some of the functions names were changed and the return type was changed to add clarity to the design (efcStuckZeroTest, checkEFCSelfTest)

#### Failed Initialization Diagnostic Strategy

A common strategy is used when diagnostics that are part of this initialization routine fail.  In general, the “ResetCause” variable is set to an appropriate value, the nError pin is forced low, and a software reset is performed.  The nError will put the controller into a known safe state.  The software reset will allow the rest of the initialization tests to be bypassed, as well as reset the controller’s registers to a known state.  The rest of the tests are bypassed to ensure the first failure is captured as the “ResetCause”, and the application can then evaluate the failure reason and set appropriate diagnostics codes (and communicate these on the communication bus if desired).  Note that the registers getting reset will also reset the nError pin state, so forcing the nError pin low is also done when processing the software reset.  Also note that for any of these diagnostics that fail, the general RAM banks will be initialized as part of the reset handling (as opposed to just initializing peripheral ram like most other resets).


#### Software Initiated Resets

For the two types of resets which can be initiated by software (CPU reset and SW reset), a strategy for setting the “ResetCause” variable has been used to allow for flexibility in adding new reset causes.  A check is done to see if the current value of the “ResetCause” indicates a power-on reset.  If this is the case, the initialization code assumes whatever code that initiated the reset did not explicitly indicate the reason for reset, and therefore the initialization code overwrites the value to the appropriate reset type (CPU or SW).  If the reset value is anything other than power-on reset, the initialization code leaves the “ResetCause” as-is under the assumption that whatever code that initiated the reset set this cause specifically.


#### Errata Processing

The device ID is checked at power-on and if the gladiator revA part ID is detected, a _esmCcmErrorsClear_() function is called to handle DEVICE#140 errata processing.


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
| ResetCause_Cnt_Enum | ResetCause_Cnt_Enum | ResetCause_Cnt_Enum |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| <None> |  |  |  |  |
|  |  |  |  |  |


**Table 3**

| Typedef Name | Element Name | Value |
| --- | --- | --- |
| enum systemClockSource | SYS_OSC | 0 |
|  | SYS_PLL1 | 1 |
|  | SYS_EXTERNAL1 | 3 |
|  | SYS_LPO_LOW | 4 |
|  | SYS_LPO_HIGH | 5 |
|  | SYS_PLL2 | 6 |
|  | SYS_EXTERNAL2 | 7 |
|  | SYS_VCLK | 9 |


**Table 4**

| Constant Name |
| --- |
| <None> |
|  |


**Table 5**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_OTP1BITERRADDR_CNT_U32 | 1 | Counts | 0xF00803F4 |
| D_OTP2BITERRADDR_CNT_U32 | 1 | Counts | 0xF00803FC |
| D_DPRAMSELECT_CNT_U32 | 1 | Counts | 0x4 |
| D_SPRAMSELECT_CNT_U32 | 1 | Counts | 0x8 |
| D_EFCAUTOLOADERROREN_CNT_U32 | 1 | Counts | 0x00040000 |
| D_EFCINSTRUCTIONERROREN_CNT_U32 | 1 | Counts | 0x00080000 |
| D_EFCINSTRUCTIONINFOEN_CNT_U32 | 1 | Counts | 0x00100000 |
| D_EFCSELFTESTERROREN_CNT_U32 | 1 | Counts | 0x00200000 |
| D_EFCSELFTESTDONE_CNT_U32 | 1 | Counts | 0x00008000 |
| D_EFCSELFTESTERROR_CNT_U32 | 1 | Counts | 0x00004000 |
| D_OUTPUTENABLE_CNT_U32 | 1 | Counts | 0x0003C000 |
| D_SELFTESTERROR_CNT_U32 | 1 | Counts | 0x18 |
| D_LPOTRIMVALUE_CNT_U32 | 1 | Counts | ((*(uint32*)0xF00801B4) & 0xFFFF0000)>>16 |
| D_PLLSLIPMASK_CNT_U32 | 1 | Counts | 0x00000300 |
|  |  |  |  |
| D_LOWBYTEMASK_CNT_U32 | 1 | Counts | 0x0000000FFUL |
| D_CURRENTLPOTRIMMASK_CNT_U32 | 1 | Counts | 0x00000FFFFUL |
| D_LPOMONLFTRIMMASK_CNT_U32 | 1 | Counts | 0xFFFFFF00UL |
| D_LPOMONHFTRIMMASK_CNT_U32 | 1 | Counts | 0xFFFF00FFUL |
| D_OTPRAMDEVICEADDR_CNT_U32 | 1 | Counts | 0xF0080148u |
| D_ESRAM5ENABLE_CNT_U32 | 1 | Counts | 0x01<<20 |
| D_ESRAM6ENABLE_CNT_U32 | 1 | Counts | 0x01<<21 |
| D_ESRAM8ENABLE_CNT_U32 | 1 | Counts | 0x01<<27 |


**Table 6**

| Constant Name |
| --- |
| D_SPRAMGRPSTMS_CNT_U32 |
| D_DPRAMGRPSTMS_CNT_U32 |
| D_CSDISCLRVAL_CNT_U32 |
| D_CSVSTATMASK_CNT_U32 |
| D_PCSPWRDWNCLR0VAL_CNT_U32 |
| D_PCSPWRDWNCLR1VAL_CNT_U32 |
| D_PSPWRDWNCLR0VAL_CNT_U32 |
| D_PSPWRDWNCLR1VAL_CNT_U32 |
| D_PSPWRDWNCLR2VAL_CNT_U32 |
| D_PSPWRDWNCLR3VAL_CNT_U32 |
| D_RAMPWRONINITMASKTMS_CNT_U32 |
| D_RAMRESETINITMASKTMS_CNT_U32 |
| D_PLLCTL1VAL_CNT_U32 |
| D_FRDCNTLVAL_CNT_U32 |


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

| Function Name | DiagFailedReset | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 10**

| Function Name | resetStartup | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | MemInitMask_Cnt_T_u32 | uint32 | FULL | FULL |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 11**

| Function Name | pwronStartup | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 12**

| Function Name | afterSTC | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 13**

| Function Name | memInitialization | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | MemInitMask_Cnt_T_u32 | uint32 | FULL | FULL |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 14**

| Function Name | cpuSelfTest | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 15**

| Function Name | setupPLL | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 16**

| Function Name | efcCheck | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 17**

| Function Name | efcStuckZeroTestPassed | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | TestPassed_Cnt_T_lgc | boolean | FALSE | TRUE | 0 |


**Table 18**

| Function Name | efcSelfTest | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 19**

| Function Name | periphInit | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 20**

| Function Name | checkEFCSelfTestPassed | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | TestPassed_Cnt_T_lgc | boolean | FALSE | TRUE | 0 |


**Table 21**

| Function Name | setupFlash | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 22**

| Function Name | trimLPO | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 23**

| Function Name | fmcBus2Check | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 24**

| Function Name | fmcECCcheck | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |


**Table 25**

| Function Name | mapClocks | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |
|  |  |  |  |  |  |
| Return Value | N/A |  |  |  |  |
