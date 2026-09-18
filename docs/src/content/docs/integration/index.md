---
title: "Integration project"
description: "Electronic Control Unit project: build system, SrlCom, VehPwrMd, CDD services"
---


# Integration project — `Chrysler_LWR_EPS_TMS570`

<span class="origin-badge origin-custom">Custom · Nexteer in-house</span>

> Naming: titles lead with the descriptive long name; short project names (`SrlComInput` Serial Communication Input Conditioning, `VehPwrMd` Vehicle Power Mode Management, `WIRInputQual` Handwheel Input Qualification) follow in parentheses.

> **Origin:** Project-owned integration (Nexteer) assembling Vector MICROSAR BSW/RTE, TI drivers, and in-house Software Components (SW-Cs) into the Chrysler LWR EPS ECU image.

## Purpose

Top-level Electronic Control Unit project: linker command file, Code Composer Studio project, post-build steps, DaVinci tool project, and the project-specific Software Components (SW-Cs) and CDD services that exist only at integration level.


## Build system

| Artefact | Role |
| --- | --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/TMS570LS202x6SFlashLnk.cmd` | Linker command file (TMS570 flash memory map) |
| `Chrysler_LWR_EPS_TMS570/SwProject/.ccsproject` | Code Composer Studio project definition |
| `Chrysler_LWR_EPS_TMS570/SwProject/postbuild.bat` | Post-build steps (checksum, hex conversion, etc.) |
| `Chrysler_LWR_EPS_TMS570/Tools/AsrProject` | DaVinci Configurator project (`EPS.dcf`), generators (incl. ARTT) |
| `Chrysler_LWR_EPS_TMS570/HLDD` | High-level design descriptions of the AUTOSAR configuration |
| `SwProject/Source/BSW` | Vector MICROSAR BSW delivery (see [BSW](../bsw/)) |
| `SwProject/Source/GenData*` | DaVinci-generated configuration (see [RTE & OS](../rte-os/)) |

Build: open `.ccsproject` in Code Composer Studio for the TMS570 target and build; `postbuild.bat` finalises the flash image. Per-component `tools/Integrate.bat` scripts copy component artefacts into the Electronic Control Unit project tree.


## ECU-level software components

| Component | Purpose |
| --- | --- |
| [Serial Communication Input Conditioning (`SrlComInput`)](./srlcominput/) | Serial-communication input conditioning and qualification |
| [Serial Communication Output Conditioning (`SrlComOutput`)](./srlcomoutput/) | Serial-communication output packing for the vehicle network |
| [Vehicle Power Mode Management (`VehPwrMd`)](./vehpwrmd/) | Vehicle power-mode management |
| [Handwheel Input Qualification (`WIRInputQual`)](./wirinputqual/) | WIR input qualification |

## ECU-level CDD services (`SwProject/Source/CDD/`)


Complex drivers and services integrated at ECU level (15 file(s)):

- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/CDD_Const.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/CDD_Data.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/CDD_Data.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/CDD_Func.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/EPS_DiagSrvcs/RTE_GlobalData.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/EPS_DiagSrvcs/SComm_Func.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/MtrCtrl/MtrCtrl_Irq.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/MtrCtrl/MtrCtrl_Irq.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/SrlComSrvc/SrlComSrvc.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/SrlComSrvc/SrlComSrvc.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/BasicSysSrvc/EcuStartup.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/BasicSysSrvc/Interrupts.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/BasicSysSrvc/Interrupts.h`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/BasicSysSrvc/Wdg_Stub.c`
- `Chrysler_LWR_EPS_TMS570/SwProject/Source/CDD/MPU/Mpu.asm`

Sub-folders: `BasicSysSrvc`, `EPS_DiagSrvcs` (manufacturing/diagnostics services, sibling of `CMS_Common`), `MPU` (memory-protection setup), `MtrCtrl` (motor-control CDD glue), `SrlComSrvc` (serial-communication services), plus shared `CDD_Data.c/h`, `CDD_Func.h`, `CDD_Const.h`.


## Tool project

- [Tools instructions](./tool-project/doc-tools-instructions/) — one-time DaVinci tool setup step (DLL rename).
- `Tools/AsrProject/Generators/Artt` — ARTT generator; see [ARTT release notes](../../general/vector-config/doc-releasenotes-artt-generator/).
