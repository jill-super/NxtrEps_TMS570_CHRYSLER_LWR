---
title: "MtrCntrl Integration Manual"
description: "Converted from MtrCntrl_Integration_Manual.docx"
---

> **Source:** `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx` (40,846 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual -- MtrCntrl

*Table of Contents*


# Dependencies


## SWCs


## Configuration Files to be provided by Integration Project

MtrCtrl_Cfg.h


## Functions to be provided to Integration Project

PICurrCntrl_Per1()

TrqCogCancRefPer1()


# Configuration


## Build Time Config


## Generator Config


# Integration


## Global Data

The global symbols mapping done in MtrCtrl_Cfg.h.


## Component Conflicts

None


## Include Path

The “include” directory of this SWC needs to be included in the integration project include search path.

.


## Configurator Changes

None


# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note: In motor control ISR include Ap_MtrCtrl.h instead of CDD_Func.h

Proper Initialization of input signals should occur before running each function for the first time.  **(****CurrParamComp_Init****)****.**


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage


## Table 1: ARM Cortex R4 Memory Usage


# Revision Control Log


**Table 1**

| Module | Required Feature |
| --- | --- |
|  |  |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| PICurrentCntrl TrqCanc | Optimization level greater than 3 |  |


**Table 3**

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 4**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| TrqCogCancRefPer1() | Must be placed in the motor control ISR, after MtrPos | Cyclic (ISR) |
| PICurrCntrl_Per1() | Must be placed in the motor control ISR after TrqCogCancRefPer1() | Cyclic (ISR) |


**Table 5**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
|  |  |  |
|  |  |  |
| QuadDet_Per1 | Must run after TrqReasonable Diagnostics | RTE (2ms) |
| CurrCmd_Per1 | Must run after QuadDet | RTE (2ms) |
| TrqCanc_Per1 | Must run after CurrCmd_Per1 | RTE (2ms) |
| PICurrCntrl_Per2() | Must be placed after TrqCanc_Per1 | RTE (2ms) |
| CurrParamComp_Per1() | Must be placed after PICurrCntrl_Per2 | RTE (2ms) |
| PeakCurrEst_Per1() | Must be placed after PICurrCntrl_Per2 | RTE (2ms) |
|  |  |  |


**Table 6**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| RTE Memory mapping |  |  |
|  |  |  |


**Table 7**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 8**

|  |
| --- |
|  |
|  |


**Table 9**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 25-Mar-13 | Selva |
|  |  |  |  |
|  |  |  |  |
