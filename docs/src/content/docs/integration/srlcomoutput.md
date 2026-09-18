---
title: "Serial Communication Output Conditioning (SrlComOutput)"
description: "Serial Communication Output Conditioning (SrlComOutput) — Serial-communication output: packs EPS internal signals into transmit messages for the vehicle network."
---


# Serial Communication Output Conditioning (`SrlComOutput`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house application component, integrated in the `Chrysler_LWR_EPS_TMS570/SwProject` Electronic Control Unit project (Vector MICROSAR RTE frame; control logic is project-owned).

## Purpose

*Serial Communication Output Conditioning* (`SrlComOutput`) — Serial-communication output: packs EPS internal signals into transmit messages for the vehicle network.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/` — implementation:

- `Chrysler_LWR_EPS_TMS570/SwProject/SrlComOutput/src/Ap_SrlComOutput.c`

## Runnable entities

- `SrlComOutput_Init1`
- `SrlComOutput_Per1`

## Usage

Scheduled by the Runtime Environment (RTE) like any other application SW-C; communicates with the Communication / Interaction Layer stack and the core EPS components via RTE ports. Generation/integration scripts are in the component `generate/` and `tools/` folders; test stubs in `utp/contract/`.


## Design documents

- [Serial Communication Output](./doc-serial-communication-output-mdd/) `(Serial_Communication_Output_MDD.doc)`
