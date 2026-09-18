---
title: "Microcontroller Unit Driver (Mcu)"
description: "MCAL Microcontroller Unit driver (Vector Mcu)."
---


# Microcontroller Unit Driver (`Mcu`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Microcontroller Unit Driver* (`Mcu`) — MCAL Microcontroller Unit driver (Vector Mcu). Clock/PLL setup, mode switching and reset handling for the TMS570.


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Mcu/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Mcu/Mcu.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Mcu/Mcu.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
