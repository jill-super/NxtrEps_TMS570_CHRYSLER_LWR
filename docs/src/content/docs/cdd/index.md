---
title: "Complex Device Drivers"
description: "Hardware-near drivers that bypass or extend standard AUTOSAR abstractions: Analog-to-Digital Converter, Pulse-Width Modulation / Enhanced Pulse-Width Modulation, Non-Volatile Memory proxy, Flash self-test, startup code. All Nexteer in-house "
sidebar:
  order: 0
---

# Complex Device Drivers

Hardware-near drivers that bypass or extend standard AUTOSAR abstractions: Analog-to-Digital Converter, Pulse-Width Modulation / Enhanced Pulse-Width Modulation, Non-Volatile Memory proxy, Flash self-test, startup code. All Nexteer in-house except TI-licensed Flash/FEE pieces where noted.

> Naming: titles lead with the descriptive long name; the short Complex Driver folder name (for example `Adc`) follows in parentheses.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Analog-to-Digital Converter Driver (`Adc`)](./adc/) | Custom | Analog-to-Digital Converter Unit 1 Complex Device Driver |
| [Enhanced Pulse-Width Modulation Driver (`ePWM`)](./epwm/) | Custom | AUTOSAR software component `Ap_ePWM2` for the Chrysler LWR EPS — design coverage: NHetRegisters; Nhet 1. |
| [Non-Volatile Memory Manager (`NvMMgr`)](./nvmmgr/) | Custom | Flash EEPROM Emulation interface module |
| [Non-Volatile Memory Proxy (`NvMProxy`)](./nvmproxy/) | Custom | Complex Driver Non-Volatile Memory Proxy which acts as a proxy between Non-Volatile Memory Manager and application |
| [Space-Vector Motor Driver – Current Mode (`SVDrvr_CM`)](./svdrvr-cm/) | Custom | Non-AUTOSAR Pulse-Width Modulation driver required to perform Electric Power Steering motor control |
| [TMS570 Startup Sequencing (`TMS570_Startup`)](./tms570-startup/) | Custom | Application Startup Sequence |
| [TMS570 Micro Diagnostics (`TMS570_uDiag`)](./tms570-udiag/) | Custom | Data and Prefetch Abort Handler |
