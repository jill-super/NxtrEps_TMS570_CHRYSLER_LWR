---
title: "Controller Area Network Driver (Can)"
description: "Controller Area Network Driver (Can) — MCAL CAN driver (Vector MICROSAR DrvCan) for the TMS570 DCAN peripheral."
---


# Controller Area Network Driver (`Can`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Controller Area Network Driver* (`Can`) — MCAL CAN driver (Vector MICROSAR DrvCan) for the TMS570 DCAN peripheral. Implements the AUTOSAR CAN driver: baud-rate/bus timing, hardware-object handling, transmit/receive via the DCAN controller, error-state handling. Configured with the Vector DaVinci toolchain.


Copyright headers found in sources reference: Texas Instruments, Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Can/` contains 3 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Can/_can_inc.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Can/can_def.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Can/can_drv.c` |

## Design documents

- [HLDD: Can configuration](../../general/vector-config/doc-drvcan/)


## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
