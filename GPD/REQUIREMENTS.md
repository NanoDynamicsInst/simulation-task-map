# REQUIREMENTS — scope, conventions, verification targets
*Seed artifact - the GPD "Formulate" output to confirm/extend on ingest - framing-neutral*

## Conventions to lock (GPD locks notation across fields)
Relevant fields: statistical mechanics (thermal noise), continuum mechanics & elasticity (beams, modes),
electrostatics & electrochemistry (actuation, dielectric, Faradaic), device physics (FET sensing, logic
primitive), probability/statistics (assembly yield), and condensed-matter (anchoring, contacts).

- **Units:** SI throughout. Report nanoscale forces in pN, energies in eV and in units of kBT
  (**kBT = 4.142 pN.nm at 300 K**), stiffness in N/m.
- **State temperature (default 300 K) and operating medium (aqueous buffer / vacuum) explicitly in every
  phase** -- noise, damping, actuation, and sensing are all medium-dependent.
- **Define geometry/sign conventions before deriving:** the Class-3 lever (fulcrum-effort-load); coordinate
  origin; mode shapes.

## Verification targets (apply GPD Verify to every phase)
- **Dimensional consistency** (e.g. eV/nm must reduce to a force; an energy/op must reduce to joules).
- **Limiting cases:** free vs clamped beam; over- vs under-damped loop; dilute vs high ionic strength.
- **Symmetry / conservation:** equipartition (sigma^2 = kBT/k), fluctuation-dissipation, energy & charge
  conservation, Landauer bound for the logic primitive.
- **Numerical stability / convergence:** mesh, timestep, sampling, statistical power.
- **Literature cross-checks** against the cited values in `../knowledge/`.

## Acceptance (trace to the matrix)
Each phase's success criterion is the **acceptance predicate of its leaf** (IDs in `ROADMAP.md`; full text
in `../knowledge/vv_matrix_feynman_path.xlsx`). A phase passes when the derivation + numerical check meet
that predicate AND clear the verification targets above.
