---
title: "BatteryVoltage Integration Manual"
description: "Converted from BatteryVoltage_Integration_Manual.docx"
---

> **Source:** `BatteryVoltage/doc/BatteryVoltage_Integration_Manual.docx` (29,865 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual – BatteryVoltage

*Table of Contents*


# Dependencies


## SWCs


## Configuration Files to be provided by Integration Project

None


## Functions to be provided to Integration Project

None


# Configuration


## Build Time Config


## Generator Config


# Integration


## Global Data

None


## Component Conflicts

None


## Include Path

None


## Configurator Changes

None


# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note: ECU Voltage Determination sub-function (BatteryVoltage_Per1) must execute prior to the Battery Overvoltage Monitoring Sub-function (ADC ISR).

**.**


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


## NvM Blocks


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

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 4**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| None | None | None |


**Table 5**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| BatteryVoltage_Per1 | None | RTE (2 ms) |
| BatteryVoltage_Per2 | None | RTE (4 ms) |


**Table 6**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| RTE Memory Mapping |  |  |
|  |  |  |


**Table 7**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 8**

| Block Name |
| --- |
| OvervoltageData |


**Table 9**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 16-Apr-13 | Jared |
