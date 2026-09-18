---
title: "Watchdog Manager (WdgM)"
description: "Watchdog Manager (Vector WdgM) with generated alive/supervision graph."
---


# Watchdog Manager (`WdgM`)

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR basic-software module, configured for this project with the DaVinci Configurator. Do not hand-edit generated files — change the DaVinci / Electronic Control Unit configuration and regenerate.

## Purpose

Watchdog Manager (Vector WdgM) with generated alive/supervision graph. Supervises application checkpoints (`Rte_Call_..._CheckpointReached`) and triggers safe reactions; see the generated `WdgM_Graph.pdf` under General documents.


## Key files


`Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgM/` contains 4 source/header file(s). Sample:

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM_Cfg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM_Checkpoint.c` |

## Design documents

- [WdgM supervision graph (generated PDF)](../../general/vector-config/doc-wdgm-graph/) — generated entity graph.
- [WdgM HLDD](../../general/vector-config/doc-wdgm/) — high-level design description.


## Usage

Application Software Components never call this module directly; they use RTE ports, the IoHwAb, or service APIs (e.g. `NvM_ReadBlock`, `Dem_ReportErrorStatus`). Configuration lives in the DaVinci project; generated artefacts land in `SwProject/Source/GenData*`.
