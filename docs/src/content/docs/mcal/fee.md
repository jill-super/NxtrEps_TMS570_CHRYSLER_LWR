---
title: "Flash EEPROM Emulation Driver (Fee)"
description: "Flash EEPROM Emulation Driver (Fee) — AUTOSAR software component `Fee` for the Chrysler LWR EPS — design coverage: AutoSAR FEE Parameter Configuration; AutoSAR FEE User Guide."
---


# Flash EEPROM Emulation Driver (`Fee`)

<span class="origin-badge origin-ti">TI-provided</span>

> **Origin:** Driver code is Texas Instruments proprietary (FEE driver / F021 Flash API). Redistribution and use are governed by the TI license accompanying the files — see the module folder.

## Purpose

*Flash EEPROM Emulation Driver* (`Fee`) — AUTOSAR software component `Fee` for the Chrysler LWR EPS — design coverage: AutoSAR FEE Parameter Configuration; AutoSAR FEE User Guide.


Copyright headers found in sources reference: Texas Instruments.


## Key files


| File | Role |
| --- | --- |
| `Fee/src/Device_TMS570LS07.c` | Implementation |
| `Fee/src/Device_TMS570LS12.c` | Implementation |
| `Fee/src/fee.c` | Implementation |
| `Fee/src/ti_fee_Info.c` | Implementation |
| `Fee/src/ti_fee_cancel.c` | Implementation |
| `Fee/src/ti_fee_eraseimmediateblock.c` | Implementation |
| `Fee/src/ti_fee_format.c` | Implementation |
| `Fee/src/ti_fee_ini.c` | Implementation |
| `Fee/src/ti_fee_invalidateblock.c` | Implementation |
| `Fee/src/ti_fee_main.c` | Implementation |
| `Fee/src/ti_fee_read.c` | Implementation |
| `Fee/src/ti_fee_readSync.c` | Implementation |
| `Fee/src/ti_fee_shutdown.c` | Implementation |
| `Fee/src/ti_fee_util.c` | Implementation |
| `Fee/src/ti_fee_writeAsync.c` | Implementation |
| `Fee/src/ti_fee_writeSync.c` | Implementation |
| `Fee/include/Device_Header.h` | Public interface |
| `Fee/include/Device_TMS570LS07.h` | Public interface |
| `Fee/include/Device_TMS570LS12.h` | Public interface |
| `Fee/include/Device_types.h` | Public interface |
| `Fee/include/Fee_Cbk.h` | Public interface |
| `Fee/include/fee.h` | Public interface |
| `Fee/include/fee_interface.h` | Public interface |
| `Fee/include/fee_memmap.h` | Public interface |
| `Fee/include/ti_fee.h` | Public interface |

Project layout per module: `src/` (implementation), `include/` (public headers, where present), `autosar/` (DaVinci/RTE artefacts), `generate/` + `tools/` (generation & integration scripts), `utp/` (unit-test package with RTE contract stubs), `doc/` (design documents).


## Dependencies (direct includes)

- `Std_Types.h`
- `Device_TMS570LS07.h`
- `Device_header.h`
- `MemMap.h`
- `Device_TMS570LS12.h`
- `Fee.h`
- `Fee_Cbk.h`
- `SchM_Fee.h`
- `Det.h`
- `ti_fee.h`


## Usage


This component is integrated through the AUTOSAR Runtime Environment (RTE): other Software Components (SW-Cs) communicate with it via sender/receiver ports and client/server calls listed above, scheduled by the Runtime Environment generated from the DaVinci / Electronic Control Unit configuration (`Chrysler_LWR_EPS_TMS570/Tools/AsrProject`). Per-component generation and integration scripts live in the module `generate/` and `tools/` folders (e.g. `RteGen.bat`, `Integrate.bat`). Unit-test harnesses with RTE contract stubs live under `utp/contract/`.


## Design documents


Converted from the module `doc/` folder (originals remain authoritative):

- [AutoSAR FEE Parameter Configuration](./doc-autosar-fee-parameter-configuration/) `(AutoSAR FEE Parameter Configuration.pdf)`
- [AutoSAR FEE User Guide](./doc-autosar-fee-user-guide/) `(AutoSAR FEE User Guide.pdf)`
- [DataSheet TMS570LS0714](./doc-datasheet-tms570ls0714/) `(DataSheet_TMS570LS0714.pdf)`
- [DataSheet TMS570LS1227](./doc-datasheet-tms570ls1227/) `(DataSheet_TMS570LS1227.pdf)`


## Other artefacts (not converted)

- `Fee/doc/Fee_Review_Checklists.xlsm` — binary spreadsheet (open in Excel/LibreOffice).
- `Fee/doc/QAC_Results/` — static-analysis (QAC) result artefacts.
