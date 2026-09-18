---
title: "NvMProxy Integration Manual"
description: "Converted from NvMProxy_Integration_Manual.docx"
---

> **Source:** `NvMProxy/doc/NvMProxy_Integration_Manual.docx` (46,733 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Integration Manual – NvM Proxy

*Table of Contents*


# Dependencies


## SWCs


## Global Functions(Non RTE) to be provided to Integration Project

NvMProxy_Init

NvMProxy_MainFunction

NvMProxy_WriteBlock

NvMProxy_WriteAll

NvMProxy_GetErrorStatus

NvMProxy_SetRamBlockStatus


# Configuration


## Build Time Config


## Configuration Files to be provided by Integration Project


### Da Vinci Parameter Configuration Changes


### DaVinci Interrupt Configuration Changes


### Manual Configuration Changes


# Integration

The following import steps must be completed :

1. Place CBD project structure to appropriate integration folder
1. Execute the “Integrate.bat” script from the Tools directory of this component to perform the necessary integration steps:
1. The script creates the required directories in the integration project, “Generators/Artt/NvMProxy” and “Generators/Components/_Schemes/NvMProxy/bswmd”
1. The script then copies the required files from the CBD generate directory into the new directories.
1. If this is the first time integration, then perform the Davinci Configurator 3rd party component integration procedure.
1. Configure NvM proxy component per program needs
1. Generate NvM proxy and import generated Cd_NvMProxy_swc.arxml into davinci developer and map all NvM service needs on the blocks needing proxies to the NvM Proxy service component (instead of the NvM service component)

## Required Global Data Inputs

N/A


## Required Global Data Outputs

N/A


## Specific Include Path present

Yes


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
| NvM | NvM_WriteBlock() NvM_GetBlockStatus() |
|  |  |
|  |  |


**Table 2**

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |


**Table 3**

| Parameter | Notes | SWC |
| --- | --- | --- |
| NvMProxyConfigSet/NvMProxyBlock/NvmRamBlockDataAddressSecure | The symbol name of the secured buffer location for the block data NOTE: For blocks defined by PIM memory in the Rte, this parameter is the symbol name that Developer inserts into the NvM Ram block configuration parameter for the associated NvM block) | NvMProxy |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
| NvMProxyConfigSet/NvMProxyBlock/NvMBlockDescriptorRef | Reference to the NvMBlockDescriptor container that defines the NvM block linked to this proxy configuration. | NvMProxy |
|  |  |  |
|  |  |  |
|  |  |  |


**Table 4**

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| N/A |  |  |  |


**Table 5**

| Constant | Notes | SWC |
| --- | --- | --- |
| NVMPROXY_EXCLUSIVE_AREA_0 | This exclusive are covers the areas of execution within the component that are operating on the request buffer. The buffer is operated on by the MainFunction and the WriteBlock functions. An appropriate level of protection must be employed to maintain exclusive usage of the buffer data. | SchM |


**Table 6**

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| NvMProxy_Init() | Must be executed after NvM driver has initialized the unsecured block data to be forwarded to the secured memory by this component. | Init |


**Table 7**

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| NvMProxy_MainFunction() | Run prior to NvM_MainFunction for minimal request processing latency | Same as NvM_MainFunction |


**Table 8**

| Memory Section | Contents | Notes |
| --- | --- | --- |
| NVMPROXY_START_SEC_VAR_NOINIT_8 |  | Typically allocated to application in which NvM driver resides. Not required to be allocated to Global shared memeory. |
| NVMPROXY_START_SEC_VAR_CLEARED_16 |  | Must be allocated into Global Shared memory |
| NVMPROXY_START_SEC_VAR_CLEARED_UNSPECIFIED |  | Must be allocated into Global Shared memory |
| NVMPROXY_START_SEC_CODE |  |  |
| NVMPROXY_START_SEC_CONST_UNSPECIFIED |  |  |


**Table 9**

| Feature | RAM | ROM |
| --- | --- | --- |
|  |  |  |


**Table 10**

| Block Name |
| --- |
| <NVM block used Non RTE functions > |


**Table 11**

| Block Name |
| --- |
| <NVM block used in RTE functions > |


**Table 12**

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version |  | JJW |
| 2 | Updates per generation definition | 10/18/12 | JJW |
| 3 | Updates for CRC and Redundant checking feature | 12/02/13 | LWW |
