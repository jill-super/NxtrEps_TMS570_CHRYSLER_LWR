---
title: "Controller Area Network Driver (Can)"
description: "Controller Area Network Driver (Can) — AUTOSAR software component `Can` for the Chrysler LWR EPS system on the TMS570."
---


# Controller Area Network Driver (`Can`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Controller Area Network Driver* (`Can`) — AUTOSAR software component `Can` for the Chrysler LWR EPS system on the TMS570.


## Key files


No `src/`/`include/` files at top level — see the sub-pages and repository tree.


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.
