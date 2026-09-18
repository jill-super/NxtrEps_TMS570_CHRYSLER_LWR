---
title: "Non-Volatile Memory Proxy (NvMProxy)"
description: "Non-Volatile Memory Proxy (NvMProxy) — Complex Driver NvMProxy which acts as a proxy between"
---


# Non-Volatile Memory Proxy (`NvMProxy`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*Non-Volatile Memory Proxy* (`NvMProxy`) — Complex Driver NvMProxy which acts as a proxy between


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `NvMProxy/src/Cd_NvMProxy.c` | Implementation |
| `NvMProxy/include/Cd_NvMProxy.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Std_Types.h`
- `Cd_NvMProxy.h`
- `NvM.h`
- `SchM_NvMProxy.h`
- `Crc.h`
- `MemMap.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [NvMProxy Integration Manual](./doc-nvmproxy-integration-manual/) `(NvMProxy_Integration_Manual.docx)`
- [NvMProxy](./doc-nvmproxy-mdd/) `(NvMProxy_MDD.docx)`


## Other artefacts (not converted)

- `NvMProxy/doc/NvMProxy_Design_Review.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `NvMProxy/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
