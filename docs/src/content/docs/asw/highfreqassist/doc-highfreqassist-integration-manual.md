---
title: "HighFreqAssist Integration Manual"
description: "Converted from HighFreqAssist_Integration_Manual.docx"
---

> **Source:** `HighFreqAssist/doc/HighFreqAssist_Integration_Manual.docx` (27,891 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual -- HighFreqAssist


# Dependencies


# Configuration


## Build Time Config


## Generator Config

The HighFreqAssist module parameter description file and generator templates are located in the “generate” folder.  The generation scheme at this time relies on the ARTT generation framework developed by BMW.  Following are the recommended steps to integrate the provided generation templates and parameter description with Davinci Configurator:

1. Copy the “Artt/artt” framework folder into the “Generators” directory (if not already present)
1. Execute the “Integrate.bat” script from the Tools directory of this component to perform the necessary integration steps:
1. The script creates the required directories in the integration project, “Generators/Artt/HighFreqAssist” and “Generators/Components/_Schemes/HighFreqAssist/bswmd”
1. The script then copies the required files from the CBD generate directory into the new directories.
1. If this is the first time integration, then perform the Davinci Configurator 3rd party component integration procedure.

## Rte Config

The SWC description included with this component in the “autosar” folder describes only the static portion of the SWC.  A partial SWC description describing the configurable part of the component interface is generated into the Ap_HighFreqAssist_Cfg.arxml file.  This description must be imported into the Rte configuration tool (Developer) using the “Merge Object” option to merge the static SWC description with the generated partial SWC description file.


# Runnable Scheduling

This section specifies the required runnable scheduling.


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory UsageRevision Control Log*


**Table 1**

| Module | Required Feature |
| --- | --- |
| Rte | Port and runnable mapping. |
| WdgM | CheckpointReached() API |


**Table 2**

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |


**Table 3**

| Constant | Notes | SWC |
| --- | --- | --- |
| HighFreqAssistGeneral | General module configuration. See HighFreqAssist technical reference for details. | HighFreqAssist |


**Table 4**

| Runnable | Scheduling Requirements | Privileged Mode | Trigger |
| --- | --- | --- | --- |
| _Per1() | Scheduled per integration project requirements | Not Required | 2ms |


**Table 5**

| Constant | Notes |
| --- | --- |
| HYSTADD_START_SEC_VAR_CLEARED_UNSPECIFIED |  |
| HIGHFREQASSIST_START_SEC_VAR_CLEARED_32 |  |


**Table 6**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full SWC |  |  |


**Table 7**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1 | Initial version | 2-May-13 | Jared |
|  |  |  |  |  |
