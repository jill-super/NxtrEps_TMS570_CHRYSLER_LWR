---
title: "Electronic Control Unit State Manager (EcuM)"
description: "Electronic Control Unit State Manager (EcuM) — ECU State Manager (Vector MICROSAR EcuM)."
---


# Electronic Control Unit State Manager (`EcuM`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Electronic Control Unit State Manager* (`EcuM`) — ECU State Manager (Vector MICROSAR EcuM). Manages ECU startup, shutdown, sleep and wake-up states, calling integration callouts such as `EcuM_Callout_Stubs.c`.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/EcuM/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/EcuM/EcuM.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/EcuM/EcuM.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
