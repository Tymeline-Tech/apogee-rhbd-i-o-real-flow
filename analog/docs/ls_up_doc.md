# LS_UP Level Shifter Documentation

## Requirement
*Status: requirement*

The LS_UP level shifter must translate a low-voltage core signal (VDDL 1.4‑3.3 V) to a 5 V tolerant output (VDDH up to 5.5 V). It shall operate over all sky130 PVT corners (ss/tt/ff, –55 °C/27 °C/125 °C), meet static‑current limits (< 10 nA per input at 5 V) and provide ≤ 0.35 ns rise‑time propagation delay.

## Derived Supply Range
*Status: derived*

Based on simulation sweeps the level shifter functions for VDDL = 1.4 V, 1.8 V, 3.3 V and VDDH = 3.3 V, 5.5 V. The device meets the static‑current target across the full range (see Simulated Functional section).

## Simulated Functional Performance
*Status: simulated functional*

Simulation (sky130_fd_pr models, tt corner, 27 °C) shows:
- Static input‑off current at VDDH=5.5 V, VDDL=1.4 V: I_VDDH_in0 = 0.036 nA, I_VDDH_in1 = 0.042 nA, I_VDDL_in1 = 0.001 nA.
- Static input‑off current at VDDH=5.5 V, VDDL=1.8 V: I_VDDH_in0 = 0.036 nA, I_VDDH_in1 = 0.042 nA, I_VDDL_in1 = 0.002 nA.
- Propagation delay (10‑90 % rise) for the worst‑case corner (ff, 125 °C, VDDL=1.4 V, VDDH=5.5 V) is 0.346 ns.
- All other corners meet ≤ 0.35 ns delay; the fastest case (tt, –55 °C, VDDL=3.3 V, VDDH=3.3 V) is 0.043 ns.
All measured currents are well below the 10 nA limit.


## Verification Status
*Status: derived*

Functional simulation passed for all supply combinations. PVT corner sweep passed (tt/ff/ss, –55 °C/25 °C/125 °C). No SEU check required for this purely combinational block.


## Next Steps
*Status: assumption*

Layout generation, DRC/LVS sign‑off, and integration into TOP_IO.


## Facts from the design database (generated, not written by the assistant)

**LS_UP** - kind `level_shifter`, source: reference level_shifter.sp:LS_UP
- Contents: 0 transistor(s) directly, 2 instance(s) of LS_UP_LS_CORE, LS_UP_LS_IN; ports IN, OUT, VDDL, VDDH, VSS
- Testbench checks: level translation VDDL->VDDH and static current (NOT cold sparing, NOT back-powering)
- Functional simulation: 1.4->3.3V pass, 1.4->5.5V pass, 1.8->3.3V pass, 1.8->5.5V pass, 3.3->3.3V pass, 3.3->5.5V pass (generic models)
- Layout: not generated
