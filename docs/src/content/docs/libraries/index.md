---
title: "Libraries & Common"
description: "Shared project libraries and headers: fixed-point math, filters, interpolation, system time, manufacturing/diagnostics common services, AUTOSAR standa"
sidebar:
  order: 0
---

# Libraries & Common

Shared project libraries and headers: fixed-point math, filters, interpolation, system time, manufacturing/diagnostics common services, AUTOSAR standard types, metrics.

> Naming: titles lead with the descriptive long name; short library names follow in parentheses.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Common Manufacturing Services (`CMS_Common`)](./cms-common/) | Mixed | Common Manufacturing Program Interface for XCP and ISO services |
| [Diagnostic Metrics Library (`Metrics`)](./metrics/) | Third-party | Data for Metrics |
| [Nexteer Mathematics and Filter Library (`NxtrLib`)](./nxtrlib/) | Custom | This file contains the checksum functions |
| [Standard Type Definitions (`StdDef`)](./stddef/) | Custom | AUTOSAR software component `StdDef` for the Chrysler LWR EPS system on the TMS570. |
