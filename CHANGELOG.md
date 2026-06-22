# Changelog

## RC2.1 — 2026-06 (actuator/joint reframing)
- **Stroke target relaxed.** ~10 nm is aspirational, not required; >=~3 nm acceptable if solidly
  repeatable or closed-loop-corrected. Higher stroke only lowers required lever amplification. (A2.1,
  A2.2, A7.4, ROADMAP Phase 2.)
- **Dominant noise term named.** Positioning noise is set by JOINT COMPLIANCE, not lever length; budget
  stiffness at the joints. (A8.2, ROADMAP Phases 2 & 4.)
- **Joint material is an open design variable.** Leading candidate: engineered proteins used as the
  linkages between inorganic members. (J3.1, I1.2, ROADMAP Phase 12.)

## RC2 — 2026-06 (adversarial-review fixes folded in)
Five independent adversarial reviews (engineering, physics, biophysics, control theory, semiconductor)
were run against RC1. The concrete, technically-actionable fixes are folded into the V&V data and seed
artifacts:

- **Actuator/sensor screening conflict (top cross-cutting finding).** Added leaf **A7.4** — a coupled
  Poisson-Boltzmann proof that one ionic-strength window meets actuator stroke AND FET SNR simultaneously.
  Pinned the **operating point** to low-ionic-strength: spermidine Mg2+-free folding (<1 mM; stable under
  high field pulses) or ~2-3 mM Mg2+ with UV thymine-dimer (CPD) covalent crosslinking. Updated A2.1/A2.2/
  A7.1/A7.2 acceptance to evaluate at this point.
- **Precision-vs-rate.** A1.4 now requires a joint (precision, rate) Pareto budget against the >=1000
  motions/s floor, not precision alone.
- **Adder reliability floor.** B2.1/B2.3 corrected: the switching-barrier target is ~15-30 kBT (bit-error
  rate over a full add), not the kBT.ln2 erasure/Landauer floor; operating temperature (room-T vs cryo)
  must be stated.
- **Sub-nm route pivot.** J3.1/I1.2 reframed: pursue sub-nm by using ~2-3 nm protein-component assemblers
  (crosslinked engineered protein joints) to position stiff inorganic members (CNTs, piezoelectric
  nanowires), not by stiffening a protein arm to k~0.41 N/m.
- **Stroke-figure reconciliation.** J1.2: ~100 nm = Class-3 lever-amplified coarse stroke; ~5-10 nm = fine
  working stroke; ~20 nm = closed-loop working volume.
- **Broken dependency edge fixed.** J1.2 `Depends on` D1 -> D1.1.

Supporting literature for the low-ionic-strength + crosslink operating point is being ingested into NDI's
knowledge base (spermidine Mg2+-free folding; site-selective UV/CPD crosslinking to cation-free water).

## RC1 — initial open Feynman-Path GPD release.
