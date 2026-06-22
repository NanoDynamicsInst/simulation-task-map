# Methodology — verifiable-task decomposition (Formulate → Plan → Execute → Verify)

This repository's task data is organized as a set of **machine-verifiable obligations**:
each leaf carries a goal, an acceptance predicate, and a named verifier, and is reasoned
about with a four-stage loop — **Formulate → Plan → Execute → Verify**.

## What "verifiable" means here
A task is admissible only when an automated or instrumental procedure can return pass/fail
against a numeric criterion. Three verifier classes:
- **In-silico** — analytic derivation or simulation (e.g. statistical mechanics, beam/peel
  mechanics, electrostatics, ROC statistics).
- **Instrumental** — a metrology measurement against a stated tolerance.
- **Logical** — exhaustive enumeration or a continuity/duty check.

## Verification targets applied to every result
- **Dimensional consistency** (e.g. an energy-per-length must reduce to a force).
- **Limiting cases** (free vs clamped; dilute vs concentrated; over- vs under-damped).
- **Symmetry / conservation** (equipartition σ² = kBT/k, fluctuation–dissipation, energy & charge conservation).
- **Numerical stability / convergence** (mesh, timestep, sampling).
- **Literature cross-check** against cited, published values.

## Conventions
SI units throughout. Nanoscale forces in pN, energies in eV and in units of kBT
(**kBT = 4.142 pN·nm at 300 K**), stiffness in N/m. State temperature and operating medium
explicitly for every task — adhesion, damping, and electrostatics are all medium-dependent.

## Honest status
The obligations here are **model-consistency targets, not empirical results** (early-stage,
TRL 1–3): the underlying science pieces are demonstrated in the cited literature, but the
integrated system is not built. "PASS" means the model is internally consistent and traced,
not that anything has been measured. Uncertainty is preserved, not hidden.
