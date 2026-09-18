---
title: "Diagnostic Event Manager (Dem)"
description: "Diagnostic Event Manager (Vector MICROSAR Dem)."
---


# Diagnostic Event Manager (`Dem`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Diagnostic Event Manager (Vector MICROSAR Dem). Central AUTOSAR Dem: event debouncing, DTC storage, status bits, FreezeFrames, and the interface used by `Ap_DiagMgr_DemIf`.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dem/` contains 3 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dem/SchM_Dem.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dem/dem.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dem/dem.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
