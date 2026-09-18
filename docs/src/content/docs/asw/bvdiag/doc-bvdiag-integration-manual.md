---
title: "BVDiag Integration Manual"
description: "Converted from BVDiag_Integration_Manual.docx"
---

> **Source:** `BVDiag/doc/BVDiag_Integration_Manual.docx` (37,199 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual - BVDIAG

*Table of Contents*


# Dependencies


## SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.


## Global Functions(Non RTE) to be provided to Integration Project

< None>


# Configuration


## Build Time Config


## Configuration Files to be provided by Integration Project

Ap_BVDiag_Cfg.h for checkpoint enables


### Da Vinci Parameter Configuration Changes


### DaVinci Interrupt Configuration Changes


### Manual Configuration Changes


# Integration


## Required Global Data Inputs

Batt_Volt_f32 from SER

CCLMSAActive_Cnt_lgc (Note : Only required for BMW as per its SER)


## Required Global Data Outputs

Sets BatteryVoltage Diagnostics


## Specific Include Path present

No


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
| <None> |  |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| <None> |  |  |


**Table 3**

| Parameter | Notes | SWC |
| --- | --- | --- |
| B1_BATTVOLTDIAG | This parameter will be turned ON only if customer requires $B1 NTC STD_ON : Enables NTC $B1 logic STD_Off : Disables NTC $B1 logic |  |


**Table 4**

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| <None> |  |  |  |


**Table 5**

| Constant | Notes | SWC |
| --- | --- | --- |
| <None> |  |  |


**Table 6**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| None | None | Init |


**Table 7**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| BVDiag_Per1 |  | 10ms |


**Table 8**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| BVDIAG_START_SEC_VAR_CLEARED_32 |  |  |


**Table 9**

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |


**Table 10**

| Block Name |
| --- |
| <None > |


**Table 11**

| Block Name |
| --- |
| None |


**Table 12**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 13-Sep-13 | NRAR |
