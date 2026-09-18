---
title: "Operating System (OS)"
description: "Operating System (OS) — Vector OSEK OS tasks, alarms and schedule tables"
---


# Operating System — MICROSAR OS

<span class="origin-badge origin-vector">Vector-provided · MICROSAR</span>

> **Origin:** Vector-provided MICROSAR OS (OSEK/VDX class). Configuration is generated from the DaVinci OS configuration; sources live in `SwProject/Source/BSW/Os/` with generated data in `SwProject/Source/GenDataOS/`.

## Purpose

*Operating System* (`OS`) — Provides tasks, alarms, events, resources and schedule tables that execute RTE runnables (e.g. `Assist_Per1`) and BSW schedules at their configured periods, plus startup/shutdown hooks into `EcuM` and the TMS570 startup code.


## Key files

| File |
| --- |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/Os_MemMap.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/intvect.asm` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/osobjs.inc` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/osobjs_init.inc` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/tcb.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/tcb.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/tcb.inc` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/trustfct.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/GenDataOS/trustfct.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/AtosTime.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/Os.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/Os_cfg.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/atosappl.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/emptymac.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osSAPI.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osek.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osek.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekalrm.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekasm.asm` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekasrt.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekcov.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekerr.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekerr.h` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekevnt.c` |
| `Chrysler_LWR_EPS_TMS570/SwProject/Source/BSW/Os/osekext.h` |

…and 10 more — see the repository tree.


## Usage

Task/period mapping is defined in the DaVinci OS configuration (`Tools/AsrProject`). Application developers attach runnables to RTE events; the OS schedule itself is a Vector configuration artefact. See also the `Os.doc` HLDD stub under [General documents](../../general/vector-config/doc-os/).
