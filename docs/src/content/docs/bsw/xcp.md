---
title: "Universal Measurement and Calibration Protocol (Xcp)"
description: "Universal Measurement and Calibration Protocol (Xcp) — BSW XCP slave stack (Vector XCP)."
---


# Universal Measurement and Calibration Protocol (`Xcp`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Universal Measurement and Calibration Protocol* (`Xcp`) — BSW XCP slave stack (Vector XCP). Measurement/calibration protocol slave used together with the `Ap_ApXcp` application component and `CMS_Common` services.


Copyright headers found in sources reference: Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/` contains 6 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/XcpProf.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/XcpProf.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/_xcp_appl.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/xcp_appl.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/xcp_can.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Xcp/xcp_can.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
