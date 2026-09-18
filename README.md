# Electric Power Steering (EPS) System for Chrysler LWR

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Language: C](https://img.shields.io/badge/Language-C-blue.svg)
![Platform: TMS570](https://img.shields.io/badge/Platform-TMS570-orange.svg)
![Standard: AUTOSAR](https://img.shields.io/badge/Standard-AUTOSAR-red.svg)
![Docs: Astro Starlight](https://img.shields.io/badge/Docs-Astro_Starlight-7c3aed.svg)
![Safety: ISO 26262 ASIL D](https://img.shields.io/badge/Safety-ISO_26262_ASIL_D-lightgrey.svg)

> Complete **Electric Power Steering (EPS)** software for the **Chrysler LWR** platform — AUTOSAR application components, complex drivers, Vector MICROSAR basic software and TI drivers on the **TMS570** microcontroller.

- [Documentation site (GitHub Pages)](../../..)
- [CI status](../../actions) · [License](LICENSE)

## Table of contents

- [Features](#features)
- [AUTOSAR architecture](#autosar-architecture)
- [Module inventory (layer × origin)](#module-inventory-layer--origin)
- [Repository structure](#repository-structure)
- [Build instructions](#build-instructions)
- [Vector vs. in-house code](#vector-vs-in-house-code)
- [Contributing](#contributing)
- [License](#license)

## Features

<details>
<summary><strong>Key components (click to expand)</strong></summary>

- **TMS570**: TI Hercules safety microcontroller running the EPS control.
- **AUTOSAR**: application Software Components (`Ap_*` Application, `Sa_*` Sensor/Actuator), Complex Device Drivers (`Cd_*` Complex Driver, sensor and actuator drivers), Vector MICROSAR Basic Software / Runtime Environment / Operating System.
- **ISO 26262 ASIL D**: firewalls, plausibility monitors, temporal monitoring, controlled shutdown paths.
- **Controller Area Network + Unified Diagnostic Services**: Vector Communication stack, Serial Communication Input (`SrlComInput`) / Serial Communication Output (`SrlComOutput`), Universal Measurement and Calibration Protocol measurement & calibration.

</details>

<details>
<summary><strong>Functionality (click to expand)</strong></summary>

- Precise power-assisted steering control (base assist, damping, return, active pull, hysteresis and stability compensation).
- Electric motor power management (current-mode control, thermal duty cycle, power limiting).
- End-of-travel, friction learning, wheel-imbalance rejection and high-frequency assist functions.
- On-board diagnostics via Diagnostic Event Manager / Diagnostic Manager (`DiagMgr`), manufacturing services via Common Manufacturing Services (`CMS_Common`).

</details>

## AUTOSAR architecture

```text
Application Software                Application / Sensor-Actuator Software Components: Steering Assist Control, Steering Damping Control, Steering Return Control, System State and Mode Management, Diagnostic Manager, …
Complex Device Drivers              Analog-to-Digital Converter Driver, Enhanced Pulse-Width Modulation Driver, Space-Vector Motor Driver, Non-Volatile Memory Manager/Proxy, TMS570 Startup Sequencing, TMS570 Micro Diagnostics
Runtime Environment (Vector)        Generated Configuration Data + per-component Runtime Environment contracts (Rte_<Software Component>.h)
Basic Software (Vector)             Services: Diagnostic Event Manager, Development Error Tracer, Electronic Control Unit State Manager, Non-Volatile Memory Manager, Memory Abstraction Interface, Watchdog Manager …  Communication: Controller Area Network Driver / Interaction Layer / Network Management / Transport Protocol / Communication Control …
Electronic Control Unit Abstraction  Input-Output Hardware Abstraction (+ project Input-Output Hardware Abstraction sources), Memory Abstraction Interface, Watchdog Interface
Microcontroller Abstraction Layer   Digital Input-Output Driver, Port Pin Driver, Microcontroller Unit Driver, General-Purpose Timer Driver, Controller Area Network Driver … + Texas Instruments Flash EEPROM Emulation / Flash Memory Driver (F021 Flash Application Programming Interface)
Operating System (Vector OSEK)      Tasks, alarms, schedule tables driving Runtime Environment runnables
Libraries & Common                  Nexteer Mathematics and Filter Library (math/filters), Common Manufacturing Services (diagnostic services), Standard Type Definitions, Diagnostic Metrics Library
```

### Abbreviations and long names

Short names are kept in parentheses for traceability to folders and files; descriptive long names lead everywhere for readability.

| Short name / abbreviation | Descriptive long name |
| --- | --- |
| Application Software | Application-level control and diagnostics; folder group `Ap_*` Application, `Sa_*` Sensor/Actuator |
| Complex Device Drivers | Hardware-near drivers; `Cd_*` Complex Driver, `Adc` Analog-to-Digital Converter, `ePWM` Enhanced Pulse-Width Modulation |
| Basic Software | Vector MICROSAR services, communication and memory stack |
| Microcontroller Abstraction Layer | Microcontroller peripheral drivers |
| Runtime Environment | AUTOSAR Virtual Function Bus implementation (generated contracts `Rte_*.h`) |
| Operating System | Vector MICROSAR OSEK tasks, alarms, schedule tables |
| Electronic Control Unit | The physical controller |
| Software Component | AUTOSAR application unit; `Ap_*` = Application, `Sa_*` = Sensor/Actuator, `Cd_*` = Complex Driver |
| Communication | Communication stack (Controller Area Network, Interaction Layer, Transport Protocol) |
| Unified Diagnostic Services | Diagnostic communication |
| Universal Measurement and Calibration Protocol | Measurement and calibration slave protocol |
| Non-Volatile Memory | Flash EEPROM Emulation, Non-Volatile Memory Manager, Memory Abstraction Interface |
| Input-Output Hardware Abstraction | Board-level signal abstraction |
| Watchdog Manager | Alive supervision with Watchdog Driver and Watchdog Interface |
| Diagnostic Event Manager | Fault event storage (Vector) |
| Diagnostic Manager | In-house `DiagMgr` fault handling on top of Diagnostic Event Manager |

## Module inventory (layer × origin)

Origin legend: **Custom** = Nexteer in-house logic (Runtime Environment frame generated by Vector MICROSAR Runtime Environment Generator) · **Vector** = Vector-provided MICROSAR Basic Software / Runtime Environment / Operating System · **TI** = Texas Instruments drivers · **Third-party** = external code customised in-house · **Mixed** = in-house with Vector-derived file(s).

<details>
<summary><strong>Application Software</strong> — 52 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Absolute Hardware Position Serial Communication (`AbsHwPosScom`) | Custom | AUTOSAR software component `Ap_AbsHwPosScom` for the Chrysler LWR EPS — design coverage: AbsHwPosSCom. |
| Active Pull Compensation (`ActivePull`) | Custom | AUTOSAR software component `Ap_ActivePull` for the Chrysler LWR EPS — design coverage: Active Pull Comp. |
| Arbiter Limiter (`ArbLmt`) | Custom | AUTOSAR software component `Ap_ArbLmt` for the Chrysler LWR EPS — design coverage: Arbiter Limiter Chrysler. |
| Steering Assist Control (`Assist`) | Custom | AUTOSAR software component `Ap_Assist` for the Chrysler LWR EPS — design coverage: Assist. |
| Assist Safety Firewall (`AssistFirewall`) | Custom | AUTOSAR software component `Ap_AssistFirewall` for the Chrysler LWR EPS — design coverage: Assist Firewall. |
| Assist Sum Limit – Current Mode (`AstLmt_CM`) | Custom | AUTOSAR software component `Ap_AstLmt` for the Chrysler LWR EPS — design coverage: Assist Sum Limit CurrentMode; AstLmt  |
| Average Friction Learning (`AvgFricLrn`) | Custom | AUTOSAR software component `Ap_AvgFricLrn` for the Chrysler LWR EPS — design coverage: Average Friction Learning. |
| Battery Voltage Monitoring (`BatteryVoltage`) | Custom | AUTOSAR software component `Ap_BatteryVoltage` for the Chrysler LWR EPS — design coverage: Battery Voltage. |
| Bulk Capacitor Pre-Charge (`BkCpPc`) | Custom | AUTOSAR software component `Sa_BkCpPc` for the Chrysler LWR EPS — design coverage: Bulk Cap Precharge. |
| Battery Voltage Diagnostics (`BVDiag`) | Custom | AUTOSAR software component `Ap_BVDiag` for the Chrysler LWR EPS — design coverage: Battery Voltage Diagnostics. |
| Current-Mode Motor Current Sensing (`CmMtrCurr`) | Custom | AUTOSAR software component `Sa_CmMtrCurr` for the Chrysler LWR EPS — design coverage: CmMtrCurr. |
| Controlled Disable and Shutdown (`CtrldDisShtdn`) | Custom | AUTOSAR software component `Ap_CtrldDisShtdn` for the Chrysler LWR EPS — design coverage: Controller Disable. |
| Controller Temperature Monitoring (`CtrlTemp`) | Custom | AUTOSAR software component `Sa_CtrlTemp` for the Chrysler LWR EPS — design coverage: Controller Temperature. |
| Current Reasonableness Diagnostics (`CurrReasDiag`) | Custom | AUTOSAR software component `Ap_CurrReasDiag` for the Chrysler LWR EPS system on the TMS570. |
| Steering Damping Control (`Damping`) | Custom | AUTOSAR software component `Ap_Damping` for the Chrysler LWR EPS — design coverage: Damping. |
| Damping Safety Firewall (`DampingFirewall`) | Custom | AUTOSAR software component `Ap_DampingFirewall` for the Chrysler LWR EPS — design coverage: Damping Firewall. |
| Diagnostic Manager (`DiagMgr`) | Custom | Core Diagnostic Manager Functionality |
| Electric Power Consumption Monitoring (`ElePwr`) | Custom | AUTOSAR software component `Ap_ElePwr` for the Chrysler LWR EPS — design coverage: Electric Power Consumption. |
| End-of-Travel Actuator Management (`EOTActuatorMng`) | Custom | AUTOSAR software component `Ap_EOTActuatorMng` for the Chrysler LWR EPS — design coverage: End of Travel Actuator Manage |
| Frequency-Dependent Damping and Inertia Compensation (`FrqDepDmpnInrtCmp`) | Custom | AUTOSAR software component `Ap_FrqDepDmpnInrtCmp` for the Chrysler LWR EPS — design coverage: Frequency Dependant Dampin |
| Global Signal Overwrite Diagnostics (`Gsod`) | Custom | AUTOSAR software component `Ap_Gsod` for the Chrysler LWR EPS — design coverage: Gsod. |
| Haptic Lane Feedback Torque Overlay (`HaLFTO`) | Custom | AUTOSAR software component `Ap_HaLFTO` for the Chrysler LWR EPS — design coverage: HaLFTO. |
| High-Frequency Assist Control (`HighFreqAssist`) | Custom | AUTOSAR software component `Ap_HighFreqAssist` for the Chrysler LWR EPS — design coverage: High Frequency Assist. |
| High-Load Stall Protection (`HiLoadStall`) | Custom | AUTOSAR software component `Ap_HiLoadStall` for the Chrysler LWR EPS — design coverage: HiLoadStall. |
| Hardware Power-Up Sequencing (`HwPwUp`) | Custom | AUTOSAR software component `Ap_HwPwUp` for the Chrysler LWR EPS — design coverage: Hardware Power Up. |
| Handwheel Torque Sensing (`HwTrq`) | Custom | AUTOSAR software component `Sa_HwTrq` for the Chrysler LWR EPS — design coverage: Handwheel Torque 2; Handwheel Torque. |
| Hysteresis Compensation (`HystComp`) | Custom | AUTOSAR software component `Ap_HystComp` for the Chrysler LWR EPS — design coverage: Hysteresis Compensation. |
| Limiter Conditioning (`LmtCod`) | Custom | AUTOSAR software component `Ap_LmtCod` for the Chrysler LWR EPS — design coverage: Limiter Conditioning. |
| End-of-Travel Learning (`LrnEOT`) | Custom | AUTOSAR software component `Ap_LrnEOT` for the Chrysler LWR EPS — design coverage: LearnEOT. |
| Motor Control – Current Mode (`MtrCtrl_CM`) | Custom | AUTOSAR software component `Ap_CurrCmd` for the Chrysler LWR EPS — design coverage: CurrCmd; CurrParamComp. |
| Motor Position Sensing (`MtrPos`) | Custom | AUTOSAR software component `Sa_MtrPos` for the Chrysler LWR EPS — design coverage: Motor Position 2; Motor Position 3. |
| Motor Temperature Estimation (`MtrTempEst`) | Custom | AUTOSAR software component `Ap_MtrTempEst` for the Chrysler LWR EPS — design coverage: Motor Temperature Estimation. |
| Motor Velocity Sensing (`MtrVel`) | Custom | AUTOSAR software component `Sa_MtrVel` for the Chrysler LWR EPS — design coverage: MotorVelocity2; MotorVelocity3. |
| Over-Voltage Monitoring (`OvrVoltMon`) | Custom | AUTOSAR software component `Sa_OvrVoltMon` for the Chrysler LWR EPS — design coverage: OverVoltageMonitor. |
| Park Assist Torque Overlay (`PAwTO`) | Custom | AUTOSAR software component `Ap_PAwTO` for the Chrysler LWR EPS — design coverage: PAwTO. |
| Signal Polarity Management (`Polarity`) | Custom | AUTOSAR software component `Ap_Polarity` for the Chrysler LWR EPS — design coverage: Polarity. |
| Power Limit Function – Current Mode (`PwrLmtFuncCr`) | Custom | AUTOSAR software component `Ap_PwrLmtFuncCr` for the Chrysler LWR EPS — design coverage: Power Limit Function CM. |
| Steering Return Control (`Return`) | Custom | AUTOSAR software component `Ap_Return` for the Chrysler LWR EPS — design coverage: Return. |
| Return Safety Firewall (`ReturnFirewall`) | Custom | AUTOSAR software component `Ap_ReturnFirewall` for the Chrysler LWR EPS — design coverage: Return Firewall. |
| Signal Conditioning (`SgnlCond`) | Custom | AUTOSAR software component `Ap_SignlCondn` for the Chrysler LWR EPS — design coverage: SignalConditioning. |
| Shutdown Mechanisms (`ShtdnMech`) | Custom | AUTOSAR software component `Sa_ShtdnMech` for the Chrysler LWR EPS — design coverage: Shutdown Mechanisms. |
| Stability Compensation (`StabilityComp`) | Custom | AUTOSAR software component `Ap_StabilityComp` for the Chrysler LWR EPS — design coverage: StabilityCompensation2; Stabil |
| System State and Mode Management (`StaMd`) | Custom | Core States and Modes Module |
| Stability Control Torque Overlay (`StbCTO`) | Custom | AUTOSAR software component `Ap_StbCTO` for the Chrysler LWR EPS — design coverage: StabiliCtrlTorqueOverlay. |
| State Output Control (`StOpCtrl`) | Custom | AUTOSAR software component `Ap_StOpCtrl` for the Chrysler LWR EPS — design coverage: State Output Control. |
| Supply Voltage and Motor Driver Diagnostics (`SVDiag`) | Custom | AUTOSAR software component `Ap_DigPhsReasDiag` for the Chrysler LWR EPS — design coverage: DigPhsReasDiag; Motor Driver  |
| Thermal Duty Cycle Management (`ThrmDutyCycle`) | Custom | AUTOSAR software component `Ap_ThrmlDutyCycle` for the Chrysler LWR EPS — design coverage: Thermal Duty Cycle. |
| Temporal Monitoring (`TmprlMon`) | Custom | AUTOSAR software component `Sa_TmprlMon` for the Chrysler LWR EPS — design coverage: Temporal Monitor 2; Temporal Monito |
| Torque Reasonableness Diagnostics (`TqRsDg`) | Custom | AUTOSAR software component `Ap_TqRsDg` for the Chrysler LWR EPS — design coverage: TorqueReasonableDiagnostics. |
| Tuning Selection Authority (`TuningSelAuth`) | Custom | AUTOSAR software component `Ap_TuningSelAuth` for the Chrysler LWR EPS — design coverage: Tuning Select Authority. |
| Vehicle Speed Limiter (`VehSpdLmt`) | Custom | AUTOSAR software component `Ap_VehSpdLmt` for the Chrysler LWR EPS — design coverage: VehSpdLmt. |
| Wheel Imbalance Rejection (`WhlImbRej`) | Custom | AUTOSAR software component `Ap_WhlImbRej` for the Chrysler LWR EPS — design coverage: Wheel Imbalance Rejection. |

</details>

<details>
<summary><strong>Complex Device Drivers</strong> — 7 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Analog-to-Digital Converter Driver (`Adc`) | Custom | Analog-to-Digital Converter Unit 1 Complex Device Driver |
| Enhanced Pulse-Width Modulation Driver (`ePWM`) | Custom | AUTOSAR software component `Ap_ePWM2` for the Chrysler LWR EPS — design coverage: NHetRegisters; Nhet 1. |
| Non-Volatile Memory Manager (`NvMMgr`) | Custom | Flash EEPROM Emulation interface module |
| Non-Volatile Memory Proxy (`NvMProxy`) | Custom | Complex Driver Non-Volatile Memory Proxy which acts as a proxy between Non-Volatile Memory Manager and application |
| Space-Vector Motor Driver – Current Mode (`SVDrvr_CM`) | Custom | Non-AUTOSAR Pulse-Width Modulation driver required to perform Electric Power Steering motor control |
| TMS570 Startup Sequencing (`TMS570_Startup`) | Custom | Application Startup Sequence |
| TMS570 Micro Diagnostics (`TMS570_uDiag`) | Custom | Data and Prefetch Abort Handler |

</details>

<details>
<summary><strong>Basic Software</strong> — 24 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Controller Area Network Driver (`BSW:Can`) | Vector | Microcontroller Abstraction Layer Controller Area Network driver (Vector MICROSAR DrvCan) for the TMS570 DCAN peripheral. |
| Communication Control (`BSW:Ccl`) | Vector | Communication Control (Vector CCL) over the MICROSAR Communication stack. |
| Cyclic Redundancy Check Library (`BSW:Crc`) | Vector | AUTOSAR Cyclic Redundancy Check library (Vector Standard Library family). |
| Diagnostic Event Manager (`BSW:Dem`) | Vector | Diagnostic Event Manager (Vector MICROSAR Dem). |
| Development Error Tracer (`BSW:Det`) | Vector | Development Error Tracer (Vector Det). |
| Diagnostic Communication Stack (`BSW:Diag`) | Vector | Diagnostic communication stack (Vector, Unified Diagnostic Services). |
| Digital Input-Output Driver (`BSW:Dio`) | Vector | Microcontroller Abstraction Layer Digital Input-Output driver (Vector Dio). |
| Diagnostic Protocol Manager (`BSW:Dpm`) | Vector | Diagnostic Protocol Manager support (Vector). |
| Electronic Control Unit State Manager (`BSW:EcuM`) | Vector | Electronic Control Unit State Manager (Vector MICROSAR Electronic Control Unit State Manager). |
| General-Purpose Timer Driver (`BSW:Gpt`) | Vector | Microcontroller Abstraction Layer General-Purpose Timer driver (Vector Gpt). |
| Interaction Layer (`BSW:Il`) | Vector | Interaction Layer (Vector IL, signal-based Communication abstraction). |
| Input-Output Hardware Abstraction (`BSW:IoHwAb`) | Vector | Input-Output Hardware Abstraction (project-specific `IoHwAb.c` on a Vector IoHwAb frame). |
| Microcontroller Unit Driver (`BSW:Mcu`) | Vector | Microcontroller Abstraction Layer Microcontroller Unit driver (Vector Mcu). |
| Memory Abstraction Interface (`BSW:MemIf`) | Vector | Memory Abstraction Interface (AUTOSAR MemIf, Vector). |
| Network Management (`BSW:Nm`) | Vector | Network Management (Controller Area Network Network Management / OSEK Network Management configuration, Vector). |
| Non-Volatile Memory Manager (`BSW:NvM`) | Vector | Non-Volatile Memory Manager (Vector MICROSAR Non-Volatile Memory Manager). |
| Port Pin Driver (`BSW:Port`) | Vector | Microcontroller Abstraction Layer Port Pin driver (Vector Port). |
| Software Integration Package Version Check (`BSW:SipVersionCheck`) | Vector | Software Integration Package version-consistency check (Vector). |
| Transport Protocol (`BSW:Tp`) | Vector | Transport Protocol — Controller Area Network Transport Protocol (Vector). |
| Vector Standard Library (`BSW:VStdLib`) | Vector | Vector standard library. |
| Watchdog Driver (`BSW:Wdg`) | Vector | Microcontroller Abstraction Layer Watchdog driver (Vector Wdg). |
| Watchdog Interface (`BSW:WdgIf`) | Vector | Watchdog Interface (AUTOSAR WdgIf, Vector). |
| Watchdog Manager (`BSW:WdgM`) | Vector | Watchdog Manager (Vector WdgM) with generated alive/supervision graph. |
| Universal Measurement and Calibration Protocol (`BSW:Xcp`) | Vector | Basic Software Universal Measurement and Calibration Protocol slave stack (Vector). |

</details>

<details>
<summary><strong>Microcontroller Abstraction Layer / Memory Drivers</strong> — 3 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Controller Area Network Driver (`Can`) | Custom | AUTOSAR software component `Can` for the Chrysler LWR EPS system on the TMS570. |
| Flash EEPROM Emulation Driver (`Fee`) | TI | AUTOSAR software component `Fee` for the Chrysler LWR EPS — design coverage: AutoSAR FEE Parameter Configuration; AutoSA |
| Flash Memory Driver (`Fls`) | TI | AUTOSAR software component `Fls` for the Chrysler LWR EPS — design coverage: F021 Flash Application Programming Interface License Agreement; Release N |

</details>

<details>
<summary><strong>Runtime Environment and Operating System</strong> — 3 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Generated Configuration Data (`GenData`) | Vector | DaVinci-generated BSW/RTE/OS configuration artefacts. |
| Operating System (`OS`) | Vector | Vector MICROSAR OSEK OS — tasks, alarms, schedule tables. |
| Runtime Environment (`RTE`) | Vector | Vector MICROSAR RTE (v2.19.1) — VFB implementation, ports, runnable glue. |

</details>

<details>
<summary><strong>Libraries & Common</strong> — 4 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Common Manufacturing Services (`CMS_Common`) | Mixed | Common Manufacturing Program Interface for XCP and ISO services |
| Diagnostic Metrics Library (`Metrics`) | Third-party | Data for Metrics |
| Nexteer Mathematics and Filter Library (`NxtrLib`) | Custom | This file contains the checksum functions |
| Standard Type Definitions (`StdDef`) | Custom | AUTOSAR software component `StdDef` for the Chrysler LWR EPS system on the TMS570. |

</details>

<details>
<summary><strong>Integration project</strong> — 4 modules (click to expand)</summary>


| Module | Origin | Purpose |
| --- | --- | --- |
| Serial Communication Input Conditioning (`SrlComInput`) | Custom | Serial-communication input conditioning: receives vehicle messages (e.g. vehicle speed, engine signals) from the COM sta |
| Serial Communication Output Conditioning (`SrlComOutput`) | Custom | Serial-communication output: packs EPS internal signals into transmit messages for the vehicle network. |
| Vehicle Power Mode Management (`VehPwrMd`) | Custom | Vehicle power-mode management: evaluates ignition/power-mode state and distributes it to the application (startup/shutdo |
| Handwheel Input Qualification (`WIRInputQual`) | Custom | WIR (wheel-input-rotation / handwheel input) qualification: plausibility-checks and qualifies handwheel-related inputs b |

</details>


## Repository structure

```text
<Module>/                 # one folder per Software Component / driver / library, e.g. Steering Assist Control (Assist/), Analog-to-Digital Converter Driver (Adc/), Nexteer Mathematics and Filter Library (NxtrLib/)
  src/ include/           # implementation + public headers (where applicable)
  autosar/                # DaVinci / Runtime Environment artefacts for the component
  generate/ tools/        # generation scripts, integration scripts — generation & Electronic Control Unit integration scripts
  utp/contract/           # unit-test package with Runtime Environment contract stubs
  doc/                    # original Word/PDF design docs (authoritative sources)
Chrysler_LWR_EPS_TMS570/  # Electronic Control Unit integration project
  SwProject/              # Code Composer Studio project, linker command, Basic Software/, Complex Device Drivers/, Generated Configuration Data, Serial Communication Input/Output, Vehicle Power Mode Management, …
  Tools/AsrProject/       # DaVinci Configurator project (EPS.dcf) + generators
  HLDD/                   # high-level design descriptions of the AUTOSAR configuration
docs/                     # documentation source (published to GitHub Pages)
.github/workflows/        # deploy workflow, auto-merge-dependabot workflow (do not modify)
```

## Build instructions

<details>
<summary><strong>Firmware build (Code Composer Studio)</strong></summary>

1. Clone this repository.
2. One-time tool setup: follow [`Chrysler_LWR_EPS_TMS570/Tools/Tools_Instructions.txt`](Chrysler_LWR_EPS_TMS570/Tools/Tools_Instructions.txt) (DaVinci prerequisite: rename `xerces_c_2_7.dll` → `xerces-c_2_7.dll` under `Tools\AsrProject\Generators\Components`).
3. Open `Chrysler_LWR_EPS_TMS570/SwProject/.ccsproject` in Code Composer Studio (TI ARM compiler for TMS570).
4. If the AUTOSAR configuration changed, regenerate with DaVinci (`Tools/AsrProject`, ECU project `EPS`) and run the per-component `RteGen.bat` / `tools/Integrate.bat` scripts as needed.
5. Build the CCS project; `SwProject/postbuild.bat` finalises the flash image (memory map: `TMS570LS202x6SFlashLnk.cmd`).
6. Flash the image onto the TMS570 target.

</details>

## Vector vs. in-house code

- **In-house (Custom)** — all Application (`Ap_*`) / Sensor-Actuator (`Sa_*`) application components, the Complex Driver (`Cd_*`) complex drivers, Analog-to-Digital Converter / Enhanced Pulse-Width Modulation drivers, Nexteer Mathematics and Filter Library, Common Manufacturing Services, Standard Type Definitions, and the Electronic Control Unit integration project. File frames carry a *“Generator: MICROSAR Runtime Environment Generator”* stamp — that is Vector-generated boilerplate; the control logic is project-owned.
- **Vector-provided** — everything under `SwProject/Source/BSW/` (Controller Area Network Driver, Operating System, Diagnostic Event Manager, Non-Volatile Memory Manager, Watchdog Manager, Universal Measurement and Calibration Protocol, …), Generated Configuration Data (Runtime Environment / Operating System / Basic Software configuration) and the DaVinci project. Governed by the Vector license; regenerate instead of hand-editing.
- **Texas Instruments-provided** — Flash EEPROM Emulation driver (`Fee/`) and Flash Memory Driver with F021 Flash Application Programming Interface (`Fls/`) under Texas Instruments license terms; TMS570 startup code builds on Texas Instruments collateral.
- **Third-party, customised** — Diagnostic Metrics Library (`Metrics/`, Delphi origin), maintained in-project.

## Contributing

We encourage contributions! If you'd like to improve this project, please submit a pull request. For Dependabot-driven dependency updates on the docs site, auto-merge is configured (see [`.github/workflows/auto-merge-dependabot.yml`](.github/workflows/auto-merge-dependabot.yml)) — the repository needs **Settings → General → Allow auto-merge** enabled for it to take effect.

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file. Bundled third-party components (Vector MICROSAR Basic Software, Texas Instruments drivers) remain under their own licenses as noted above and in [LICENSE](LICENSE).
