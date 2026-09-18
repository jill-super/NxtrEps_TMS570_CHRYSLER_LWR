---
title: "Digital Input-Output Driver (Dio)"
description: "Digital Input-Output Driver (Dio) — MCAL Digital I/O driver (Vector Dio)."
---


# Digital Input-Output Driver (`Dio`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Digital Input-Output Driver* (`Dio`) — MCAL Digital I/O driver (Vector Dio). Channel/group/port read-write services on TMS570 GPIOs.


Copyright headers found in sources reference: MICROSAR, Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dio/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dio/Dio.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dio/Dio.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
