---
title: "Nexteer Mathematics and Filter Library (NxtrLib)"
description: "Nexteer Mathematics and Filter Library (NxtrLib) — This file contains the checksum functions"
---


# Nexteer Mathematics and Filter Library (`NxtrLib`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Nexteer Mathematics and Filter Library* (`NxtrLib`) — This file contains the checksum functions


## Key files


| File | Role |
| --- | --- |
| `NxtrLib/src/CheckSums.c` | Implementation |
| `NxtrLib/src/SystemTime.c` | Implementation |
| `NxtrLib/src/atan2.asm` | Assembly |
| `NxtrLib/src/atan2_octants.c` | Implementation |
| `NxtrLib/src/filters.c` | Implementation |
| `NxtrLib/src/interpolation.c` | Implementation |
| `NxtrLib/include/CheckSums.h` | Public interface |
| `NxtrLib/include/Filter_Types.h` | Public interface |
| `NxtrLib/include/GlobalMacro.h` | Public interface |
| `NxtrLib/include/SystemTime.h` | Public interface |
| `NxtrLib/include/atan2.h` | Public interface |
| `NxtrLib/include/filters.h` | Public interface |
| `NxtrLib/include/fixmath.h` | Public interface |
| `NxtrLib/include/fpmtype.h` | Public interface |
| `NxtrLib/include/interpolation.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `CheckSums.h`
- `fpmtype.h`
- `fixmath.h`
- `Rte_NexteerLibs.h`
- `SystemTime.h`
- `GlobalMacro.h`
- `Gpt.h`
- `Gpt_Cfg.h`
- `SystemTime_Cfg.h`
- `MemMap.h`
- `Std_Types.h`
- `filters.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [Filter Library Design Document](./doc-filter-library-design-document/) `(Filter_Library_Design_Document.doc)`
- [Interpolation Design](./doc-interpolation-design-mdd/) `(Interpolation_Design_MDD.doc)`
- [NxtrLib Systemtime Integration Manual](./doc-nxtrlib-systemtime-integration-manual/) `(NxtrLib_Systemtime Integration_Manual.docx)`
