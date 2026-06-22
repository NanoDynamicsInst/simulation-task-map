# GPD ingestion guide — Open Feynman-Path repo

GPD: `github.com/psi-oss/get-physics-done` (Physical Superintelligence PBC, Apache-2.0).
Four-stage workflow: **Formulate -> Plan -> Execute -> Verify.**

## How to ingest (pick one)
1. **Map this folder (recommended):** from a runtime with GPD installed, run `map-research` in the repo
   root. GPD reads the `GPD/` seed artifacts + `knowledge/` and canonicalizes project state.
2. **New project + import:** run `new-project`, point GPD at `knowledge/`, `digest-knowledge` the cited
   literature (DOIs where present in the docs), and reconcile against `GPD/ROADMAP.md`.

Then:
```
gpd validate consistency
gpd validate project-contract -
# per phase:
discuss-phase N -> plan-phase N -> execute-phase N -> verify-work N
```

## Mapping
NDI segments/capabilities -> GPD **Milestones/Phases**; machine-verifiable leaves (IDs like `A1.1`,
`B1.1`, `J3.1`) -> GPD **Plans/Tasks**. Leaf IDs are carried in `ROADMAP.md` so GPD outputs trace back
to `knowledge/vv_matrix_feynman_path.xlsx`.

## Scope
GPD executes the **machine-verifiable physics** (proof + simulation; `track = MACHINE` in the task CSV).
The **bench (`track = BENCH`) tasks are out of GPD's scope** — they are the experiments GPD's results
inform and design, not execute.

## Caveats
- The `GPD/` files are NDI-authored seeds aligned to GPD's conventions; let GPD's validators canonicalize.
- TRL 1-3; "PASS" = model-consistency, not empirical proof.
- Lock conventions per `REQUIREMENTS.md` (units, medium, sign choices).
- Preserve uncertainty; do not fabricate results.

If GPD contributes to published results, cite per its `CITATION.cff` and this repo's `CITATION.cff`.
