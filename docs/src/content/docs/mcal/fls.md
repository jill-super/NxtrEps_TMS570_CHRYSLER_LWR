---
title: "Flash Memory Driver (Fls)"
description: "Flash Memory Driver (Fls) — AUTOSAR software component `Fls` for the Chrysler LWR EPS — design coverage: F021 Flash API License Agreement; Release Notes."
---


# Flash Memory Driver (`Fls`)

<span class="origin-badge origin-ti">TI-provided</span>

> **Origin:** Driver code is Texas Instruments proprietary (FEE driver / F021 Flash API). Redistribution and use are governed by the TI license accompanying the files — see the module folder.

## Purpose

*Flash Memory Driver* (`Fls`) — AUTOSAR software component `Fls` for the Chrysler LWR EPS — design coverage: F021 Flash API License Agreement; Release Notes.


Copyright headers found in sources reference: Texas Instruments.


## Key files


| File | Role |
| --- | --- |
| `Fls/src/F021_API_CortexR4_BE_V3D16.lib` | Source |
| `Fls/include/CGT.ARM.h` | Public interface |
| `Fls/include/CGT.CCS.h` | Public interface |
| `Fls/include/CGT.GHS.h` | Public interface |
| `Fls/include/CGT.IAR.h` | Public interface |
| `Fls/include/CGT.gcc.h` | Public interface |
| `Fls/include/Compatibility.h` | Public interface |
| `Fls/include/Constants.h` | Public interface |
| `Fls/include/F021.h` | Public interface |
| `Fls/include/FapiFunctions.h` | Public interface |
| `Fls/include/Helpers.h` | Public interface |
| `Fls/include/Registers.h` | Public interface |
| `Fls/include/Registers_FMC_BE.h` | Public interface |
| `Fls/include/Registers_FMC_LE.h` | Public interface |
| `Fls/include/Types.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [F021 Flash API License Agreement](./doc-f021-flash-api-license-agreement/) `(F021_Flash_API_License_Agreement.pdf)`
- [Release Notes](./doc-release-notes/) `(Release_Notes.pdf)`
- [SPNA148](./doc-spna148/) `(SPNA148.pdf)`
- [SPNU501F](./doc-spnu501f/) `(SPNU501F.pdf)`
- [SPNZ210](./doc-spnz210/) `(SPNZ210.pdf)`
- [build information](./doc-build-information/) `(build_information.txt)`
- [readme](./doc-readme/) `(readme.txt)`
