---
title: "TMS570 Startup Sequencing (TMS570_Startup)"
description: "TMS570 Startup Sequencing (TMS570_Startup) — Application Startup Sequence"
---


# TMS570 Startup Sequencing (`TMS570_Startup`)

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> **Origin:** Nexteer in-house developed code. The file frame/RTE boilerplate is produced by the Vector MICROSAR RTE Generator (see Generated at / Generator header lines); the control logic itself is project-owned.

## Purpose

*TMS570 Startup Sequencing* (`TMS570_Startup`) — Application Startup Sequence


Copyright headers found in sources reference: Nexteer Automotive.


## Key files


| File | Role |
| --- | --- |
| `TMS570_Startup/src/AppStartup.c` | Implementation |
| `TMS570_Startup/src/BootStartup.c` | Implementation |
| `TMS570_Startup/src/ResetCause.c` | Implementation |
| `TMS570_Startup/src/fiqintvect.asm` | Assembly |
| `TMS570_Startup/src/sys_core.asm` | Assembly |
| `TMS570_Startup/src/sys_memory.asm` | Assembly |
| `TMS570_Startup/src/sys_startup.c` | Implementation |
| `TMS570_Startup/include/ResetCause.h` | Public interface |
| `TMS570_Startup/include/sys_core.h` | Public interface |
| `TMS570_Startup/include/sys_memory.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `system_regs.h`
- `esm_regs.h`
- `efc_regs.h`
- `stc_regs.h`
- `pbist_regs.h`
- `mibspi_regs.h`
- `n2het_regs.h`
- `adc_regs.h`
- `htu_regs.h`
- `dcan_regs.h`
- `dma_regs.h`
- `vim_regs.h`
- `flash_regs.h`
- `pcr_regs.h`
- `tcram_regs.h`
- `ccm_regs.h`
- `gio_regs.h`
- `appinit_cfg.h`
- `ResetCause.h`
- `sys_core.h`
- `uDiag.h`
- `Platform_Types.h`
- `Compiler.h`
- `MemMap.h`
- `sys_memory.h`
- `startup_cfg.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [TMS570 Startup BootStartup](./doc-tms570-startup-bootstartup-mdd/) `(TMS570_Startup_BootStartup_MDD.docx)`
- [TMS570 Startup FiqIntVect](./doc-tms570-startup-fiqintvect-mdd/) `(TMS570_Startup_FiqIntVect_MDD.docx)`
- [TMS570 Startup Integration Manual](./doc-tms570-startup-integration-manual/) `(TMS570_Startup_Integration_Manual.docx)`
- [TMS570 Startup SysCore](./doc-tms570-startup-syscore-mdd/) `(TMS570_Startup_SysCore_MDD.docx)`
- [TMS570 Startup SysStartup](./doc-tms570-startup-sysstartup-mdd/) `(TMS570_Startup_SysStartup_MDD.docx)`
- [spna106a](./doc-spna106a/) `(spna106a.pdf)`
