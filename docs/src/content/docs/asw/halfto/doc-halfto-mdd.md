---
title: "Haptic Lane Feedback Torque Overlay (HaLFTO)"
description: "Converted from HaLFTO_MDD.docx"
---

> **Source:** `HaLFTO/doc/HaLFTO_MDD.docx` (828,284 bytes, `DOCX`)
> Converted automatically for web viewing. The original file in the repository remains authoritative.

# Module -- HaLFTO


# High-Level Description

This function describes the activation logic used to implement the torque overlay functionality related to lane departure warning with haptic lane feedback.


# Figures


## Component Diagram


### Diagram – Function HaLFTO_Per1

This diagram describes the functional characteristics and data flow of a given function.


# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.


## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.


# Constant Data Dictionary


## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.


## Program(fixed) Constants


### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.


#### Local


#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.


# Functions/Macros used by the Sub-Modules


## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m

Rte_Call_SystemTime_GetSystemTime_mS_u32

Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16

Rte_Call_NxtrDiagMgr_GetNTCFailed

Rte_Call_NxtrDiagMgr_SetNTCStatus

Rte_Call_HaLFState_SCom_Transition


## Data Hiding Functions

Rte_Mode_SystemState_Mode


## Local Functions/Macros Used by this MDD only


### Common HwTrqVehSpdRevGear Check


#### Description

HaLFEnableRqst_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFEnableRqst_Cnt_lgc()

HwTorque_HwNm_T_f32 = Rte_IRead_HaLFTO_Per1_HwTorque_HwNm_f32()

HaLFTrqOvReverseGearEngage_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFTrqOvReverseGearEngage_Cnt_lgc()

VehicleSpeed_Kph_T_f32 = Rte_IRead_HaLFTO_Per1_VehicleSpeed_Kph_f32()

HaLFDiagStatus_Cnt_T_enum = NTC_STATUS_PASSED


#### Hw Trq Check


#### Vehicle Speed Check


#### Reverse Gear Check


# Software Module Implementation


## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.


## Initialization Functions


### Init: HaLFTO_Init1(void)


#### Design Rationale

The init function here sets all timers to some valid value, and informs SCom that the module is transitioning into the inactive state.


#### Initial State Transition

Rte_Call_HaLFState_SCom_Transition(D_HALFSTATEINACTIVE_CNT_U08)


#### Module Internal

Rte_Call_SystemTime_GetSystemTime_mS_u32(&Time_mS_u32)

HaLFTO_IncorHaLFActvnHwTrqTimer_mS_M_u32 = Time_mS_u32

HaLFTO_IncorHaLFActvnVehSpdTimer_mS_M_u32 = Time_mS_u32

HaLFTO_IncorHaLFActvnRevGearTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactHwTrqTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactVehSpdTimer_mS_M_u32 = Time_mS_u32

HaLFTO_HaLFDeactRevGearTimer_mS_M_u32 = Time_mS_u32

HaLFTO_DSTSyncTimer_mS_M_u32 = Time_mS_u32

HaLFTO_LimitPercentFilteredTimer_mS_M_u32 = Time_mS_u32

(void)Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_VLF_04, 0x0U, NTC_STATUS_PASSED);


## Periodic Functions


### Per: _Per1(void)


#### Design Rationale

None


#### Program Flow Start

Rte_Call_HaLFTO_Per1_CP0_CheckpointReached()


#### Store Module Inputs to Local copies

DSTState_Cnt_T_u08 = Rte_IRead_HaLFTO_Per1_DSTState_Cnt_u08()

DiagStsNonRecRmpToZeroFltPres_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_DiagStsNonRecRmpToZeroFltPres_Cnt_lgc()

DiagStsRecRmpToZeroFltPres_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_DiagStsRecRmpToZeroFltPres_Cnt_lgc()

HaLFEnableRqst_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFEnableRqst_Cnt_lgc()

HaLFErrInterfaceActive_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFErrInterfaceActive_Cnt_lgc()

HaLFExtSystemFltActive_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFExtSystemFltActive_Cnt_lgc()

HaLFFuncPresent_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFFuncPresent_Cnt_lgc()

HaLFIntSystemFltActive_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFIntSystemFltActive_Cnt_lgc()

HaLFSWATrqFail_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFSWATrqFail_Cnt_lgc()

HaLFSlewComplete_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_HaLFSlewComplete_Cnt_lgc()

LimitPercentFiltered_Uls_T_f32 = Rte_IRead_HaLFTO_Per1_LimitPercentFiltered_Uls_f32()

TOEOLDisable_Cnt_T_lgc = Rte_IRead_HaLFTO_Per1_TOEOLDisable_Cnt_lgc()


#### Initialize Faults


#### Incorrect HaLF Activation Diagnostic


#### HaLF Deactivation Diagnostic


#### HaLF Deactivation Diagnostic continued…


#### HalF Torque Overlay Enable


#### Transition Vector Logic


#### Inactive Transitions


#### Active Transitions


#### Recoverable Transitions


#### Transitions Complete


