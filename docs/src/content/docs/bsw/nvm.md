---
title: "Non-Volatile Memory Manager (NvM)"
description: "Non-Volatile Memory Manager (NvM) — NVRAM Manager (Vector MICROSAR NvM)."
---


# Non-Volatile Memory Manager (`NvM`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Non-Volatile Memory Manager* (`NvM`) — NVRAM Manager (Vector MICROSAR NvM). Block-based non-volatile data management on top of MemIf/Fee; used via `Cd_NvMProxy`/`Cd_FeeIf`.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/` contains 14 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Act.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Act.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Cbk.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Crc.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Crc.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_JobProc.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_JobProc.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Qry.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Qry.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Queue.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Queue.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Types.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
