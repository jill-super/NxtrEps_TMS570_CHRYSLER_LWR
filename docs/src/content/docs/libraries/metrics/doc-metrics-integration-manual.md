---
title: "Metrics Integration Manual"
description: "Converted from Metrics_Integration_Manual.docx"
---

> **Source:** `Metrics/doc/Metrics_Integration_Manual.docx` (32,020 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual --


# Dependencies


# Configuration


## Build Time Config


## Generator Config


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table : ARM Cortex R4 Memory UsageRevision Control Log*


**Table 1**

| Module | Required Feature |
| --- | --- |
| Rte | Rte_Task_Dispatch() hooks |
| Dio | Dio_WriteChannel() |
|  |  |
| NxtrLib | DtrmnElapsedTime_uS_u32() GetSystemTime_uS_u32() |
|  |  |
| Os | osdNumberOfAllTasks constant value |


**Table 2**

| Constant | Notes | SWC |
| --- | --- | --- |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
| ENABLE_CPUUSE_DIO | If defined then CPU usage is output via a DIO where the DIO is high while the CPU is not in the background task. | Metrics |
| RTE_VFB_TRACE=1 | Enable Rte’s VFB trace functionality to support Rte_Task_Dispatch() hooks | Rte |
| Rte_Task_Dispatch | Enable Rte’s Rte_Task_Dispatch() hooks | Rte |


**Table 3**

| Constant | Notes | SWC |
| --- | --- | --- |
| Dio Channel Name: “Metrics” | Required when ENABLE_CPUUSE_DIO is defined | Dio |
|  |  |  |
|  |  |  |
|  |  |  |


**Table 4**

| Constant | Notes |
| --- | --- |
| METRICS_START_SEC_VAR_CLEARED_UNSPECIFIED | Writable across all applications |


**Table 5**

| Feature | RAM | ROM |
| --- | --- | --- |
| Software task time stamping of task execution |  |  |
| Stack usage monitoring |  |  |


**Table 6**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 |  |  |  |  |
