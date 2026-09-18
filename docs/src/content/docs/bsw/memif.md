---
title: "Memory Abstraction Interface (MemIf)"
description: "Memory Abstraction Interface (AUTOSAR MemIf, Vector)."
---


# Memory Abstraction Interface (`MemIf`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Memory Abstraction Interface (AUTOSAR MemIf, Vector). Abstracts Fee/Ea devices behind a uniform block-device API used by NvM.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/MemIf/` contains 3 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf_Types.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
