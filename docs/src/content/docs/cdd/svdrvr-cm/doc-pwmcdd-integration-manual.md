---
title: "PWMCdd Integration Manual"
description: "Converted from PWMCdd_Integration_Manual.docx"
---

> **Source:** `SVDrvr_CM/doc/PWMCdd_Integration_Manual.docx` (33,531 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual -- PWMCdd


# Dependencies


## SWCs


## Configuration Files to be provided by Integration Project (Project Specific)

PWMCdd_Cfg.h  ( Note : Make sure Macro assignments match correct global variable  included in PWMCdd_Cfg.h . File below is a template. Necessary definition changes needs to be made to template before integration).


## Functions provided to Integration Project

CDDPorts_ClearPhsReasSum(uint16 DataAccessBfr_Cnt_T_u16)

CDD_ApplyPWMMtrElecMechPol(sint8 MtrElecMechPol_Cnt_s8)


# Configuration


## Build Time Config


## Generator Config


# Integration


## Global Data

The following global symbols must be defined in CDD_Data.c and .h (populated by PwmCdd):

1. uint16: CDD_DCPhsComp_Cnt_G_u16[3]
1. uint16: CDD_PWMPeriod_Cnt_G_u16

## Component Conflicts


### Project Specific

1. **NHET****/****EPWM**  version corresponding PWMCdd component spilt and using global variables CDD_DCPhsComp_Cnt_G_u16 and CDD_PWMPeriod_Cnt_G_u16  should be used.

## Include Path

The “include” directory of this SWC needs to be included in the integration project include search path.


# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note: don’t forget include  header file from PWMCDD  where PwmCdd_Per1 is called


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


# Revision Control Log


**Table 1**

| Module | Required Feature |
| --- | --- |
| CDD_Data | Global variables for DC Phs Comp (for using in Nhet/) |


**Table 2**

| Constant | Notes | SWC |
| --- | --- | --- |
|  |  |  |


**Table 3**

| Constant | Notes | SWC |
| --- | --- | --- |
|  |  |  |


**Table 4**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| PwmCdd_Init | Place in EcuStartup. Execute along with NHET initialization. | Init |
| PwmCdd_Per1 | Must be placed in the motor control ISR, before Nhet (or whichever function populates the global variables used byNhet). | Cyclic (ISR) * |


**Table 5**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| PWMCDD_START_SEC_VAR_CLEARED_16 | Variable Definitions |  |


**Table 6**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 7**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 14-Feb-13 | Selva |
