---
title: "NxtrLib Systemtime Integration Manual"
description: "Converted from NxtrLib_Systemtime Integration_Manual.docx"
---

> **Source:** `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx` (26,185 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual – NxtrLib_SystemTime


# Dependencies


# Configuration


## Build Time Config


## Generator Config


### System


# Integration

The following import steps must be completed:

1. Place CBD project structure to appropriate integration folder
1. Copy SystemTime_Cfg.h.tt into the Header folder and remove the .tt extension.
1. Configure the constant D_TickRate_Cnt_u32 to the appropriate Os system tick time.

# Runnable Scheduling

This section specifies the required runnable scheduling.


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
|  |  |  |


**Table 5**

| Constant | Notes |
| --- | --- |
|  |  |


**Table 6**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 7**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 |  | Initial version | 26Jul13 | SAH |
