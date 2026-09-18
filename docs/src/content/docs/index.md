---
title: "Chrysler LWR EPS — AUTOSAR Documentation"
description: "Documentation for the Electric Power Steering AUTOSAR system on TMS570 (Chrysler LWR)"
template: splash
hero:
  title: Chrysler LWR EPS Documentation
  tagline: AUTOSAR Electric Power Steering software for the TMS570 (Chrysler LWR platform) — layers, modules, and converted design documents.
  actions:
    - text: Browse application software
      link: ./asw/
      icon: right-arrow
    - text: Module & origin overview
      link: ./asw/
      variant: minimal
---

import { Card, CardGrid, Badge } from '@astrojs/starlight/components';

## Project overview

This site documents an **AUTOSAR-based Electric Power Steering (EPS)** system for the **Chrysler LWR** platform, running on the **TI TMS570** microcontroller. It covers roughly **90 software modules** and **4 converted design documents** (Word/PDF originals in the repository, preserved as authoritative sources).

<CardGrid>
  <Card title="Application Software (ASW)" icon="puzzle">
    52 application Software Components (`Ap_*` Application, `Sa_*` Sensor/Actuator): assist, damping, return, diagnostics, sensors and monitors. [Browse Application Software](./asw/).
  </Card>
  <Card title="Complex Device Drivers (CDD)" icon="setting">
    7 hardware-near Complex Device Drivers: Analog-to-Digital Converter, Enhanced Pulse-Width Modulation, Non-Volatile Memory proxy, Flash self-test, startup. [Browse Complex Device Drivers](./cdd/).
  </Card>
  <Card title="Basic Software (BSW)" icon="layers">
    47 Vector MICROSAR Basic Software service and Communication modules plus memory stack. [Browse Basic Software](./bsw/).
  </Card>
  <Card title="MCAL" icon="cpu">
    3 microcontroller-abstraction and TI memory drivers. [Browse Microcontroller Abstraction Layer](./mcal/).
  </Card>
  <Card title="RTE & OS" icon="rocket">
    Vector MICROSAR Runtime Environment, OSEK Operating System and generated configuration. [Browse](./rte-os/).
  </Card>
  <Card title="Integration" icon="wrench">
    Electronic Control Unit project, build system, Serial Communication (`SrlComInput`/`SrlComOutput`) and Vehicle Power Mode (`VehPwrMd`) components. [Browse](./integration/).
  </Card>
</CardGrid>

## Vector vs. in-house — how to read the badges

Every module page carries an origin badge. The rule used throughout this site:

- <span class="origin-badge origin-custom">Custom · Nexteer in-house</span> — control logic developed in-house for this EPS program. Note: file *frames* of application Software Components are emitted by the Vector MICROSAR RTE Generator (the `Generator:` header line); the functional code between the markers is project-owned.
- <span class="origin-badge origin-vector">Vector-provided · MICROSAR</span> — delivered and licensed by Vector Informatik (Basic Software stack, Runtime Environment, Operating System, DaVinci configuration). Regenerate, don't hand-edit.
- <span class="origin-badge origin-ti">TI-provided</span> — Texas Instruments drivers (Flash EEPROM Emulation, F021 Flash Application Programming Interface) under TI license terms.
- <span class="origin-badge origin-thirdparty">Third-party · customised</span> — e.g. Delphi-origin metrics code maintained in this project.

Methodology note: origins were assigned from copyright/license headers in the sources, generator stamps, and delivery paths (`SwProject/Source/Basic Software`, `GenData*` Generated Configuration Data ⇒ Vector; Flash EEPROM Emulation / Flash Memory Driver ⇒ Texas Instruments). Converted `.doc`/`.docx`/`.pdf` pages state their repository source path; legacy binary `.doc` files that could not be parsed automatically carry an explicit stub note instead of fabricated content.

## Repository layout

- C sources and tooling stay at the repository root, grouped per module (`src/`, `include/`, `autosar/`, `generate/`, `tools/`, `utp/`, `doc/`).
- This documentation site lives entirely in `docs/` (Astro v7 + Starlight). The deployed site is published to GitHub Pages from `docs/` via the `deploy.yml` workflow.
- Start with [Application Software](./asw/), [BSW](./bsw/), or the [Integration project](./integration/).

## Abbreviations and long names

Short folder and file names are kept in parentheses for traceability to the sources, but titles and tables always lead with the descriptive long name.

| Abbreviation | Long name |
| --- | --- |
| Application Software (`asw/`) | Application-level (application-level control and diagnostics; folder group `Ap_*`, `Sa_*`) |
| Complex Device Drivers (`cdd/`) | Hardware-near (hardware-near drivers; `Cd_*`, `Adc`, `ePWM`) |
| Basic Software (`bsw/`) | Vector MICROSAR services (Vector MICROSAR services, communication and memory stack) |
| Microcontroller Abstraction Layer (`mcal/`) | Microcontroller peripheral (microcontroller peripheral drivers) |
| Runtime Environment (`rte-os/`) | AUTOSAR Virtual Function Bus (AUTOSAR Virtual Function Bus implementation) |
| Operating System (`rte-os/`) | Vector MICROSAR OSEK tasks (Vector MICROSAR OSEK tasks, alarms, schedule tables) |
| Electronic Control Unit | The physical controller (the physical controller) |
| Software Component (SW-C) | AUTOSAR application unit (AUTOSAR application unit; `Ap_*` = Application, `Sa_*` = Sensor/Actuator, `Cd_*` = Complex Driver) |
| Communication (COM) | Communication stack (Controller Area Network, Interaction Layer, Transport Protocol) |
| Unified Diagnostic Services (UDS) | Diagnostic communication (diagnostic communication) |
| Universal Measurement and Calibration Protocol (XCP) | Measurement and calibration (measurement and calibration slave) |
| Non-Volatile Memory (NVRAM) | Flash EEPROM Emulation (Flash EEPROM Emulation, Non-Volatile Memory Manager, Memory Abstraction Interface) |
| Input-Output Hardware Abstraction (IoHwAb) | Board-level (board-level signal abstraction) |
| Watchdog Manager (WdgM) | Alive supervision (alive supervision with Watchdog Driver and Watchdog Interface) |
| Diagnostic Event Manager (Dem) | Fault event storage (fault event storage) |
| Diagnostic Manager (DiagMgr) | In-house (in-house `DiagMgr` fault handling on top of Diagnostic Event Manager) |

