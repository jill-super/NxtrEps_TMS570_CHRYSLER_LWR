---
title: "Power Limit Function CM Integration Manual"
description: "Converted from Power_Limit_Function_CM_Integration_Manual.docx"
---

> **Source:** `PwrLmtFuncCr/doc/Power_Limit_Function_CM_Integration_Manual.docx` (40,887 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual  - PwrLmtFuncCr

*Table of Contents*


# Dependencies


## SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.


## Global Functions(Non RTE) to be provided to Integration Project

< Global function (except the ones that are defined in RTE modules) that is defined in this component but used by other function>


# Configuration


## Build Time Config


## Configuration Files to be provided by Integration Project

Ap_PwrLmtFuncCr_Cfg.h


### Da Vinci Parameter Configuration Changes


### DaVinci Interrupt Configuration Changes


### Manual Configuration Changes


# Integration


## Required Global Data Inputs

EstKe_VpRadpS_f32

MotorVelMRF_MtrRadpS_f32

PosServEnable_Cnt_lgc

Vecu_Volt_f32

CntDisMtrTrqCmdMRF_MtrNm_f32

AltFaultActive_Cnt_lgc


## Required Global Data Outputs

MRFMtrTrqCmd_MtrNm_f32

FltTrqLmt_Uls_f32

ThresholdExceeded_Cnt_lgc


## Specific Include Path present

< No >


# Runnable Scheduling

This section specifies the required runnable scheduling.

**.**


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


## Non  RTE NvM Blocks

Note : Size of the NVM block if configured in developer


## RTE NvM Blocks

Note : Size of the NVM block if configured in developer


# Compiler Settings


## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.


## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.


# Revision Control Log


**Table 1**

| Module | Required Feature |
| --- | --- |
| <Name of SWC> | <Addition of global data, function*. |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |


**Table 3**

| Parameter | Notes | SWC |
| --- | --- | --- |
| PwrLmtFuncCrGeneral/PwrLmtFuncCrCPEnable | Enable checkpoints if needed | PwrLmtFuncCr |


**Table 4**

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| <Configurator Changes for Interrupts> |  |  |  |


**Table 5**

| Constant | Notes | SWC |
| --- | --- | --- |
| <Additional configuration changes> |  |  |


**Table 6**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| PwrLmtFuncCr_Init1 | Called from RTE before first call of periodic function | RTE at init |


**Table 7**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| PwrLmtFuncCr_Per1 | Not in WARMINIT, OFF, DISABLE | RTE 2ms |
| PwrLmtFuncCr_Per2 | Not in WARMINIT, OFF, DISABLE | RTE 10ms |


**Table 8**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| PWRLMTFUNCCR_START_SEC_VAR_CLEARED_32 |  |  |
| PWRLMTFUNCCR_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| PWRLMTFUNCCR_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |
| RTE_START_SEC_AP_PWRLMTFUNCCR_APPL_CODE |  |  |


**Table 9**

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |


**Table 10**

| Block Name |
| --- |
| <NVM block used Non RTE functions > |


**Table 11**

| Block Name |
| --- |
| <NVM block used in RTE functions > |


**Table 12**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 28-Aug-13 | KMC |
