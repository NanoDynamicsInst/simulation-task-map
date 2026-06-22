# ROADMAP — milestones, phases, plans
*Seed artifact - phase = a derive + simulate + verify unit - IDs in [brackets] are V&V leaves (see `../knowledge/vv_matrix_feynman_path.xlsx`)*

Hierarchy: Milestone -> Phase -> Plan (leaf) -> Task. Waves = execution order within a milestone
(same wave runs in parallel).

## Milestone M1 — Manipulator-arm physics
- **Phase 1 — Stiffness vs thermal-noise floor** [A1.1, A1.2, A1.4]. Required effective stiffness for a
  target positioning sigma (equipartition); simulate as-designed lever variance; prove whether a closed
  loop (feedback-cooling / dwell-averaging) reaches sub-nm effective placement, else flag stiffening
  required. **Jointly budget the averaging window against the >=1000 motions/s rate (Phase 2 bandwidth) and report the (precision, rate) Pareto point.** *Verify:* sigma = sqrt(kBT/k), fluctuation-dissipation, damped-oscillator limits. **Wave 1.**
- **Phase 2 — Electrostatic actuation** [A2.1, A2.2, A2.5]. Stroke & blocking force vs gate voltage for a
  high-k-gated DNA-origami lever; field-driven deflection incl. ionic screening; dielectric field below
  breakdown over duty cycle. Targets: stroke aspirational ~10 nm (>=~3 nm acceptable if repeatable or closed-loop-corrected; higher stroke only lowers required amplification, and JOINT COMPLIANCE -- not lever length -- is the dominant positioning-noise term), force >= 100 pN, bandwidth >= 1 kHz. **Operating point: low-ionic-strength (spermidine Mg2+-free folding <1 mM, stable under high field pulses, or ~2-3 mM Mg2+ with UV thymine-dimer/CPD covalent crosslinking) so the drive field is not screened.** *Verify:*
  dimensions, screening-length limit, breakdown margin. **Wave 1.**
- **Phase 3 — FET displacement sensing & the screening window** [A7.1, A7.2, A7.4]. Information-theoretic SNR bound for charge-
  displacement sensing vs bandwidth; device simulation of FET sensitivity vs distance/screening.
  Add the **coupled actuation-vs-sensing operating-window proof (A7.4)**: one Poisson-Boltzmann calculation showing an ionic-strength window (spermidine Mg2+-free or low-Mg + CPD crosslink) that meets actuator stroke >=10 nm AND FET SNR>=10 at >=1 kHz simultaneously. *Verify:* SNR limits, Debye-length/attenuation vs Mg2+, dimensional consistency. **Wave 1 — the closed-loop's critical element; resolves the actuator-needs-ions vs sensor-needs-low-screening conflict.**
- **Phase 4 — Mechanism & structure** [A3.1, A3.2, A8.1, A8.2]. DOF/mobility for a parallel (delta-type)
  manipulator; workspace & singularity map; <=100 nm envelope; structural-mode/rigidity consistency with
  Phase 1; identify the DOMINANT compliance term (joint compliance, not lever length) and budget stiffness at the joints. *Verify:* mobility count, mode stiffness, envelope. **Wave 2 (after 1).**

## Milestone M2 — Molecular adder physics
- **Phase 5 — Logic equivalence & device behaviour** [B1.1, B1.2, B6.1]. Formal equivalence of the adder
  netlist to a reference 8-bit adder; device-level simulation reproduces the truth table with noise
  margin; down-select a positionally-assemblable primitive. *Verify:* exhaustive/symbolic equivalence,
  state separation > margin. **Wave 1.**
- **Phase 6 — Primitive physics & energy** [B2.1, B2.3, B5.1]. Bistability & switching energy; bit-error-
  rate vs energy/temperature (noise-limited); energy/heat per addition. **Reliability floor = ~15-30 kBT switching barrier for a correct 8-bit add (NOT the kBT.ln2 erasure/Landauer floor); state the operating temperature this implies (room-T vs cryogenic).** *Verify:* BER bound, barrier-vs-temperature margin. **Wave 1.**
- **Phase 7 — Area & coupling** [B3.1, B3.2, B4.1]. Place-and-route within a 50 nm cube; adjacent-device
  crosstalk; I/O scheme. *Verify:* area closure, coupling < margin. **Wave 2.**

## Milestone M3 — Yield, metrology & control
- **Phase 8 — Yield budget & assembly** [C1.1, C2.1]. Max tolerable per-step defect rate for >= 32 good
  devices; staged self-assembly yield. *Verify:* statistical consistency. **Wave 1.**
- **Phase 9 — Metrology adequacy & acceptance harness** [D1.1, D3.1]. Tool resolution < tolerance per
  measured quantity; automated instrument-output -> assertion harness. *Verify:* resolution vs tolerance.
  **Wave 1.**
- **Phase 10 — Control & addressing** [E3.1, E4.1]. Real-time loop latency/stability budget; array-
  addressing scalability (wiring vs N). *Verify:* phase margin, wiring/crosstalk budget. **Wave 2.**

## Milestone M4 — Generations & environmental transition
- **Phase 11 — Gen-1/Gen-2 models** [J1.1, J2.1]. Gen-1 voltage-controlled-spring stack model
  (force-displacement, thermal spectrum, closed-loop precision); Gen-2 protein-stiffened NEMS model.
  *Verify:* equipartition, stiffness consistency. **Wave 1.**
- **Phase 12 — Sub-nm via protein-assembled inorganic members** [J3.1]. Pursue sub-nm NOT by stiffening a protein arm to k ~ 0.41 N/m
  for sub-nm (0.1 nm) placement; use ~2-3 nm protein-component assemblers (crosslinked, engineered protein joints) to POSITION stiff inorganic members (CNTs, piezoelectric nanowires); protein joints persist until mechanosynthesis-competent inorganic joints exist. Quantify required-vs-achievable for the assembler + inorganic-member stiffness, not the bare protein. Joint material is an open design variable (leading candidate: engineered proteins as the linkages between inorganic members). *Verify:* sigma = sqrt(kBT/k) for the composite member. **Wave 2.**
- **Phase 13 — Fluid -> vacuum transition** [I3.1, I3.2]. Define the explicit fluid->vacuum transition
  (stabilize -> salt-free rinse -> critical-point/freeze dry -> pump-down); quantify the vacuum payoff for
  in-line electrical test and dry van-der-Waals adhesion. *Verify:* Debye-length limit, dry-vs-wet
  adhesion scaling. **Wave 2.**

**Suggested start:** Phases 1, 2, 3, 5, 6, 8, 9, 11 have no unmet dependencies (Wave 1). Phase 1 (stiffness
vs thermal noise) and Phase 3 (FET sensing) gate the closed-loop arm; Phase 12 decides the sub-nm route.
