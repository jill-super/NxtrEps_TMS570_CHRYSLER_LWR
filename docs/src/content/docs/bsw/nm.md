---
title: "Network Management (Nm)"
description: "Network Management (CanNm/OsekNm configuration, Vector)."
---


# Network Management (`Nm`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Network Management (CanNm/OsekNm configuration, Vector). Coordinated bus sleep/wake-up for the vehicle network.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/` contains 6 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/n_onm.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/n_onmdef.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/nm_basic.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/nm_basic.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/onmxdc.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Nm/onmxdc.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