#### Store Local copy of outputs into Module Outputs

Rte_IWrite_HaLFTO_Per1_HaLFState_Cnt_u08(HaLFTO_State_Cnt_M_u08)

Rte_IWrite_HaLFTO_Per1_HaLFSuspend_Cnt_lgc(HaLFSuspend_T_lgc)


#### Program Flow End

Rte_Call_HaLFTO_Per1_CP1_CheckpointReached()


## Execution Requirements


### Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design


### Execution Requirements for Serial Communication Functions


# Memory Map Definition Requirements


## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.


## Local Functions

This table identifies the software segments for local functions identified in this module.


# Known Issues / Limitations With Design

Inline functions in GlobalMacro.h are not unit tested.


# Revision Control Log


**Table 1**

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| HaLFEnableRqst_Cnt_lgc | HaLFEnableRqst_Cnt_lgc | HaLFActive_Cnt_lgc |
|  |  | HaLFState_Cnt_u08 |
| HaLFIntSystemFltActive_Cnt_lgc | HaLFIntSystemFltActive_Cnt_lgc | HaLFSuspend_Cnt_lgc |
| HaLFErrInterfaceActive_Cnt_lgc | HaLFErrInterfaceActive_Cnt_lgc |  |
| HaLFExtSystemFltActive_Cnt_lgc | HaLFExtSystemFltActive_Cnt_lgc |  |
| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |
| HaLFSWATrqFail_Cnt_lgc | HaLFSWATrqFail_Cnt_lgc |  |
| HaLFTrqOvReverseGearEngage_Cnt_lgc | HaLFTrqOvReverseGearEngage_Cnt_lgc |  |
| HaLFSlewComplete_Cnt_lgc | HaLFSlewComplete_Cnt_lgc |  |
| HaLFFuncPresent_Cnt_lgc | HaLFFuncPresent_Cnt_lgc |  |
| HwTorque_HwNm_f32 | HwTorque_HwNm_f32 |  |
| SystemState_Mode | SystemState_Mode |  |
| LimitPercentFiltered_Uls_f32 | LimitPercentFiltered_Uls_f32 |  |
| DSTState_Cnt_u08 | DSTState_Cnt_u08 |  |
| TOEOLDisable_Cnt_lgc | TOEOLDisable_Cnt_lgc |  |
|  |  |  |
|  |  |  |


**Table 2**

| Variable Name | Resolution | Legal Range (min) | Legal Range (max) | Software Segment |
| --- | --- | --- | --- | --- |
| HaLFTO_DeactDSTStateChkFail_Cnt_D_lgc | 1 | FALSE | TRUE | HALFTO_START_SEC_VAR_CLEARED_BOOLEAN |
| HaLFTO_IncorHaLFActvnFailed_Cnt_M_lgc | 1 | FALSE | TRUE | HALFTO_START_SEC_VAR_CLEARED_BOOLEAN |
| HaLFTO_HaLFDeactLongFailed_Cnt_M_lgc | 1 | FALSE | TRUE | HALFTO_START_SEC_VAR_CLEARED_BOOLEAN |
|  |  |  |  |  |
| HaLFTO_IncorHaLFActvnHwTrqTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_IncorHaLFActvnVehSpdTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_IncorHaLFActvnRevGearTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_HaLFDeactHwTrqTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_HaLFDeactVehSpdTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_HaLFDeactRevGearTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_DSTSyncTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
| HaLFTO_LimitPercentFilteredTimer_mS_M_u32 | 1 | FULL | FULL | HALFTO_START_SEC_VAR_NOINIT_32 |
|  |  |  |  |  |
|  |  |  |  |  |
| HaLFTO_State_Cnt_M_u08 | 1 | 0 | 3 | HALFTO_START_SEC_VAR_CLEARED_8 |


**Table 3**

| Constant Name |
| --- |
| k_HaLFActvHwTrqTime_mS_u16 |
| k_HaLFActvMaxHwTrq_mS_f32 |
| k_HaLFActvVehSpdTime_mS_u16 |
| k_HaLFActvMinVehSpd_Kph_f32 |
| k_HaLFActvMaxVehSpd_Kph_f32 |
| k_HaLFActvRevGearTime_mS_u16 |
| k_HaLFDeactHwTrqTime_mS_u16 |
| k_HaLFDeactMaxHwTrq_HwNm_f32 |
| k_HaLFDeactVehSpdTime_mS_u16 |
| k_HaLFDeactMinVehSpd_Kph_f32 |
| k_HaLFDeactMaxVehSpd_Kph_f32 |
| k_HaLFDeactRevGearTime_mS_u16 |
| k_HaLFDSTSyncTime_mS_u16 |
| k_TrqOverlayLimitPerc_Uls_f32 |
| k_TrqOverlaySuspendTime_mS_u16 |


