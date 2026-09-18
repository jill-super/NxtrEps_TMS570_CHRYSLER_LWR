---
title: "Non-Volatile Memory Manager (NvMMgr)"
description: "Non-Volatile Memory Manager (NvMMgr) — Fee interface module"
---


# Non-Volatile Memory Manager (`NvMMgr`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Non-Volatile Memory Manager* (`NvMMgr`) — Fee interface module


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `NvMMgr/src/Cd_FeeIf.c` | Implementation |
| `NvMMgr/src/Fapi_UserDefinedFunctions.c` | Implementation |
| `NvMMgr/include/Cd_FeeIf.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Cd_FeeIf.h`
- `F021.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Fee Interface](./doc-fee-interface-mdd/) `(Fee_Interface_MDD.docx)`
- [NvMMgr Integration Manual](./doc-nvmmgr-integration-manual/) `(NvMMgr_Integration_Manual.docx)`
