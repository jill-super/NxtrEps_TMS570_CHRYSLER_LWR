---
title: "Watchdog Driver (Wdg)"
description: "MCAL Watchdog driver (Vector Wdg)."
---


# Watchdog Driver (`Wdg`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Watchdog Driver* (`Wdg`) — MCAL Watchdog driver (Vector Wdg). Hardware watchdog triggering on the TMS570.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/` contains 6 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg_Cfg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg_TMS570LS3x.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg_TMS570LS3x.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg_TMS570LS3x_Cfg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Wdg/Wdg_TMS570LS3x_reg_defs.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
