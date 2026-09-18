---
title: "Communication Control (Ccl)"
description: "Communication Control (Vector CCL) over the MICROSAR Communication stack."
---


# Communication Control (`Ccl`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Communication Control (Vector CCL) over the MICROSAR Communication stack. Manages communication states and PDU-group control for the EPS ECU.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Ccl/` contains 3 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Ccl/ccl.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Ccl/ccl.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Ccl/ccl_inc.h` |

## Design documents

- [HLDD: Ccl configuration](../../general/vector-config/doc-ccl/)


## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
