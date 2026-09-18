---
title: "Watchdog Interface (WdgIf)"
description: "Watchdog Interface (AUTOSAR WdgIf, Vector)."
---


# Watchdog Interface (`WdgIf`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Watchdog Interface (AUTOSAR WdgIf, Vector). Routes supervision requests from the WdgM to the hardware watchdog driver(s).


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgIf/` contains 4 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgIf/WdgIf.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgIf/WdgIf.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgIf/WdgIf_Cfg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgIf/WdgIf_Types.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
