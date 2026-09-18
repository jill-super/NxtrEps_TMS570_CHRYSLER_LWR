---
title: "Software Integration Package Version Check (SipVersionCheck)"
description: "Software Integration Package Version Check (SipVersionCheck) — SIP version-consistency check (Vector)."
---


# Software Integration Package Version Check (`SipVersionCheck`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

*Software Integration Package Version Check* (`SipVersionCheck`) — SIP version-consistency check (Vector). Verifies that the integrated Software Integration Package versions match at build time.


Copyright headers found in sources reference: Texas Instruments, Vector Informatik.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/SipVersionCheck/` contains 3 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/SipVersionCheck/sip_vers.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/SipVersionCheck/sip_vers.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/SipVersionCheck/v_ver.h` |

## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
