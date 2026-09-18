---
title: "Diagnostic Communication Stack (Diag)"
description: "Diagnostic communication stack (Vector, UDS)."
---


# Diagnostic Communication Stack (`Diag`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Diagnostic Communication Stack* (`Diag`) — Diagnostic communication stack (Vector, UDS). Implements UDS services on CAN used by manufacturing and service tools together with `CMS_Common`.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Diag/` contains 1 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Diag/mindiag.c` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
