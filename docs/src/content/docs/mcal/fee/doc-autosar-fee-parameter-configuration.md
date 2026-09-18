---
title: "AutoSAR FEE Parameter Configuration"
description: "Converted from AutoSAR FEE Parameter Configuration.pdf"
---

> **Source:** `Fee/doc/AutoSAR FEE Parameter Configuration.pdf` (307,679 bytes, `PDF`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

*PDF original: 31 page(s). Text extracted below (first 15 pages shown). Layout, figures and diagrams are not preserved — consult the original file in the repository for exact rendering.*


## Page 1

AutoSAR FEE Parameter Configuration (Rev 1.8)   
            
 
 
 
Texas Instruments Incorporated 
 
 
 
 
 
 
 
AutoSAR FEE Parameter  
Configuration Document


## Page 2

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      2 
 
ABSTRACT 
 
AutoSAR Flash EEPROM Emulation (AutoSAR FEE) driver utilizes Code Generation 
Tool to generate the configuration parameters required for EEPROM emulation. Code 
Generation Tool is used to configure parameters like which Flash Sectors to use, the 
number of Block s, Block Size etc. for EE PROM emulation . Code Generation Tool  
generates two files (Fee_cfg.h & Fee_cfg.c) depending on the configuration. 
 
This document describes the parameters used by Code Generation Tool to generate the 
AutoSAR FEE Configuration parameters.


## Page 3

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      3 
 
Revision History  
 
Version Release 
Date 
Author Comment 
1.0 09/16/2012 Vishwanath 
Reddy 
Initial version 
1.1  10/10/2012 Vishwanath 
Reddy 
Add configuration parameter 
FEE_NUMBER_OF_VIRTUAL_SECTORS_EEP1 
1.2 11/20/2012 Vishwanath 
Reddy 
Remove FeeSetModeSupported 
1.3 06/11/2013 Vishwanath 
Reddy 
Add configuration parameter’s: 
FEE_NUMBER_OF_UNCONFIGUREDBLOCKSTOCOPY, 
FEE_NUMBER_OF_EIGHTBYTEWRITES 
1.4 01/06/2014 Vishwanath 
Reddy 
Added configuration parameter 
FEE_CHECK_BANK7_ACCESS 
1.5 09/25/2014 Vishwanath 
Reddy 
Configuration update to support TMS570LS05xx, 
TMS570LS07xx, TMS570LS09xx. Range updated for 
FEE_VirtualSectorNumber, Virtual Sectors. 
New configuration parameter 
FEE_TOTAL_BLOCKS_DATASETS added. 
1.6 12/31/2014 Vishwanath 
Reddy 
Add new Configuration parameters. 
FEE_VIRTUALSECTOR_SIZE, 
FEE_PHYSICALSECTOR_SIZE,  
FEE_GENERATE_DEVICEANDVIRTUALSECTORSTRUC 
Note added in section 1.6 FEE Sector Configuration. 
1.7 01/07/2015 Vishwanath 
Reddy 
Remove Device_Header.h from fee_cfg.h file. 
1.8 01/21/2015 Vishwanath 
Reddy 
Added comments for FEE_TOTAL_BLOCKS_DATASETS, 
FEE_NUMBER_OF_EEPS and  
FEE_NUMBER_OF_BLOCKS 
 
 
Configuration Changes 
 
Parameter added/ Modified Change 
  
FeeCRCEnable New 
FeeWriteCounterSave New 
FeeNumberOfEEPS New 
FeeDevErrorDetect New 
FeeBlockOverhead Changed to 0x18 
FeeEEPNumber(in block configuration) New 
FeeNumberOfVirtualSectorsEEP1 New 
FEE_NUMBER_OF_UNCONFIGUREDBLOCKSTOCOPY New


## Page 4

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      4 
 
FEE_NUMBER_OF_EIGHTBYTEWRITES New 
FEE_CHECK_BANK7_ACCESS New 
FEE_TOTAL_BLOCKS_DATASETS New 
FEE_VIRTUALSECTOR_SIZE New 
FEE_PHYSICALSECTOR_SIZE New 
FEE_GENERATE_DEVICEANDVIRTUALSECTORSTRUC New


## Page 5

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      5 
 
Table of Contents  
 
1 Introduction ................................ ................................ ................................ .............. 7 
1.1 FEE Published information ................................ ................................ ............... 7 
1.1.1 Block OverHead ................................ ................................ ......................... 7 
1.1.2 Maximum Blocking Time ................................ ................................ ............ 7 
1.1.3 Page OverHead ................................ ................................ ......................... 8 
1.1.4 Sector OverHead ................................ ................................ ....................... 8 
1.2 FEE General Settings ................................ ................................ ...................... 9 
1.2.1 Virtual Page size ................................ ................................ ........................ 9 
1.2.2 Driver Index................................ ................................ ................................  9 
1.2.3 Error Notification ................................ ................................ ...................... 10 
1.2.4 End Notification ................................ ................................ ........................ 10 
1.2.5 Frequency ................................ ................................ ................................  11 
1.2.6 Enable Polling mode ................................ ................................ ................ 11 
1.2.7 Enable Error Correction ................................ ................................ ........... 12 
1.2.8 Error Correction Handling ................................ ................................ ......... 12 
1.2.9 Cyclic Redundancy Check ................................ ................................ ....... 13 
1.2.10 Block Write counter save................................ ................................ .......... 13 
1.2.11 Number of EEPs ................................ ................................ ...................... 14 
1.2.12 Development error Detect ................................ ................................ ........ 14 
1.2.13 Non configured blocks to copy ................................ ................................ . 15 
1.2.14 Number of eight byte writes ................................ ................................ ...... 15 
1.2.15 Check BANK7 Address Range ................................ ................................ . 16 
1.2.16 Total Blocks and Data Sets ................................ ................................ ...... 16 
1.2.17 Generate Device and Virtual sector structures ................................ ......... 17 
1.2.18 Required Virtual Sector Size ................................ ................................ .... 18 
1.2.19 FEE bank Physical Sector Size ................................ ................................  19 
1.3 Number of Blocks ................................ ................................ .......................... 20 
1.3.1 Blocks ................................ ................................ ................................ ...... 20 
1.4 Number of Virtual Sectors ................................ ................................ .............. 20 
1.4.1 Virtual Sectors ................................ ................................ .......................... 20 
1.4.2 Virtual Sectors for EEP1................................ ................................ ........... 21 
1.5 FEE functions ................................ ................................ ................................  21 
1.5.1 FEE_GetVersionInfo ................................ ................................ ................ 21 
1.6 FEE Sector Configuration ................................ ................................ .............. 22 
1.6.1 FEE_VirtualSectorConfiguration ................................ ...............................  22 
1.6.1.1 FEE_VirtualSectorNumber ................................ ................................  22 
1.6.1.2 FEE_VirtualSectorBank ................................ ................................ .... 23 
1.6.1.3 FEE_VirtualSectorStart ................................ ................................ ..... 23 
1.6.1.4 FEE_VirtualSectorEnd ................................ ................................ ...... 24 
1.6.2 Example Virtual Sector Configuration ................................ ....................... 25 
1.7 FEE Block Configuration ................................ ................................ ................ 26 
1.7.1 FEE Block Configuration ................................ ................................ .......... 26 
1.7.1.1 FEE_BlockNumber................................ ................................ ............ 26


## Page 6

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      6 
 
1.7.1.2 FEE_BlockSize ................................ ................................ ................. 27 
1.7.1.3 FEE_NumberOfWriteCycles ................................ ..............................  27 
1.7.1.4 FEE_UseImmediateData ................................ ................................ .. 28 
1.7.1.5 FEE Device Index ................................ ................................ ............. 28 
1.7.1.6 FeeNumberOfDataSets ................................ ................................ ..... 29 
1.7.1.7 FEE EEP Number ................................ ................................ ............. 29 
1.7.2 Example Block Configuration ................................ ................................ ... 30 
1.8 Header Files ................................ ................................ ................................ .. 31 
1.8.1 Header Files for Fee_cfg.h ................................ ................................ ....... 31 
1.8.2 Header Files for Fee_cfg.c ................................ ................................ ....... 31


## Page 7

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      7 
 
1 Introduction 
The following sections describe  each parameter in the Fee_ParamDef.axml file 
used by Code Generation Tool  and the corresponding configuration parameter 
generated. Code Generation Tool  generates two files (Fee_ Cfg.c and Fee_cfg.h) 
depending on the configuration values. This section describes each configuration 
value in the above two files and their relation to the parameter defin ed in the 
Fee_ParamDef.axml file. 
1.1 FEE Published information 
1.1.1 Block OverHead 
Parameter defined in 
Fee_ParamDef.axml 
 
FeeBlockOverhead 
 
Description 
 
Indicates the number of bytes used for Block 
Header. 
 
Generated configuration 
 
FEE_BLOCK_OVERHEAD is set to the value 
assigned to FeeBlockOverhead. 
 
Default Value 
 
0x18 
 
Parameter Range 
 
Fixed to 0x18. 
 
Parameter Type 
 
uint8 
 
Target file 
 
Fee_cfg.h 
1.1.2 Maximum Blocking Time  
Parameter defined in 
Fee_ParamDef.axml 
 
FeeMaximumBlockingTime 
 
Description 
 
Indicates the maximum allowed blocking time for any 
Fee call.  
 
Generated configuration 
 
FEE_MAXIMUM_BLOCKING_TIME is set to the 
value assigned to FeeMaximumBlockingTime. 
Default Value 600.00 
 
Parameter Range 
 
Fixed to 600 µs. 
 
Parameter Type 
 
float 
Target file Fee_cfg.h


## Page 8

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      8 
 
1.1.3 Page OverHead 
Parameter defined in 
Fee_ParamDef.axml 
 
FeePageOverhead 
 
Description 
 
Indicates the Page Overhead in bytes. 
 
Generated configuration 
 
FEE_PAGE_OVERHEAD is set to the value 
assigned to FeePageOverhead. (0x0) 
 
Default Value  
 
0x0 
 
Parameter Range 
 
Fixed to 0x0. 
 
Parameter Type 
 
uint8 
 
Target File 
 
Fee_cfg.h 
1.1.4 Sector OverHead 
Parameter defined in 
Fee_ParamDef.axml 
 
FeeVirtualSectorOverhead 
 
Description 
 
Indicates the number of bytes used for Virtual Sector 
Header. 
 
Generated configuration 
 
FEE_VIRTUAL_SECTOR_OVERHEAD is set to the 
value assigned to FeeVirtualSectorOverhead (0x10). 
 
Default Value 
 
0x10 
 
Parameter Range 
 
Fixed to 0x10. 
 
Parameter Type 
 
uint8 
Target File Fee_cfg.h


## Page 9

AutoSAR FEE Parameter Configuration (Rev 1.8)   
 
 
 
 
Texas Instruments Incorporated                                                      9 
 
1.2 FEE General Settings 
1.2.1 Virtual Page size 
Parameter defined in 
Fee_ParamDef.axml 
 
FeeVirtualPageSize 
 
Description 
 
Indicates the virtual page size in bytes. 
 
Generated configuration 
 
FEE_VIRTUAL_PAGE_SIZE is set to the value 
assigned to FeeVirtualPageSize. (0x8) 
 
Default Value 
 
0x8 
 
Parameter Range 
 
Fixed to 0x8. 
 
Parameter Type 
 
uint8 
 
Target File 
 
Fee_cfg.h 
 
 
 
 
 
 
1.2.2  Driver Index 
Parameter defined in 
Fee_ParamDef.axml 
 
FeeIndex 
 
Description 
 
In


> **Note:** remaining pages truncated. See the original PDF in the repository.
