---
title: "Standard Type Definitions (StdDef)"
description: "Standard Type Definitions (StdDef) — AUTOSAR software component `StdDef` for the Chrysler LWR EPS system on the TMS570."
---


# Standard Type Definitions (`StdDef`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Standard Type Definitions* (`StdDef`) — AUTOSAR software component `StdDef` for the Chrysler LWR EPS system on the TMS570.


Copyright headers found in sources reference: Vector Informatik.


## Key files


| File | Role |
| --- | --- |
| `StdDef/include/Compiler.h` | Public interface |
| `StdDef/include/Platform_Types.h` | Public interface |
| `StdDef/include/Std_Types.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.
