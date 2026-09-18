---
title: "Input-Output Hardware Abstraction (IoHwAb)"
description: "Input-Output Hardware Abstraction (IoHwAb) — I/O Hardware Abstraction (project-specific `IoHwAb.c` on a Vector IoHwAb frame)."
---


# Input-Output Hardware Abstraction (`IoHwAb`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Input-Output Hardware Abstraction* (`IoHwAb`) — I/O Hardware Abstraction (project-specific `IoHwAb.c` on a Vector IoHwAb frame). ECU-abstraction access to sensors/actuators (ADC results, PWM duty, GPIOs) for the application SW-Cs.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/IoHwAb/` contains 1 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/IoHwAb/IoHwAb.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
