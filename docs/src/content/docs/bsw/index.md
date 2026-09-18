---
title: "Basic Software — Services and Electronic Control Unit Abstraction"
description: "Vector MICROSAR service, communication and Electronic Control Unit abstraction modules, configured with DaVinci. Do not hand-edit generated files."
sidebar:
  order: 0
---

# Basic Software — Services and Electronic Control Unit Abstraction

Vector MICROSAR service, communication and Electronic Control Unit abstraction modules, configured with DaVinci. Do not hand-edit generated files.

> Naming: titles lead with the descriptive long name; the short Basic Software module name (for example `Can` Controller Area Network Driver) follows in parentheses. `BSW:` marks Vector MICROSAR Basic Software under `SwProject/Source/BSW/`.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Controller Area Network Driver (`Can`)](./can/) | Vector | Microcontroller Abstraction Layer Controller Area Network driver (Vector MICROSAR DrvCan) for the TMS570 DCAN peripheral. |
| [Communication Control (`Ccl`)](./ccl/) | Vector | Communication Control (Vector CCL) over the MICROSAR Communication stack. |
| [Cyclic Redundancy Check Library (`Crc`)](./crc/) | Vector | AUTOSAR Cyclic Redundancy Check library (Vector Standard Library family). |
| [Diagnostic Event Manager (`Dem`)](./dem/) | Vector | Diagnostic Event Manager (Vector MICROSAR Dem). |
| [Development Error Tracer (`Det`)](./det/) | Vector | Development Error Tracer (Vector Det). |
| [Diagnostic Communication Stack (`Diag`)](./diag/) | Vector | Diagnostic communication stack (Vector, Unified Diagnostic Services). |
| [Digital Input-Output Driver (`Dio`)](./dio/) | Vector | Microcontroller Abstraction Layer Digital Input-Output driver (Vector Dio). |
| [Diagnostic Protocol Manager (`Dpm`)](./dpm/) | Vector | Diagnostic Protocol Manager support (Vector). |
| [Electronic Control Unit State Manager (`EcuM`)](./ecum/) | Vector | Electronic Control Unit State Manager (Vector MICROSAR Electronic Control Unit State Manager). |
| [General-Purpose Timer Driver (`Gpt`)](./gpt/) | Vector | Microcontroller Abstraction Layer General-Purpose Timer driver (Vector Gpt). |
| [Interaction Layer (`Il`)](./il/) | Vector | Interaction Layer (Vector IL, signal-based Communication abstraction). |
| [Input-Output Hardware Abstraction (`IoHwAb`)](./iohwab/) | Vector | Input-Output Hardware Abstraction (project-specific `IoHwAb.c` on a Vector IoHwAb frame). |
| [Microcontroller Unit Driver (`Mcu`)](./mcu/) | Vector | Microcontroller Abstraction Layer Microcontroller Unit driver (Vector Mcu). |
| [Memory Abstraction Interface (`MemIf`)](./memif/) | Vector | Memory Abstraction Interface (AUTOSAR MemIf, Vector). |
| [Network Management (`Nm`)](./nm/) | Vector | Network Management (Controller Area Network Network Management / OSEK Network Management configuration, Vector). |
| [Non-Volatile Memory Manager (`NvM`)](./nvm/) | Vector | Non-Volatile Memory Manager (Vector MICROSAR Non-Volatile Memory Manager). |
| [Port Pin Driver (`Port`)](./port/) | Vector | Microcontroller Abstraction Layer Port Pin driver (Vector Port). |
| [Software Integration Package Version Check (`SipVersionCheck`)](./sipversioncheck/) | Vector | Software Integration Package version-consistency check (Vector). |
| [Transport Protocol (`Tp`)](./tp/) | Vector | Transport Protocol — Controller Area Network Transport Protocol (Vector). |
| [Vector Standard Library (`VStdLib`)](./vstdlib/) | Vector | Vector standard library. |
| [Watchdog Driver (`Wdg`)](./wdg/) | Vector | Microcontroller Abstraction Layer Watchdog driver (Vector Wdg). |
| [Watchdog Interface (`WdgIf`)](./wdgif/) | Vector | Watchdog Interface (AUTOSAR WdgIf, Vector). |
| [Watchdog Manager (`WdgM`)](./wdgm/) | Vector | Watchdog Manager (Vector WdgM) with generated alive/supervision graph. |
| [Universal Measurement and Calibration Protocol (`Xcp`)](./xcp/) | Vector | Basic Software Universal Measurement and Calibration Protocol slave stack (Vector). |
