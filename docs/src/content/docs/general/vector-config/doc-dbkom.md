---
title: "Dbkom"
description: "Converted from Dbkom.docx"
---

> **Source:** `Chrysler_LWR_EPS_TMS570/HLDD/AUTOSAR Config/Dbkom.docx` (27,432 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

**Module  --**** ****Dbkom**


# References

DBKOM Technical Reference v2.08.00 ()

TMS570LS Series Microcontroller Technical Reference Manual (TMS570 Tech Ref_spnu489.pdf)


# Configuration Settings


## Il_Dbkom Configuration


## Tx Messages


### D_RS_EPS


# Known Issues / Limitations With Configuration

The configuration is only partially documented due to lack of time.


# Revision Control Log


**Table 1**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| Configurable Options | Configurable Options | Configurable Options |
| User Config File | None | Default setting |
| Write access to rx buffer | Write access to rx buffer | Write access to rx buffer |
| Byte | No | Default setting |
| Word | No | Default setting |
| nByte | No | Default setting |
| Timing parameters | Timing parameters | Timing parameters |
| Start Delay Time Area [ms] | 200 | Default setting |
| Channel0 | Channel0 | Channel0 |
| TxCycle | 2 | 2ms is a common factor of the transmission rates 10ms and 100ms and also ensures that the message trigger jitter is less than the required +/- 5ms. |
| RxCycle | 10 | Default setting |
| Transceiver Settings | Transceiver Settings | Transceiver Settings |
| Transceiver Config File | None | Default setting |


**Table 2**

| Attribute Name | Value | Rationale |
| --- | --- | --- |
| D_RS_EPS | D_RS_EPS | D_RS_EPS |
| Generate | Yes | Default setting |
| Start delay time [ms] | n/a |  |
| ECU_APPL_EPS | ECU_APPL_EPS | ECU_APPL_EPS |
| Generate | Yes | Default setting |
| Start delay time [ms] | n/a |  |
| EPS_1 | EPS_1 | EPS_1 |
| Generate | Yes | Required tx message |
| Start delay time [ms] | 0 | Arbitrarily set to 0, however, the time between this 10ms cyclic message and the EPS_A1 100ms cyclic message must be greater than 2 ms. |
| EPS_A1 | EPS_A1 | EPS_A1 |
| Generate | Yes | Required tx message |
| Start delay time [ms] | 4 | 5ms offset is the optimal spacing for offsetting this message from EPS_1. The current system tick is 2ms, so 4ms was selected. 4ms provides a guaranteed 2ms message spacing even under extreme jitter. |
| NM_EPS | NM_EPS | NM_EPS |
| Generate | Yes | Default setting |
| Start delay time [ms] | n/a |  |
| SD_RS_EPS | SD_RS_EPS | SD_RS_EPS |
| Generate | Yes | Default setting |
| Start delay time [ms] | 0 | Default setting |


**Table 3**

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Creation | 30JUL13 | JJW |
|  |  |  |  |  |
