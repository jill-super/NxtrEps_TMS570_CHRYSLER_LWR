---
title: "Transport Protocol (Tp)"
description: "Transport Protocol — CanTp (Vector)."
---


# Transport Protocol (`Tp`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Transport Protocol — CanTp (Vector). Segmentation/reassembly (ISO 15765-2) for UDS diagnostics and flashing.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Tp/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Tp/tpmc.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Tp/tpmc.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
