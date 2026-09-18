---
title: "Vehicle Power Mode Management (VehPwrMd)"
description: "Vehicle Power Mode Management (VehPwrMd) — Vehicle power-mode management: evaluates ignition/power-mode state and distributes it to the application (startup/shutdown coordination)."
---


# Vehicle Power Mode Management (`VehPwrMd`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house application component, integrated in the `Chrysler_LWR_EPS_TMS570/SwProject` Electronic Control Unit project (Vector MICROSAR RTE frame; control logic is project-owned).

## Purpose

*Vehicle Power Mode Management* (`VehPwrMd`) — Vehicle power-mode management: evaluates ignition/power-mode state and distributes it to the application (startup/shutdown coordination).


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/VehPwrMd/` — implementation:

- `Chrysler_LWR_EPS_TMS570/SwProject/VehPwrMd/src/Ap_VehPwrMd.c`

## Runnable entities

- `VehPwrMd_Init1`
- `VehPwrMd_Per1`

## Usage

Scheduled by the Runtime Environment (RTE) like any other application SW-C; communicates with the Communication / Interaction Layer stack and the core EPS components via RTE ports. Generation/integration scripts are in the component `generate/` and `tools/` folders; test stubs in `utp/contract/`.


## Design documents

- [VehiclePowerMode](./doc-vehiclepowermode-mdd/) `(VehiclePowerMode_MDD.docx)`
