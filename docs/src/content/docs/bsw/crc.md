---
title: "Cyclic Redundancy Check Library (Crc)"
description: "Cyclic Redundancy Check Library (Crc) — AUTOSAR CRC library (Vector VStdLib-family)."
---


# Cyclic Redundancy Check Library (`Crc`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Cyclic Redundancy Check Library* (`Crc`) — AUTOSAR CRC library (Vector VStdLib-family). Provides CRC8/16/32 routines used by E2E protection, NvM and communication stacks.


Copyright headers found in sources reference: MICROSAR, Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Crc/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Crc/Crc.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Crc/Crc.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
