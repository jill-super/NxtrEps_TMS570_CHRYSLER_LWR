---
title: "Integration Manual ADC"
description: "Converted from Integration_Manual_ADC.docx"
---

> **Source:** `Adc/doc/Integration_Manual_ADC.docx` (36,546 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual ADC

*Table of Contents*


# Dependencies


## SWCs


## Configuration Files to be provided by Integration Project

NOTE:

For Projects using 33E, make sure “D_ADC1CURRENTMODE_ULS_LGC”  is defined Adc_Cfg.h file.

For Projects using 33C, make sure “D_ADC1CURRENTMODE_ULS_LGC”  is  **N****OT** defined Adc_Cfg.h file.

Template for Configuration file:

Adc_Cfg.h

Adc2_Cfg.h


## Functions to be provided to Integration Project

Adc2_ReadConversion

Adc2_Init1

Adc2_StartGroupConversion

Adc2_EnableGroupNotification

Adc_Init_FixedCfg

Adc_StartGroupConversion

Adc_ReadGroup

Adc_GetGroupStatus


# Configuration


## Build Time Config


## Generator Config


# Integration


## Global Data

None


## Component Conflicts

IoHwAb


## Include Path

$PROJECTPATH$\Adc\include

Adc.h,  Adc2.h, Adc_Common.h


## Configurator Changes

None


# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note:

**.**


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


# Revision Control Log


**Table 1**

| Module | Required Feature |
| --- | --- |
|  |  |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |


**Table 3**

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 4**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| Adc_Init() | Before Adc2_Init1 initialization | ECU Startup |
| Adc2_Init1() | Before PWMCdd initialization | ECU Startup |


**Table 5**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| Adc_StartGroupConversion | None | ISR |


**Table 6**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| ADC2_START_SEC_CODE |  |  |
| ADC2_START_SEC_CONST_32 |  |  |
| ADC_START_SEC_CONST_32 |  |  |
| ADC_START_SEC_CODE |  |  |


**Table 7**

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |


**Table 8**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 09-Apr-13 | Selva |
