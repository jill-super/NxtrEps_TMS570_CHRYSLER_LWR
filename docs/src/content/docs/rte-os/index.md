---
title: "Runtime Environment and Operating System"
description: "Vector MICROSAR Run-Time Environment, OSEK OS and the DaVinci-generated configuration data shared by the whole ECU."
sidebar:
  order: 0
---

# Runtime Environment and Operating System

Vector MICROSAR Run-Time Environment, OSEK OS and the DaVinci-generated configuration data shared by the whole ECU.

> Naming: Runtime Environment and Operating System — titles lead with the long name; short names (`RTE`, `OS`, `GenData` Generated Configuration Data) follow in parentheses.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Generated Configuration Data (`GenData`)](./gendata/) | Vector | DaVinci-generated BSW/RTE/OS configuration artefacts. |
| [Operating System (`OS`)](./os/) | Vector | Vector MICROSAR OSEK OS — tasks, alarms, schedule tables. |
| [Runtime Environment (`RTE`)](./rte/) | Vector | Vector MICROSAR RTE (v2.19.1) — VFB implementation, ports, runnable glue. |
