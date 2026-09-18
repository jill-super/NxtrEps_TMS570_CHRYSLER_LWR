---
title: "Interaction Layer (Il)"
description: "Interaction Layer (Vector IL, signal-based COM abstraction)."
---


# Interaction Layer (`Il`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Interaction Layer (Vector IL, signal-based COM abstraction). Maps application signals to PDUs for transmission/reception on CAN.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Il/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Il/can_dbk.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Il/dbk_def.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
