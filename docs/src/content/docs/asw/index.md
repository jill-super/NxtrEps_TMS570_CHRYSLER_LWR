---
title: "Application Software"
description: "AUTOSAR Application Software components — Application (`Ap_*`) and Sensor-Actuator (`Sa_*`) Software Components. All are Nexteer in-house logic."
sidebar:
  order: 0
---

# Application Software

AUTOSAR Application Software components — Application (`Ap_*`) and Sensor-Actuator (`Sa_*`) Software Components. All are Nexteer in-house logic on a Vector MICROSAR Runtime Environment frame.

> Naming: titles lead with the descriptive long name; the short folder name (for example `Assist`) and the Software Component name (for example `Ap_Assist` Application, `Sa_*` Sensor/Actuator) follow in parentheses for traceability.


## Modules

| Module | Origin | Purpose |
| --- | --- | --- |
| [Absolute Hardware Position Serial Communication (`AbsHwPosScom`)](./abshwposscom/) | Custom | AUTOSAR software component `Ap_AbsHwPosScom` for the Chrysler LWR EPS — design coverage: AbsHwPosSCom. |
| [Active Pull Compensation (`ActivePull`)](./activepull/) | Custom | AUTOSAR software component `Ap_ActivePull` for the Chrysler LWR EPS — design coverage: Active Pull Comp. |
| [Arbiter Limiter (`ArbLmt`)](./arblmt/) | Custom | AUTOSAR software component `Ap_ArbLmt` for the Chrysler LWR EPS — design coverage: Arbiter Limiter Chrysler. |
| [Steering Assist Control (`Assist`)](./assist/) | Custom | AUTOSAR software component `Ap_Assist` for the Chrysler LWR EPS — design coverage: Assist. |
| [Assist Safety Firewall (`AssistFirewall`)](./assistfirewall/) | Custom | AUTOSAR software component `Ap_AssistFirewall` for the Chrysler LWR EPS — design coverage: Assist Firewall. |
| [Assist Sum Limit – Current Mode (`AstLmt_CM`)](./astlmt-cm/) | Custom | AUTOSAR software component `Ap_AstLmt` for the Chrysler LWR EPS — design coverage: Assist Sum Limit CurrentMode; AstLmt CM IntegrationManual |
| [Average Friction Learning (`AvgFricLrn`)](./avgfriclrn/) | Custom | AUTOSAR software component `Ap_AvgFricLrn` for the Chrysler LWR EPS — design coverage: Average Friction Learning. |
| [Battery Voltage Monitoring (`BatteryVoltage`)](./batteryvoltage/) | Custom | AUTOSAR software component `Ap_BatteryVoltage` for the Chrysler LWR EPS — design coverage: Battery Voltage. |
| [Bulk Capacitor Pre-Charge (`BkCpPc`)](./bkcppc/) | Custom | AUTOSAR software component `Sa_BkCpPc` for the Chrysler LWR EPS — design coverage: Bulk Cap Precharge. |
| [Battery Voltage Diagnostics (`BVDiag`)](./bvdiag/) | Custom | AUTOSAR software component `Ap_BVDiag` for the Chrysler LWR EPS — design coverage: Battery Voltage Diagnostics. |
| [Current-Mode Motor Current Sensing (`CmMtrCurr`)](./cmmtrcurr/) | Custom | AUTOSAR software component `Sa_CmMtrCurr` for the Chrysler LWR EPS — design coverage: CmMtrCurr. |
| [Controlled Disable and Shutdown (`CtrldDisShtdn`)](./ctrlddisshtdn/) | Custom | AUTOSAR software component `Ap_CtrldDisShtdn` for the Chrysler LWR EPS — design coverage: Controller Disable. |
| [Controller Temperature Monitoring (`CtrlTemp`)](./ctrltemp/) | Custom | AUTOSAR software component `Sa_CtrlTemp` for the Chrysler LWR EPS — design coverage: Controller Temperature. |
| [Current Reasonableness Diagnostics (`CurrReasDiag`)](./currreasdiag/) | Custom | AUTOSAR software component `Ap_CurrReasDiag` for the Chrysler LWR EPS system on the TMS570. |
| [Steering Damping Control (`Damping`)](./damping/) | Custom | AUTOSAR software component `Ap_Damping` for the Chrysler LWR EPS — design coverage: Damping. |
| [Damping Safety Firewall (`DampingFirewall`)](./dampingfirewall/) | Custom | AUTOSAR software component `Ap_DampingFirewall` for the Chrysler LWR EPS — design coverage: Damping Firewall. |
| [Diagnostic Manager (`DiagMgr`)](./diagmgr/) | Custom | Core Diagnostic Manager Functionality |
| [Electric Power Consumption Monitoring (`ElePwr`)](./elepwr/) | Custom | AUTOSAR software component `Ap_ElePwr` for the Chrysler LWR EPS — design coverage: Electric Power Consumption. |
| [End-of-Travel Actuator Management (`EOTActuatorMng`)](./eotactuatormng/) | Custom | AUTOSAR software component `Ap_EOTActuatorMng` for the Chrysler LWR EPS — design coverage: End of Travel Actuator Management. |
| [Frequency-Dependent Damping and Inertia Compensation (`FrqDepDmpnInrtCmp`)](./frqdepdmpninrtcmp/) | Custom | AUTOSAR software component `Ap_FrqDepDmpnInrtCmp` for the Chrysler LWR EPS — design coverage: Frequency Dependant Damping And Inertia Compen |
| [Global Signal Overwrite Diagnostics (`Gsod`)](./gsod/) | Custom | AUTOSAR software component `Ap_Gsod` for the Chrysler LWR EPS — design coverage: Gsod. |
| [Haptic Lane Feedback Torque Overlay (`HaLFTO`)](./halfto/) | Custom | AUTOSAR software component `Ap_HaLFTO` for the Chrysler LWR EPS — design coverage: HaLFTO. |
| [High-Frequency Assist Control (`HighFreqAssist`)](./highfreqassist/) | Custom | AUTOSAR software component `Ap_HighFreqAssist` for the Chrysler LWR EPS — design coverage: High Frequency Assist. |
| [High-Load Stall Protection (`HiLoadStall`)](./hiloadstall/) | Custom | AUTOSAR software component `Ap_HiLoadStall` for the Chrysler LWR EPS — design coverage: HiLoadStall. |
| [Hardware Power-Up Sequencing (`HwPwUp`)](./hwpwup/) | Custom | AUTOSAR software component `Ap_HwPwUp` for the Chrysler LWR EPS — design coverage: Hardware Power Up. |
| [Handwheel Torque Sensing (`HwTrq`)](./hwtrq/) | Custom | AUTOSAR software component `Sa_HwTrq` for the Chrysler LWR EPS — design coverage: Handwheel Torque 2; Handwheel Torque. |
| [Hysteresis Compensation (`HystComp`)](./hystcomp/) | Custom | AUTOSAR software component `Ap_HystComp` for the Chrysler LWR EPS — design coverage: Hysteresis Compensation. |
| [Limiter Conditioning (`LmtCod`)](./lmtcod/) | Custom | AUTOSAR software component `Ap_LmtCod` for the Chrysler LWR EPS — design coverage: Limiter Conditioning. |
| [End-of-Travel Learning (`LrnEOT`)](./lrneot/) | Custom | AUTOSAR software component `Ap_LrnEOT` for the Chrysler LWR EPS — design coverage: LearnEOT. |
| [Motor Control – Current Mode (`MtrCtrl_CM`)](./mtrctrl-cm/) | Custom | AUTOSAR software component `Ap_CurrCmd` for the Chrysler LWR EPS — design coverage: CurrCmd; CurrParamComp. |
| [Motor Position Sensing (`MtrPos`)](./mtrpos/) | Custom | AUTOSAR software component `Sa_MtrPos` for the Chrysler LWR EPS — design coverage: Motor Position 2; Motor Position 3. |
| [Motor Temperature Estimation (`MtrTempEst`)](./mtrtempest/) | Custom | AUTOSAR software component `Ap_MtrTempEst` for the Chrysler LWR EPS — design coverage: Motor Temperature Estimation. |
| [Motor Velocity Sensing (`MtrVel`)](./mtrvel/) | Custom | AUTOSAR software component `Sa_MtrVel` for the Chrysler LWR EPS — design coverage: MotorVelocity2; MotorVelocity3. |
| [Over-Voltage Monitoring (`OvrVoltMon`)](./ovrvoltmon/) | Custom | AUTOSAR software component `Sa_OvrVoltMon` for the Chrysler LWR EPS — design coverage: OverVoltageMonitor. |
| [Park Assist Torque Overlay (`PAwTO`)](./pawto/) | Custom | AUTOSAR software component `Ap_PAwTO` for the Chrysler LWR EPS — design coverage: PAwTO. |
| [Signal Polarity Management (`Polarity`)](./polarity/) | Custom | AUTOSAR software component `Ap_Polarity` for the Chrysler LWR EPS — design coverage: Polarity. |
| [Power Limit Function – Current Mode (`PwrLmtFuncCr`)](./pwrlmtfunccr/) | Custom | AUTOSAR software component `Ap_PwrLmtFuncCr` for the Chrysler LWR EPS — design coverage: Power Limit Function CM. |
| [Steering Return Control (`Return`)](./return/) | Custom | AUTOSAR software component `Ap_Return` for the Chrysler LWR EPS — design coverage: Return. |
| [Return Safety Firewall (`ReturnFirewall`)](./returnfirewall/) | Custom | AUTOSAR software component `Ap_ReturnFirewall` for the Chrysler LWR EPS — design coverage: Return Firewall. |
| [Signal Conditioning (`SgnlCond`)](./sgnlcond/) | Custom | AUTOSAR software component `Ap_SignlCondn` for the Chrysler LWR EPS — design coverage: SignalConditioning. |
| [Shutdown Mechanisms (`ShtdnMech`)](./shtdnmech/) | Custom | AUTOSAR software component `Sa_ShtdnMech` for the Chrysler LWR EPS — design coverage: Shutdown Mechanisms. |
| [Stability Compensation (`StabilityComp`)](./stabilitycomp/) | Custom | AUTOSAR software component `Ap_StabilityComp` for the Chrysler LWR EPS — design coverage: StabilityCompensation2; StabilityCompensation. |
| [System State and Mode Management (`StaMd`)](./stamd/) | Custom | Core States and Modes Module |
| [Stability Control Torque Overlay (`StbCTO`)](./stbcto/) | Custom | AUTOSAR software component `Ap_StbCTO` for the Chrysler LWR EPS — design coverage: StabiliCtrlTorqueOverlay. |
| [State Output Control (`StOpCtrl`)](./stopctrl/) | Custom | AUTOSAR software component `Ap_StOpCtrl` for the Chrysler LWR EPS — design coverage: State Output Control. |
| [Supply Voltage and Motor Driver Diagnostics (`SVDiag`)](./svdiag/) | Custom | AUTOSAR software component `Ap_DigPhsReasDiag` for the Chrysler LWR EPS — design coverage: DigPhsReasDiag; Motor Driver Diagnostics. |
| [Thermal Duty Cycle Management (`ThrmDutyCycle`)](./thrmdutycycle/) | Custom | AUTOSAR software component `Ap_ThrmlDutyCycle` for the Chrysler LWR EPS — design coverage: Thermal Duty Cycle. |
| [Temporal Monitoring (`TmprlMon`)](./tmprlmon/) | Custom | AUTOSAR software component `Sa_TmprlMon` for the Chrysler LWR EPS — design coverage: Temporal Monitor 2; Temporal Monitor. |
| [Torque Reasonableness Diagnostics (`TqRsDg`)](./tqrsdg/) | Custom | AUTOSAR software component `Ap_TqRsDg` for the Chrysler LWR EPS — design coverage: TorqueReasonableDiagnostics. |
| [Tuning Selection Authority (`TuningSelAuth`)](./tuningselauth/) | Custom | AUTOSAR software component `Ap_TuningSelAuth` for the Chrysler LWR EPS — design coverage: Tuning Select Authority. |
| [Vehicle Speed Limiter (`VehSpdLmt`)](./vehspdlmt/) | Custom | AUTOSAR software component `Ap_VehSpdLmt` for the Chrysler LWR EPS — design coverage: VehSpdLmt. |
| [Wheel Imbalance Rejection (`WhlImbRej`)](./whlimbrej/) | Custom | AUTOSAR software component `Ap_WhlImbRej` for the Chrysler LWR EPS — design coverage: Wheel Imbalance Rejection. |
