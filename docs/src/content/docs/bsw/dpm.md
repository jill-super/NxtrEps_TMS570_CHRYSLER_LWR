---
title: "Diagnostic Protocol Manager (Dpm)"
description: "Diagnostic Protocol Manager support (Vector)."
---


# Diagnostic Protocol Manager (`Dpm`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Diagnostic Protocol Manager support (Vector). Supports diagnostic session/protocol handling for the EPS ECU.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dpm/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dpm/dpm.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Dpm/dpm.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
