# LS_UP Level Shifter Netlist Documentation

## Netlist
*Status: derived*

.subckt LS_UP IN OUT VDDL VDDH VSS
XI IN INB VDDL VSS LS_UP_LS_IN
XC IN INB OUT VDDH VSS LS_UP_LS_CORE
.ends

## Simulation Summary (TT Corner, 27 °C)
*Status: simulated functional*

The LS_UP level shifter was simulated across the full supply sweep. All numbers are taken directly from the LS_UP simulation results (TT corner, 27 °C).

| VDDL (V) | VDDH (V) | I_VDDH_in0 (nA) | I_VDDH_in1 (nA) | I_VDDL_in1 (nA) | tpd_in_rise (ns) |
|----------|----------|----------------|----------------|----------------|-----------------|
| 1.4 | 3.3 | 0.016 | 0.020 | 0.001 | 0.30 |
| 1.8 | 3.3 | 0.016 | 0.020 | 0.002 | 0.213 |
| 3.3 | 3.3 | 0.016 | 0.020 | 0.003 | 0.053 |
| 1.4 | 5.5 | 0.034 | 0.039 | 0.001 | 0.349 |
| 1.8 | 5.5 | 0.034 | 0.039 | 0.002 | 0.228 |
| 3.3 | 5.5 | 0.034 | 0.039 | 0.003 | 0.055 |

All functional checks passed for each supply point.

## Facts from the design database (generated, not written by the assistant)

**LS_UP_LS_IN** - kind `custom`, source: reference level_shifter.sp:LS_IN
- Contents: 2 transistor(s) directly; ports IN, INB, VDDL, VSS
- Testbench checks: nothing (no testbench)
- Functional simulation: not run
- Layout: not generated

**LS_UP_LS_CORE** - kind `custom`, source: reference level_shifter.sp:LS_CORE
- Contents: 6 transistor(s) directly; ports IN, INB, OUT, VDDH, VSS
- Testbench checks: nothing (no testbench)
- Functional simulation: not run
- Layout: not generated

**LS_UP** - kind `level_shifter`, source: reference level_shifter.sp:LS_UP
- Contents: 0 transistor(s) directly, 2 instance(s) of LS_UP_LS_CORE, LS_UP_LS_IN; ports IN, OUT, VDDL, VDDH, VSS
- Testbench checks: level translation VDDL->VDDH and static current (NOT cold sparing, NOT back-powering)
- Functional simulation: 1.4->3.3V pass, 1.4->5.5V pass, 1.8->3.3V pass, 1.8->5.5V pass, 3.3->3.3V pass, 3.3->5.5V pass (generic models)
- Layout: not generated
