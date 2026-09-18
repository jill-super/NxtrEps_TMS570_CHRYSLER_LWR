---
title: "Microcontroller Abstraction Layer"
description: "Lowest hardware-abstraction drivers for the TMS570: Vector Microcontroller Abstraction Layer modules plus Texas Instruments-provided memory drivers (Flash EEPROM Emulation, F021 Flash Application Programming Interface)."
sidebar:
  order: 0
---

# Microcontroller Abstraction Layer

Lowest hardware-abstraction drivers for the TMS570: Vector Microcontroller Abstraction Layer modules plus Texas Instruments-provided memory drivers (Flash EEPROM Emulation, F021 Flash Application Programming Interface).

> Naming: titles lead with the descriptive long name; the short Microcontroller Abstraction Layer module name follows in parentheses.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Controller Area Network Driver (`Can`)](./can/) | Custom | AUTOSAR software component `Can` for the Chrysler LWR EPS system on the TMS570. |
| [Flash EEPROM Emulation Driver (`Fee`)](./fee/) | TI | AUTOSAR software component `Fee` for the Chrysler LWR EPS — design coverage: AutoSAR FEE Parameter Configuration; AutoSAR FEE User Guide. |
| [Flash Memory Driver (`Fls`)](./fls/) | TI | AUTOSAR software component `Fls` for the Chrysler LWR EPS — design coverage: F021 Flash Application Programming Interface License Agreement; Release Notes. |