**Table 4**

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| D_HALFSTATEINACTIVE_CNT_U08 | 1 | Counts | 0 |
| D_HALFSTATEACTIVE_CNT_U08 | 1 | Counts | 1 |
| D_HALFSTATEIHIBITED_CNT_U08 | 1 | Counts | 2 |
| D_HALFSTATERECOVERABLE_CNT_U08 | 1 | Counts | 3 |
| D_DSTACTIVE1_CNT_U08 | 1 | Counts | 5 |
| D_DSTACTIVE2_CNT_U08 | 1 | Counts | 6 |
| D_DSTACTIVE3_CNT_U08 | 1 | Counts | 7 |
| D_INCORHALFACTVNMASK_CNT_U08 | 1 | Counts | 1 |
| D_HALFDEACTLONGMASK_CNT_U08 | 1 | Counts | 2 |


**Table 5**

| Constant Name |
| --- |
| D_ZERO_ULS_F32 |
| FLT_EPSILON |


**Table 6**

| Function Name | HwTrqVehSpdRevGearCheck | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | HwTrqTime_mS_T_u16 | Uint16 | 0 | FULL | 0 |
|  | HwTrqTimerPtr_mS_T_u32 | Uint32* | 0 | FULL | 0 |
|  | MaxHwTrq_HwNm_T_f32 | float32 | 0.0 | 10.0 | 0.00390625 |
|  | VehSpdTime_mS_T_u16 | Uint16 | 0 | FULL | 0 |
|  | VehSpdTimerPtr_mS_T_u32 | Uint32* | 0 | FULL | 0 |
|  | MinVehSpd_Kph_T_f32 | float32 | 0 | 255 | .0078125 |
|  | MaxVehSpd_Kph_T_f32 | float32 | 0 | 255 | .0078125 |
|  | RevGearChkTime_mS_T_u16 | Uint16 | 0 | FULL | 0 |
|  | RevGearTimerPtr_mS_T_u32 | Uint32* | 0 | FULL | 0 |
| Return Value | HaLFDiagStatus_Cnt_T_enum | Uint8 NxtrDiagMgrStatus | 0 | 3 | 0 |


**Table 7**

| Data | Value |
| --- | --- |
| DSTState_Cnt_u08 | 0 |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc | FALSE |
| DiagStsRecRmpToZeroFltPres_Cnt_lgc | FALSE |
| HaLFActive_Cnt_lgc | FALSE |
| HaLFEnableRqst_Cnt_lgc | FALSE |
| HaLFErrInterfaceActive_Cnt_lgc | FALSE |
| HaLFExtSystemFltActive_Cnt_lgc | FALSE |
| HaLFFuncPresent_Cnt_lgc | FALSE |
| HaLFIntSystemFltActive_Cnt_lgc | FALSE |
| HaLFSWATrqFail_Cnt_lgc | FALSE |
| HaLFSlewComplete_Cnt_lgc | FALSE |
| HaLFState_Cnt_u08 | 0 |
| HaLFSuspend_Cnt_lgc | FALSE |
|  | 0 |
| HwTorque_HwNm_f32 | 0 |
| LimitPercentFiltered_Uls_f32 | 0 |
| HaLFTrqOvReverseGearEngage_Cnt_lgc | FALSE |
| VehicleSpeed_Kph_f32 | 0 |
| TOEOLDisable_Cnt_lgc | FALSE |
|  |  |
|  |  |


**Table 8**

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| HaLFTO_Per1 | 2ms | Warm Init, Disable, Operate |


**Table 9**

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |


**Table 10**

| Name of Sub Module | Software Segment |
| --- | --- |
| HaLFTO_Init1 | RTE_START_SEC_AP_HALFTO_APPL_CODE |
| HaLFTO_Per1 | RTE_START_SEC_AP_HALFTO_APPL_CODE |


**Table 11**

| Name of Sub Module | Software Segment |
| --- | --- |
| HwTrqVehSpdRevGearCheck | RTE_AP_HALFTO_APPL_CODE |


**Table 12**

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1 | Initial component creation. | 5-Nov-12 | BWL |
| 2 | Corrected vehicle speed check Incorrect HaLF activation(DST Active State Deactivation) | 20-Feb-13 | SR |
| 3 | Corrected Transition T5 from Recoverable to Inactive as per anomaly 4527 | 26-Feb-13 | SR |
| 4 | Update to FDD 40D v004 | 09-May-13 | BDO |
| 5 | Updated to CF 08A V001 | 09-Jul-13 | SP |
| 6 | Added logic to pass the NTCs if the enable criteria is FALSE. | 08-Oct-13 | MR |
| 7 | Updated to FDD CF-08C v004 | 23-Jan-14 | VT |
| 8 | Updated to FDD CF-08C v005 | 04-Feb-14 | VT |
| 9 | Unit Testing Finding Fixes | 20-Feb-14 | KPIT-PM |
| 10 | Updated to FDD CF-08C v006 | 24-Feb-14 | VT |
| 11 | Updated to FDD CF-08C v007 | 06-Mar-14 | VT |
| 12 | Updated per Design Review and Updated to FDD CF-08Cv008 | 24-Apr-14 | M. Story |
|  |  |  |  |
