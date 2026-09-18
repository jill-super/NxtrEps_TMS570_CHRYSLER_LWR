---
title: "Vector Standard Library (VStdLib)"
description: "Vector standard library."
---


# Vector Standard Library (`VStdLib`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Vector Standard Library* (`VStdLib`) — Vector standard library. Compiler-independent integer/bit utilities shared by the MICROSAR stack.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/VStdLib/` contains 2 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/VStdLib/vstdlib.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/VStdLib/vstdlib.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
