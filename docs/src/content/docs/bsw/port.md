---
title: "Port Pin Driver (Port)"
description: "Port Pin Driver (Port) — MCAL Port driver (Vector Port)."
---


# Port Pin Driver (`Port`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Port Pin Driver* (`Port`) — MCAL Port driver (Vector Port). Pin multiplexing and direction configuration for the TMS570 package.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Port/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Port/Port.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Port/Port.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
