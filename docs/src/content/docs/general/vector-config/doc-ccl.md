---
title: "Communication Control (Ccl)"
description: "Converted from Ccl.docx"
---

> **Source:** `Chrysler_LWR_EPS_TMS570/HLDD/AUTOSAR Config/Ccl.docx` (30,815 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

**Module  --**** ****Ccl**


# References

Communication Control LayerTechnical Reference v1.8 ()

TMS570LS Series Microcontroller Technical Reference Manual (TMS570 Tech Ref_spnu489.pdf)


# Configuration Settings


## Ccl__core Configuration


## Advanced Task Settings Configuration


# Known Issues / Limitations With Configuration


# Revision Control Log


**Table 1**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| Configurable Options | Configurable Options | Configurable Options |
| CCL Canbedded Handling | Yes | Default setting |
| Emc Wake Up Timeout (ms) | 500 | Default setting |
| Ecu Mode | Stop mode ECU | Default setting |
| Enable Transceiver In Wake Up Interrupt | No | Default setting |
| Naming Conventions | Naming Conventions | Naming Conventions |
| CCL Task Prefix | Ccl | Default setting |
| Advanced Task settings | Advanced Task settings | Advanced Task settings |
| Scheduler Base Time (ms) | 10 | Default setting |
| CANbedded Tasks |  |  |
| CCL Task Mode | Function Call |  |
| Debug handling | Debug handling | Debug handling |
| Internal Debug | No | Nexteer has no design in place to log the fatal failures in the event an assertion is triggered during development. Perhaps the assertions should be mapped to the Autosar Det. Until a design use case is determined, this feature is being disabled, The production intended setting is “None” to reduce the driver operating overhead (i.e. runtime and program space) by eliminating unnecessary error checking in the final tested configuration. |
| Use CCL Error Hook | No | See above. |
| Transceiver Settings | Transceiver Settings | Transceiver Settings |
| Transceiver Config File | None | Default setting |


**Table 2**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| CANdesc Task | CANdesc Task | CANdesc Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) |  |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| XCP Task | XCP Task | XCP Task |
| Cycle Time (ms) | 0 | Default setting |
| Offset Time (ms) | 0 | Default setting |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| DPM Task | DPM Task | DPM Task |
| Cycle Time (ms) | 20 | Default setting |
| Offset Time (ms) | 0 | Default setting |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| TP Tx Task | TP Tx Task | TP Tx Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) | 0 |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| TP Rx Task | TP Rx Task | TP Rx Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) | 0 |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| FRFM Task | FRFM Task | FRFM Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) |  |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| DBKOM Tx Task | DBKOM Tx Task | DBKOM Tx Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) | 0 |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| DBKOM Rx Task | DBKOM Rx Task | DBKOM Rx Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) | 0 |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |
| NM OSEK Task | NM OSEK Task | NM OSEK Task |
| Cycle Time (ms) | 10 | Default setting |
| Offset Time (ms) | 0 |  |
| Pre Task | No | Default setting |
| Post Task | No | Default setting |


**Table 3**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Creation | 30JUL13 | JJW |
|  |  |  |  |  |
