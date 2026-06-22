# PROJECT — Load-bearing physics for an electrically-controlled molecular manipulator
*Seed artifact - NDI-authored - GPD-convention-aligned - open Feynman-Path scope*

## Research question
Derive and verify, computationally, the physics that gates a **productive-nanosystem platform** -- an
electrically-controlled, closed-loop molecular manipulator built from DNA origami (Gen-1) and stiffened
with designed proteins (Gen-2/3) -- and the molecular logic device (8-bit adder) needed to meet the
(reframed, material-agnostic) Feynman Grand Prize. Settle the make-or-break questions on paper before
they are committed to the bench.

## Why GPD
These are analytical + numerical physics problems -- Langevin dynamics and thermal-noise floors, beam
mechanics and structural modes, electrostatic actuation and FET charge sensing, device-physics of a
molecular logic primitive, assembly-yield statistics, and the fluid->vacuum environmental transition --
each with clear verification targets. GPD's Formulate -> Plan -> Execute -> Verify loop is the harness.

## Scope
**IN:** the machine-verifiable physics (proof + simulation) for the manipulator arm, the molecular adder,
yield/metrology/control, and the generational platform (Gen-1/2/3) -- organized as the phases in
`ROADMAP.md`.
**OUT (referenced, not executed here):** bench / wet-lab tasks (origami folding, actuation demos,
closed-loop placement, adder fabrication, vacuum-substrate bootstrap). See `../knowledge/program_tasks_feynman_path.csv` (`track = BENCH`).

## The load-bearing questions (each maps to one or more phases)
1. What effective stiffness does a given positioning precision require against thermal noise, and can a
   closed loop reach it (feedback-cooling / dwell-averaging)?  [A1.x]
2. Can an electrostatically-gated DNA-origami lever deliver a sufficient (stroke is a soft target -- ~10 nm aspirational, ~3 nm acceptable if repeatable/closed-loop-corrected; joint compliance, not lever length, dominates noise) stroke and force below dielectric
   breakdown, at >= 1 kHz, at a low-ionic-strength operating point (spermidine Mg2+-free / low-Mg + CPD crosslink) that does not screen the drive field?  [A2.x]
3. Can FET charge-displacement sensing resolve the required displacement at the required bandwidth -- and is there a single ionic-strength window where actuation and sensing BOTH work (coupled Poisson-Boltzmann)?  [A7.x, A7.4]
4. Does a positionally-assemblable molecular logic primitive yield a correct, low-energy 8-bit adder in a
   50 nm cube?  [B1-B6]
5. What per-step yield delivers >= 32 spec-conforming devices, and does staged self-assembly reach it?  [C1-C2]
6. Sub-nm route: rather than stiffening a protein arm, can ~2-3 nm protein-component assemblers position stiff inorganic members (CNTs, piezoelectric nanowires) via crosslinked protein joints, until inorganic joints are mechanosynthesizable?  [J3.1, I1.2, I3.x]

## Source corpus
`../knowledge/`: the reframed prize, the capability-axes + characterization framework, the verifiable-task
schema, and the Feynman-Path V&V data (`vv_matrix_feynman_path.xlsx`, `program_tasks_feynman_path.csv`).

## Status
**TRL 1-3. Nothing executed.** "PASS" = model-consistency, not empirical. Begin with the arm noise-floor
and stiffness phases (they gate everything downstream).
