---
title: "Serial Communication Input Conditioning (SrlComInput)"
description: "Serial Communication Input Conditioning (SrlComInput) — Serial-communication input conditioning: receives vehicle messages (e.g. vehicle speed, engine signals) from the Communication stack and qualifies them for the "
---


# Serial Communication Input Conditioning (`SrlComInput`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house application component, integrated in the `Chrysler_LWR_EPS_TMS570/SwProject` Electronic Control Unit project (Vector MICROSAR RTE frame; control logic is project-owned).

## Purpose

*Serial Communication Input Conditioning* (`SrlComInput`) — Serial-communication input conditioning: receives vehicle messages (e.g. vehicle speed, engine signals) from the Communication stack and qualifies them for the application.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/` — implementation:

- `Chrysler_LWR_EPS_TMS570/SwProject/SrlComInput/src/Ap_SrlComInput.c`

## Runnable entities

- `FaultInjection_FltInjection`
- `HaLFState_SCom_Transition`
- `PrkAssistState_SCom_Transition`
- `SrlComInput_Init`
- `SrlComInput_Per1`

## Usage

Scheduled by the Runtime Environment (RTE) like any other application SW-C; communicates with the Communication / Interaction Layer stack and the core EPS components via RTE ports. Generation/integration scripts are in the component `generate/` and `tools/` folders; test stubs in `utp/contract/`.


## Design documents

- [Serial Communication Input](./doc-serial-communication-input-mdd/) `(Serial_Communication_Input_MDD.doc)`
