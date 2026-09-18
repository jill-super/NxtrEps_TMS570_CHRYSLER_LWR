---
title: "Handwheel Input Qualification (WIRInputQual)"
description: "Handwheel Input Qualification (WIRInputQual) — WIR (wheel-input-rotation / handwheel input) qualification: plausibility-checks and qualifies handwheel-related inputs before use by assist functions."
---


# Handwheel Input Qualification (`WIRInputQual`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house application component, integrated in the `Chrysler_LWR_EPS_TMS570/SwProject` Electronic Control Unit project (Vector MICROSAR RTE frame; control logic is project-owned).

## Purpose

*Handwheel Input Qualification* (`WIRInputQual`) — WIR (wheel-input-rotation / handwheel input) qualification: plausibility-checks and qualifies handwheel-related inputs before use by assist functions.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/` — implementation:

- `Chrysler_LWR_EPS_TMS570/SwProject/WIRInputQual/src/Ap_WIRInputQual.c`

## Runnable entities

- `WIRInputQual_Per1`

## Usage

Scheduled by the Runtime Environment (RTE) like any other application SW-C; communicates with the Communication / Interaction Layer stack and the core EPS components via RTE ports. Generation/integration scripts are in the component `generate/` and `tools/` folders; test stubs in `utp/contract/`.


## Design documents

- [WIR Input Qualification](./doc-wir-input-qualification-mdd/) `(WIR_Input_Qualification_MDD.docx)`
