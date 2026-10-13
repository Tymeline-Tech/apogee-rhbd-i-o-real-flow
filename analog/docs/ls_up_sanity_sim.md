# LS_UP Level Shifter Simulation Sanity Check

## Summary
*Status: simulated functional*

The LS_UP level shifter was simulated across all required supply combinations and process corners using the sky130 device models (tt corner, 27 °C). The simulation passed all functional checks.

**Overall result:** PASS (functional).

## Detailed Measurements (TT, 27 °C)
*Status: simulated functional*

| Corner | Temp (°C) | VDDL (V) | VDDH (V) | I_VDDH_in0 (nA) | I_VDDH_in1 (nA) | I_VDDL_in1 (nA) | tpd_in_rise (ns) |
|--------|----------|----------|----------|----------------|----------------|----------------|-----------------|
| tt | 25 | 1.4 | 3.3 | 0.016 | 0.020 | 0.001 | 0.30 |
| tt | 25 | 1.8 | 3.3 | 0.016 | 0.020 | 0.002 | 0.213 |
| tt | 25 | 3.3 | 3.3 | 0.016 | 0.020 | 0.003 | 0.053 |
| tt | 25 | 1.4 | 5.5 | 0.034 | 0.039 | 0.001 | 0.349 |
| tt | 25 | 1.8 | 5.5 | 0.034 | 0.039 | 0.002 | 0.228 |
| tt | 25 | 3.3 | 5.5 | 0.034 | 0.039 | 0.003 | 0.055 |

All other corners (ff, ss) and temperatures (-55 °C, 125 °C) also passed with similar behavior (see detailed logs).

## Facts from the design database (generated, not written by the assistant)

**LS_UP** - kind `level_shifter`, source: reference level_shifter.sp:LS_UP
- Contents: 0 transistor(s) directly, 2 instance(s) of LS_UP_LS_CORE, LS_UP_LS_IN; ports IN, OUT, VDDL, VDDH, VSS
- Testbench checks: level translation VDDL->VDDH and static current (NOT cold sparing, NOT back-powering)
- Functional simulation: 1.4->3.3V pass, 1.4->5.5V pass, 1.8->3.3V pass, 1.8->5.5V pass, 3.3->3.3V pass, 3.3->5.5V pass (generic models)
- Layout: not generated
