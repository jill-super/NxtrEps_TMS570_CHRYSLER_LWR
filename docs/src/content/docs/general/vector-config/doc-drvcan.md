---
title: "DrvCan"
description: "Converted from DrvCan.docx"
---

> **Source:** `Chrysler_LWR_EPS_TMS570/HLDD/AUTOSAR Config/DrvCan.docx` (33,084 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

**Module  --**** ****DrvCan**


# References

Vector CAN Driver Technical Reference V3.01.01 ()

Vector CAN Driver Technical Reference  TI TMS470 DCAN v 1.03.02 ()

TMS570LS Series Microcontroller Technical Reference Manual (TMS570 Tech Ref_spnu489.pdf)


# Configuration Settings


## DrvCan Configuration


## Hw Configuration


# Known Issues / Limitations With Configuration

None .


# Revision Control Log


**Table 1**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| Hw_Tms470DcanCpuCan | Hw_Tms470DcanCpuCan | Hw_Tms470DcanCpuCan |
| Errata Dcan22 iterations | 255 | Default setting |
| Common Driver Parameters | Common Driver Parameters | Common Driver Parameters |
| CANOnline / CANOffline Notification | No | Default setting |
| DLC Check | Against minimum acceptance length | Default setting |
| Copy Mechanism | Copy all received bytes | Default setting |
| Sleep / Wake-up Functionality | No | Default setting |
| FullCAN Overrun Notification | Yes | Default setting |
| Use Tx BitQueue | Yes | Default setting |
| Can Interrupt Control Callbacks | No | Default setting |
| Common Confirmation Function | No | Default setting |
| Rx Notification | No | Default setting |
| Active / Passive State | No | Default setting |
| Extended Status | No | Default setting |
| Transmit Queue | Yes | Default setting |
| Tx Observation | No | Default setting |
| Message Not Matched Notification | No | Default setting |
| Overrun Notification | No | Default setting |
| Hardware Loop Check | No | Default setting |
| Partial Offline Mode | Yes | Default setting |
| Generic Precopy | No | Default setting |
| CopyToCAN / CopyFromCAN Service | No | Default setting |
| CAN Cancel Notification | No | Default setting |
| Offline Modes | Offline Modes | Offline Modes |
| To be completed |  |  |
| OSEK OS | OSEK OS | OSEK OS |
| OSEK OS Cat. 2 Interrupt | No | This setting should be “Yes” because the driver is QM software, which means in the EPS system that it must be run in a user mode application. In order for the Os to appropriately configure the MPU and switch to user mode a category 2 interrupt is required. This setting is “grayed out” and set to “No”. The current software implementation configures a Cat2 interrupt function which then simply calls the interrupt function as a workaround. |
| Polling | Polling | Polling |
| Polling Type | Type Specific | Desired configuration is to provide interrupt processing only on Tx messages. The “Type Specific” setting provides a polling configuration granularity that allows this configuration. “Individual” would also work, but has a finer configuration granularity that is more complex and is not necessary for this use case. |
| Rx BasicCAN Polling | Yes | In order to prevent excessive interrupt overhead, all Rx messages are to be processed on a polled basis. |
| Rx FullCAN Polling | Yes | In order to prevent excessive interrupt overhead, all Rx messages are to be processed on a polled basis. |
| Tx Polling | No | In order to provide maximum Tx bandwidth for XCP DAQ lists, Tx processing is performed on an interrupt basis. |
| Error Polling | Yes | Poll the CAN controller for error indications in order to set an appropriate DTC and perform error recovery processing. Polling does no violate any known error reaction/error recovery response time requirement. Elimination of unnecessary ISR sources eliminates application issues arising from excessive IRQ’s pre-empting critical control processing tasks. |
| Low Level Messages Transmission | Low Level Messages Transmission | Low Level Messages Transmission |
| Low Level Transmit Cancel Notification | No | Default setting |
| Low Level Transmission | No | Default setting |
| Low Level Transmission Confirmation Function | No | Default setting |
| API | API | API |
| Symbolic Names for Signal Values | Yes | Default setting |
| Indexed Component | No | Default setting |
| General Settings | General Settings | General Settings |
| Security Level | 30 | Default setting |
| User Config File | user.cfg | Name of the file containing Nexteer user configuration settings for GENy generation. |
| Debug Support | Debug Support | Debug Support |
| Assertions | None | Nexteer has no design in place to log the fatal failures in the event an assertion is triggered during development. Perhaps the assertions should be mapped to the Autosar Det. Until a design use case is determined, this feature is being disabled. The production intended setting is “None” to reduce the driver operating overhead (i.e. runtime and program space) by eliminating unnecessary error checking in the final tested configuration. |
| Dynamic Tx Objects | Dynamic Tx Objects | Dynamic Tx Objects |
| ID | No | Default setting |
| DLC | No | Default setting |
| Data Pointer | No | Default setting |
| Confirmation | No | Default setting |
| Pretransmit | No | Default setting |
| ID Search Algorithm | ID Search Algorithm | ID Search Algorithm |
| Search Algorithm | Linear | Default setting |
| Addtiional Memory [byte] | 0 | Default setting |
| Maximum Search Steps | 2 | Default setting |
| Rx Queue | Rx Queue | Rx Queue |
| Overrun Notification | No | Default setting |
| Rx Queue | No | Default setting |
| Pre Rx Queue Notification | No | Default setting |
| Size | 3 | Default setting |


**Table 2**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| Configurable Options | Configurable Options | Configurable Options |
| Compiler | TexasInstruments | Default setting |
| Derivative | TMS570PSFC66 | Default setting |
| General Settings | General Settings | General Settings |
| User Config File | None | Default setting |
| CPU Settings | CPU Settings | CPU Settings |
| CPU Type | 32 Bit | Default setting |
| Byte Order | Big Endian | Default setting |
| Bit Order | MSB to LSB | Default setting |
| Definition of ‘Define C_COMP_xxx’ | TI_TMS470_DCAN | Default setting |
| Definition of ‘Define C_PROCESSOR_xxx’ | TI_TMS470_PFSC66 | Default setting |
| Generation Additions | Generation Additions | Generation Additions |
| Dummy Functions | No | Default setting |
| Dummy Statement | Yes | Default setting |
| OS | OS | OS |
| OS Type | Autosar | An Autosar Os is used in this project. |
| Optimization | Optimization | Optimization |
| Atomic Bit Access in Bitfield | No | Default setting |
| Atomic Variable Access | Atomic32BitAccess | The TMS570 microcontroller performs 32 bit atomic data accesses. |
| Multiple GENy Projects | Multiple GENy Projects | Multiple GENy Projects |
|  |  | Default setting |
|  |  | Default setting |
| Generation Options | Generation Options | Generation Options |
| Disable generation of #error directives | No | Default setting |
| Conditional Generation | No | Default setting |
| VStdLib | VStdLib | VStdLib |
| Synch Mechanism | Synch Mechanism | Synch Mechanism |
| Lock Mechanism | OSEK | “Default” handling is NOT selected because the VStdLib default interrupt handling requires a privileged CPU mode of execution. The Nexteer use case is placing the Can drivers in a user mode application because they are QM rated drivers. Therefore the “Default” interrupt handling will not function properly and cannot be used. “OSEK” Handling selected for compatibility with the Nexteer use case. |
| Lock Level | Global | Default setting |
| Nested Disable | None | Default setting |
| Nested Restore | None | Default setting |
| Debug Support | Debug Support | Debug Support |
| Assertions | no | Default setting |


**Table 3**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Creation | 30JUL13 | JJW |
|  |  |  |  |  |
