---
title: "FlsTst Integration Manual"
description: "Converted from FlsTst_Integration_Manual.docx"
---

> **Source:** `TMS570_uDiag/doc/FlsTst_Integration_Manual.docx` (43,432 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual --

The FlsTst module parameter description file and generator templates are located in the “generate” folder.  The generation scheme at this time relies on the ARTT generation framework developed by BMW.  Following are the recommended steps to integrate the provided generation templates and parameter description with Davinci Configurator:

1. Copy the “Artt/artt” framework folder into the “Generators” directory (if not already present)
1. Execute the “Integrate.bat” script from the Tools directory of this component to perform the necessary integration steps:
1. The script creates the required directories in the integration project, “Generators/Artt/FlsTst” and “Generators/Components/_Schemes/FlsTst/bswmd”
1. The script then copies the required files from the CBD generate directory into the new directories.
1. If this is the first time integration, then perform the Davinci Configurator 3rd party component integration procedure.

# Runnable Scheduling

This section specifies the required runnable scheduling.

* Can be called during run time to change block test configuration if required.


# Memory Mapping


## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.


## Usage

*Table 1: ARM Cortex R4 Memory Usage*


**Table 1**

| Module | Required Feature |
| --- | --- |
| NxtrLib | DtrmnElapsedTime_uS_u32() GetSystemTime_uS_u32() |
| TMS570 CRC peripheral | Exclusive access to the CRC peripheral registers. |
| TMS570 DMA peripheral | Exclusive access to the DMA peripheral registers. |
| TMS570 ESM peripheral | Exclusive access to the ESM configuration bits that control the DMA MPU interrupt enable, nError pin action, and Interrupt level mapping. |
|  |  |
| DiagMgr (Nexteer DEM) | NxtrDiagMgr_ReportNTCStatus() API |
| uDiagESM | DMAMPUErr() Callback notification on DMA MPU violation |
|  |  |


**Table 2**

|  |  |  |
| --- | --- | --- |
|  |  |  |


**Table 3**

|  |  |  |
| --- | --- | --- |
|  |  |  |


**Table 4**

|  | Notes | SWC |
| --- | --- | --- |
|  |  |  |
| FlsTstConfigSet | At least one block configuration set must be defined. See FlsTst technical reference for details. | FlsTst |
| FlsTstConfigurationOfOptApiServices | Configuration of optional API services. All optional services are disabled by default. | FlsTst |
| FlsTstDemEventParameterRefs | Configuration of NTC enumeration symbol name for diagnostic tests performed in this module. | FlsTst |
| FlsTstGeneral | General module configuration. See FlsTst technical reference for details. | FlsTst |
|  |  |  |


**Table 5**

|  |  |  |  |
| --- | --- | --- | --- |
|  |  |  |  |
|  |  |  |  |


**Table 6**

|  |  |  |
| --- | --- | --- |
|  |  |  |


**Table 7**

| Runnable | Scheduling Requirements | Privileged Mode | Trigger |
| --- | --- | --- | --- |
| FlsTst_Init() | Must be executed prior to using FlsTst_MainFunction() | Required | Init* |
| FlsTst_MainFunction() | Scheduling cycle can influence the time to complete the background test interval. A new test block is started only during the invocation of the MainFunction, so an excessively large period between MainFunction calls will extend the time for a test interval to complete. |  | Cyclic |
| FlsTst_CrcIrq() | Scheduled via hardware IRQ. The integrator must enable the interrupt source configured in the Os before this runnable can be triggered by the hardware. |  | IRQ on signature failure |


**Table 8**

| Constant | Notes |
| --- | --- |
| FLSTST_START_SEC_VAR_CLEARED_8 |  |
| FLSTST_START_SEC_VAR_16 |  |
| FLSTST_START_SEC_VAR_CLEARED_UNSPECIFIED |  |
| FLSTST_START_SEC_VAR_UNSPECIFIED |  |
| FLSTST_START_SEC_CODE |  |
|  |  |


**Table 9**

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |


**Table 10**

|  |
| --- |
|  |


**Table 11**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1 | Initial version |  | JJW |
| 2 | Updated integration process description to reference use of Integrate.bat | 09/18/12 | JJW |
|  |  |  |  |
