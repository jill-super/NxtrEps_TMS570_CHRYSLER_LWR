---
title: "AutoSAR FEE User Guide"
description: "Converted from AutoSAR FEE User Guide.pdf"
---

> **Source:** `Fee/doc/AutoSAR FEE User Guide.pdf` (325,561 bytes, `PDF`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

*PDF original: 53 page(s). Text extracted below (first 15 pages shown). Layout, figures and diagrams are not preserved — consult the original file in the repository for exact rendering.*


## Page 1

AutoSAR FEE Driver 
 
 
 
 
 
 
 
 
 
 
 
 
Version 1.14 
 
Aug05, 2016 
 
Copyright  Texas Instruments Incorporated 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
User's Guide
                User Manual


## Page 2

Read This First 
  
 
 2 
IMPORTANT NOTICE 
 
Texas Instruments and its subsidiaries (TI) reserve the right to make changes to their products or to 
discontinue any product or service without notice, and advise customers to obtain the latest version of 
relevant information to verify, before placing orders, that information being relied on is current and 
complete. All products are sold subject to the terms and conditions of sale supplied at the time of order 
acknowledgment, including those pertaining to warranty, patent infringement, and limitation of liability. 
TI warrants performance of its products to the specifications appl icable at the time of sale in 
accordance with TI’s standard warranty. Testing and other quality control techniques are utilized to the 
extent TI deems necessary to support this warranty. Specific testing of all parameters of each device is 
not necessarily performed, except those mandated by government requirements. 
Customers are responsible for their applications using TI components. 
In order to minimize risks associated with the customer’s applications, adequate design and operating 
safeguards ought to be provided by the customer so as to minimize inherent or procedural hazards. 
TI assumes no liability for applications assistance or customer product design. TI does not warrant or 
represent that any license, either express or implied, is granted under any patent right, copyright, mask 
work right, or other intellectual property right of TI covering or relating to any combination, machine, or 
process in which such products or services might be or are used. TI’s publication of information 
regarding any third par ty’s products or services does not constitute TI’s approval, license, warranty or 
endorsement thereof. 
Reproduction of information in TI data books or data sheets is permissible only if reproduction is without 
alteration and is accompanied by all associated warranties, conditions, limitations and notices.  
Representation or reproduction of this information with alteration voids all warranties provided for an 
associated TI product or service  is an unfair and deceptive business practice, and TI is neither 
responsible nor liable for any such use. 
Resale of TI’s products or services with statements different from or beyond the parameters  stated by 
TI for that product or service voids all express and any implied warranties for the associated TI product 
or service, is an unfair and deceptive business practice, and TI is not responsible nor liable for any such 
use. 
Also see: Standard Terms and Conditions of Sale for Semiconductor Products.   
www.ti.com/sc/docs/stdterms.htm 
Mailing Address: 
Texas Instruments 
Post Office Box 655303 
Dallas, Texas 75265 
 
Copyright © 2012, Texas Instruments Incorporated


## Page 3

3 
Preface 
Read This First 
 
About This Manual 
This user manual serves as a software programmer’s handbook for working with the 
AutoSAR FEE Driver . It provides necessary information regarding how to build and use AutoSAR 
FEE Driver in user systems and applications.  
It also provides details regarding the AutoSAR FEE Driver functionality, the requirements it 
places on the hardware and software environment where it can be deployed, how to customize/ 
configure it etc. It also provides supplementary information regarding steps to be followed for proper 
installation/ un-installation of the AutoSAR FEE Driver.  
 
Important Notes 
Customers have to include F021 API library  v2.01.01 or greater. 
Abbreviations 
 
1-1.  Table of Abbreviations 
 
Abbreviation Description 
AutoSAR FEE Driver This is TI coined name for the product. 
FEE Flash EEPROM Emulation


## Page 4

Read This First 
  
 
 4 
Document Revision History  
 
Version Date Revision History 
1.0 09/25/2012 Initial version 
1.1 11/08/2012 Changes for EA2 
1.2 11/21/2012 Additional changes for BETA 
1.3 12/12/2012 Add error recovery prototypes 
1.4 06/11/2013 Add software revision history. Added new 
configuration tags information. 
1.5 10/23/2013 Updated software revision history. 
1.6 01/03/2014 Add new configuration parameter for  
address range check for Read/Write. 
Check for Multi bit error during Read. 
MISRA fixes. 
1.7 09/11/2014 Manual Suspend/Resume feature added. 
1.8 10/15/2014 RAM Optimization changes. 
1.9 10/31/2014 Support TMS570LS05xx, TMS570LS07xx, 
TMS570LS09xx. Range updated for 
FEE_VirtualSectorNumber, Virtual Sectors 
1.10 01/21/2015 Changes related to unification of Archer and 
Champion. 
1.11 10/14/2015 Bugfix for block lost issue. 
1.12 11/20/2015 Enhancement for “Do not change FEE state 
to IDLE after copying of the blocks is 
completed” 
1.13 03/15/2016 Bugfix for “Block offset address does not get 
updated correctly, if copy operation was 
interrupted.” Added section “Important Notes” 
1.14 08/05/2016 Updated software revision history. 
 
Software Revision History  
 
Version Date Revision History 
00.01.00 08/31/2012 Initial version


## Page 5

5 
00.01.01 10/29/2012 Changes for implementing Error Recovery 
00.01.02 11/30/2012 Misra Fixes, Memory segmentation changes 
00.01.03 01/14/2013 Changes as requested by Vector. If there is an immediate 
erase/invalidate block  request before writing of a block ,  
API should return the job status as JOB_OK. 
00.01.04 02/12/2013 Integration issues fix.  Fixed issues regarding integration of 
FEE with NvM. 
00.01.05 03/04/2013 Added Deleting a block feature 
00.01.06 03/11/2013 Added feature : copying of unconfigured blocks. 
00.01.07 03/15/2013 Added feature : Number of 8 bytes writes, fixed issue with 
copy blocks. 
00.01.08 04/05/2013 Added feature : CRC check for unconfigured  blocks, Main 
function modified to complete writes as fast as possible, 
Added Non polling mode support. 
00.01.09 04/19/2013 Warning removal, Added feature comparison of data 
during write. 
00.01.10 06/11/2013 Fixed issue with erase sector. Also fixed issue with 2 
EEPROM’s where if one EEPROM is locked with error 
condition, other EEPROM will not get locked. 
01.10.00 10/23/2013 Updated software to support more than two VS. 
01.20.00 01/03/2014 Add new configuration parameter for address range check 
for Read/Write. 
Check for Multi bit error during Read. 
MISRA fixes. 
01.20.01 09/11/2014 Manual Suspend/Resume feature added. 
01.21.00 10/15/2014 RAM Optimization changes. New configuration parameter 
FEE_TOTAL_BLOCKS_DATASETS added. 
01.22.00 01/21/2015 Add new Configuration parameters. 
FEE_VIRTUALSECTOR_SIZE, 
FEE_PHYSICALSECTOR_SIZE,  
FEE_GENERATE_DEVICEANDVIRTUALSECTORSTRUC 
 
01.23.00 10/14/2015 Bugfix for block lost issue. 
01.23.01 11/20/2015 Enhancement for “Do not change FEE state to IDLE after 
copying of the blocks is completed” 
01.23.02 03/15/2016 Bugfix for “Block offset address does not get updated 
correctly, if copy operation was interrupted.”


## Page 6

Read This First 
  
 
 6 
01.23.03 08/05/2016 Fee_Getstatus API should return MEMIF_BUSY, if FEE is 
doing internal operations.


## Page 7

7 
Contents 
 
Read This First ................................................................................................................... 3 
Contents ............................................................................................................................... 7 
Table of tables .................................................................................................................... 9 
Table of figures ................................................................................................................. 10 
Chapter 1 ............................................................................................................................ 11 
AutoSAR FEE Driver Introduction ............................................................................... 11 
1.1 Overview .................................................................................................  12 
1.1.1 Functions supported in the AutoSAR FEE Driver ............................ 12 
1.1.2 System Requirements ..................................................................... 13 
Chapter 2 ............................................................................................................................ 14 
AutoSAR FEE Driver Design Overview ...................................................................... 14 
Overview ........................................................................................................... 14 
2.1 Flash EEPROM Emulation Methodology ................................................ 15 
2.1.1 Virtual Sector Organization .............................................................. 15 
2.1.2 Data Block Organization .................................................................. 18 
2.1.3 Available Commands ....................................................................... 20 
2.1.4 Status Codes ................................................................................... 20 
2.1.5 Job Result........................................................................................ 20 
Chapter 3 ............................................................................................................................ 21 
Integration Guide ............................................................................................................. 21 
3.1 Error Recovery Implementation .............................................................. 21 
3.2 Single and Double bit Error Corrections ................................................. 22 
3.3 Memory Mapping .................................................................................... 22 
3.4 Symbolic Constants and Enumerated Data types .................................. 23 
3.5 Data Structures ....................................................................................... 26 
3.6 AutoSAR FEE Driver Configuration Parameters ..................................... 27 
3.6.1 Block Overhead ............................................................................... 27 
3.6.2 Maximum Blocking Time ................................................................. 27 
3.6.3 Page Overhead ............................................................................... 27 
3.6.4 Sector  Overhead ............................................................................ 27 
3.6.5 Virtual Page Size ............................................................................. 28 
3.6.6 Driver Index ..................................................................................... 28 
3.6.7 Job Error Notification ....................................................................... 28


## Page 8

Contents 
  
 
 8 
3.6.8 Job End  Notification ........................................................................ 28 
3.6.9 FEE Operating Frequency................................................................ 29 
3.6.10 Polling Mode .................................................................................... 29 
3.6.11 Enable Error Correction ................................................................... 29 
3.6.12 Error Correction Handling................................................................. 30 
3.6.13 Block Write Counter Save ................................................................ 30 
3.6.14 Enable CRC ..................................................................................... 30 
3.6.15 NumberOfEEPs ................................................................................ 30 
3.6.16 Number of Blocks ............................................................................. 31 
3.6.17 Number of Virtual Sectors ................................................................ 31 
3.6.18 Number of Virtual Sectors on EEP1 ................................................. 31 
3.6.1


> **Note:** remaining pages truncated. See the original PDF in the repository.
