---
title: "General-Purpose Timer Driver (Gpt)"
description: "General-Purpose Timer Driver (Gpt) — MCAL General Purpose Timer driver (Vector Gpt)."
---


# General-Purpose Timer Driver (`Gpt`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*General-Purpose Timer Driver* (`Gpt`) — MCAL General Purpose Timer driver (Vector Gpt). Timer channels, one-shot/continuous modes and notifications on the TMS570.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Gpt/` contains 4 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Gpt/Gpt.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Gpt/Gpt.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Gpt/Gpt_Irq.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Gpt/Gpt_Irq.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
