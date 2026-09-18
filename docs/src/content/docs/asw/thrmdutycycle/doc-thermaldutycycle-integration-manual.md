---
title: "ThermalDutyCycle Integration Manual"
description: "Converted from ThermalDutyCycle_Integration_Manual.docx"
---

> **Source:** `ThrmDutyCycle/doc/ThermalDutyCycle_Integration_Manual.docx` (29,193 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual – Thermal Duty cycle

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

None.


## Configurator Changes

None


# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note:

Proper Initialization of input signals should occur before running each function for the first time.  **(****ThrmlDutyCycle_Init1 ****)****.**


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


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

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| ThrmlDutyCycle_ _Per1 | None | RTE (100ms) |


**Table 5**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| RTE Memory mapping |  |  |
|  |  |  |


**Table 6**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 7**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 25-Mar-13 | Selva |
