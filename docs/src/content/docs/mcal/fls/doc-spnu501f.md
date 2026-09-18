---
title: "SPNU501F"
description: "Converted from SPNU501F.pdf"
---

> **Source:** `Fls/doc/SPNU501F.pdf` (167,634 bytes, `PDF`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

*PDF original: 51 page(s). Text extracted below (first 15 pages shown). Layout, figures and diagrams are not preserved — consult the original file in the repository for exact rendering.*


## Page 1

F021 Flash API
Version 2.01.00
Reference Guide
Literature Number: SPNU501F
December 2012 – Revised May 2014


## Page 2

Contents
1 Introduction......................................................................................................................... 4
1.1 Reference Material....................................................................................................... 4
1.2 Function Listing Format ................................................................................................. 4
2 F021 Flash API Overview ...................................................................................................... 6
2.1 Introduction................................................................................................................ 6
2.2 API Overview ............................................................................................................. 6
2.3 Using API.................................................................................................................. 7
3 API Functions .................................................................................................................... 10
3.1 Flash State Machine Functions ....................................................................................... 10
3.2 Asynchronous Functions .............................................................................................. 16
3.3 Program Functions ..................................................................................................... 18
3.4 Read Functions ......................................................................................................... 20
3.5 Informational Functions ................................................................................................ 29
3.6 Utility Functions ......................................................................................................... 32
3.7 User Definable Functions.............................................................................................. 33
4 API Macros ........................................................................................................................ 34
4.1 FAPI_CHECK_FSM_READY_BUSY ................................................................................ 34
4.2 FAPI_CLEAR_FSM_DONE_EVENT................................................................................. 34
4.3 FAPI_GET_FSM_STATUS............................................................................................ 35
4.4 FAPI_SUSPEND_FSM ................................................................................................ 36
4.5 FAPI_WRITE_EWAIT .................................................................................................. 37
4.6 FAPI_WRITE_LOCKED_FSM_REGISTER ......................................................................... 37
5 Recommended FSM Flows .................................................................................................. 37
5.1 New Devices From Factory ........................................................................................... 37
5.2 Recommended Erase Flows .......................................................................................... 38
5.3 Recommended Program Flow ........................................................................................ 40
Appendix A Flash State Machine Commands................................................................................. 41
A.1 Flash State Machine Commands.................................................................................... 41
Appendix B Typedefs and Enumerations....................................................................................... 42
B.1 Type Definitions ....................................................................................................... 42
B.2 Enumerations .......................................................................................................... 42
Appendix C Flash Validation Procedure ........................................................................................ 47
Appendix D Parallel Signature Analysis (PSA) algorithm................................................................. 48
Appendix E Revision History ....................................................................................................... 49
2 Table of Contents SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated


## Page 3

www.ti.com
List of Figures
1 FMSTAT Register .......................................................................................................... 35
2 Recommended Sector Erase Flow....................................................................................... 38
3 Recommended Bank Erase Flow ........................................................................................ 39
4 Recommended Program Flow............................................................................................ 40
List of Tables
1 Summary of Flash State Machine Functions............................................................................. 6
2 Summary of Asynchronous Command Functions ....................................................................... 6
3 Summary of Program Functions ........................................................................................... 6
4 Summary of Read Functions ............................................................................................... 7
5 Summary of Information Functions........................................................................................ 7
6 Summary of User Defined Functions...................................................................................... 7
7 Summary of Utility Functions............................................................................................... 7
8 FMSTAT Register Field Descriptions.................................................................................... 35
9 Flash State Machine Commands ........................................................................................ 41
10 API Version History ........................................................................................................ 49
11 Document Revision History ............................................................................................... 50
3SPNU501F – December 2012 – Revised May 2014 List of Figures
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated


## Page 4

Reference Guide
SPNU501F – December 2012 – Revised May 2014
1 Introduction
Background
This reference guide provides a detailed description of Texas Instruments' F021 Flash API functions that
can be used to erase, program and verify F021 Flash on TI devices.
1.1 Reference Material
Use this guide in conjunction with the F021 Flash Module chapter in the device-specific technical
reference manual and data sheet that is being used. For additional options for programming and erasing
the Flash, see the Advanced F021 Flash API Erase/Program Usage (SPNA148).
1.2 Function Listing Format
This is the general format of an entry for a function, compiler intrinsic, or macro.
A short description of what function function_name() does.
Synopsis
Provides a prototype for function function_name().
<return_type> function_name(
<type_1> parameter_1,
<type_2> parameter_2,
<type_n> parameter_n
)
Parameters
parameter_1 [in] Pointer to x
parameter_2 [out] Handle for y
parameter_n [in/out] Pointer to z
Parameter passing is categorized as follows:
• In — Means the function uses one or more values in the parameter that you give it without storing any
changes.
• Out — Means the function saves one or more of the values in the parameter that you give it. You can
examine the saved values to find out useful information about your application.
• In/out — Means the function changes one or more of the values in the parameter that you give it and
saves the result. You can examine the saved values to find out useful information about your
application.
Description
Describes the function function_name(). This section also describes any special characteristics or
restrictions that might apply:
• Function blocks or might block under certain conditions
• Function has pre-conditions that might not be obvious
• Function has restrictions or special behavior
All trademarks are the property of their respective owners.
4 SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated


## Page 5

www.ti.com Introduction
Return Value
Specifies any value or values returned by function function_name().
See Also
Lists other functions or data types related to function function_name().
Example
Provides an example (or a reference to an example) that illustrates the use of function function_name().
5SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated


## Page 6

F021 Flash API Overview www.ti.com
2 F021 Flash API Overview
2.1 Introduction
The F021 Flash API is a library of routines that when called with the proper parameters in the proper
sequence, erases, programs, or verifies Flash memory on Texas Instruments microcontrollers using the
F021 (65nm) process. On ARM Cortex devices, these routines must be run in a privileged mode (a mode
other than user) to allow access to the Flash memory controller registers. The API verifies for the selected
bank, that the appropriate RWAIT or EWAIT value is set for the specified system frequency.
2.2 API Overview
Table 1. Summary of Flash State Machine Functions
API Function Description
Fapi_disableAutoEccCalculation() (1) Disables auto generation of ECC when data is written into an FWPWRITEx
register.
Fapi_disableBanksForOtpWrite() Disables all banks from programming customer OTP
Fapi_disableFsmDoneEvent() Disables the generation of an FSM_Done event at the end of a program or erase
operation.
Fapi_enableAutoEccCalculation() (1) Enables auto generation of ECC when data is written into an FWPWRITEx register.
Fapi_enableBanksForOtpWrite() Enables banks to allow programming of customer OTP
Fapi_enableEepromBankSectors() Enables the sectors in EEPROM bank for program and erase operations
Fapi_enableFsmDoneEvent() Enables the generation of an FSM_Done event at the end of a program or erase
operation.
Fapi_enableMainBankSectors() Enables the sectors in Main banks for program and erase operations
Fapi_initializeFlashBanks() Required Bank initialization before any erase, program, or verify API function.
Fapi_isAddressEcc() Determines if address falls in Flash memory controller ECC ranges
Fapi_remapEccAddress() Remaps an ECC address to corresponding main address
Fapi_remapMainAddress() Remaps an Main address to corresponding ECC address
Fapi_setActiveFlashBank() Sets the active bank for a erase or program command
(1) This function is only available on devices with the L2FMC Flash Controller.
Table 2. Summary of Asynchronous Command Functions
API Function Description
Fapi_issueAsyncCommand() Issues a command to FSM for operations that do not require an address
Fapi_issueAsyncCommandWithAddress() Issues a command to FSM for operations that require an address
Table 3. Summary of Program Functions
API Function Description
Sets up the required registers for programming and issues the command to theFapi_issueProgrammingCommand() FSM
Fapi_issueProgrammingCommandForEccAdd Remaps an ECC address to the main data space and then call
ress() Fapi_issueProgrammingCommand()
6 SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated


## Page 7

www.ti.com F021 Flash API Overview
Table 4. Summary of Read Functions
API Function Description
Fapi_doVerify() Verifies specified Flash memory range against supplied values
Fapi_doVerifyByByte() Verifies specified Flash memory range


> **Note:** remaining pages truncated. See the original PDF in the repository.
