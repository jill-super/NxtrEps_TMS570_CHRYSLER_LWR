---
title: "SVDiag Integration Manual"
description: "Converted from SVDiag_Integration_Manual.docx"
---

> **Source:** `SVDiag/doc/SVDiag_Integration_Manual.docx` (37,916 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual –

*Table of Contents*


# Dependencies


## SWCs


## Global Functions(Non RTE) to be provided to Integration Project

< Global function (except the ones that are defined in RTE modules) that is defined in this component but used by other function>


# Configuration


## Build Time Config


## Configuration Files to be provided by Integration Project

<Configuration file that will generated from this components that will require Da Vinci Config generation or manual generation. Describe each parameter >


### Da Vinci Parameter Configuration Changes


### DaVinci Interrupt Configuration Changes


### Manual Configuration Changes


# Integration


## Required Global Data Inputs

ExpectedOnTimeA_Cnt_u32

ExpectedOnTimeB_Cnt_u32

ExpectedOnTimeC_Cnt_u32

LRPRCorrectedMtrPosCaptured_Rev_f32

LRPRModulationIndexCaptured_Uls_f32

LRPRPhaseadvanceCaptured_Cnt_s16

MeasuredOnTimeA_Cnt_u32

MeasuredOnTimeB_Cnt_u32

MeasuredOnTimeC_Cnt_u32

MotorVelMRFUnfiltered_MtrRadpS_f32

MtrElecMechPolarity_Cnt_s08

PDActivateTest_Cnt_lgc

MtrDrvrInitStart_Cnt_lgc

VswitchClosed_Cnt_lgc


## Required Global Data Outputs

SVDiag_LowPhReasErrorAcc_Cnt_u16

SVDiag_HighResPhsReasDisable_u8

SVDiag_LowResPhsReasDisable_u8

SVDiag_MtrDrvInitComp_Cnt_lgc

SVDiag_GateDriveFltAcc_Cnt_u16

SVDiag_GenGateDriveFltAcc_Cnt_u16

SVDiag_OnStateFltAcc_Cnt_u16


## Specific Include Path present

None


# Runnable Scheduling

This section specifies the required runnable scheduling.


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
| None |  |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |


**Table 3**

| Parameter | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 4**

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| None |  |  |  |


**Table 5**

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 6**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigPhsReasDiag_Init | Executed once after the RTE is started before first call of MtrDrvDiag_Per1 | RTE (at Startup) |


**Table 7**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigPhsReasDiag_Per1 | Not in OFF, DISABLE, or WARMINIT modes | Rte 2ms task |
| DigPhsReasDiag_Trans1 | In OPERATE mode | On entering mode |
| MtrDrvDiag_Per1 | Not in DISABLE or OFF modes | Rte 2ms task |
| MtrDrvDiag_Per2 | Not in OPERATE or WARMINIT modes | Rte 2ms task |
| MtrDrvDiag_Trns1 | In WARMINIT mode | On entering mode |


**Table 8**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| < Memory mapping Info> |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_32 |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_16 |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_8 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_32 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |


**Table 9**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full |  |  |


**Table 10**

| Block Name |
| --- |
| None |


**Table 11**

| Block Name |
| --- |
| None |


**Table 12**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 3-Oct-13 | VT |
