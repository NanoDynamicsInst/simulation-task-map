# AGENTS.md — Open Feynman-Path GPD repo
*Entry point for any agent reading, summarizing, or building from this repository. Self-contained.*

## 0. What this is
An open-science GPD project for the **Feynman-Path pursuit** (molecular-manipulator / mechanosynthesis
toward atomically precise construction). All content here is **open** (public Feynman-path science and
plans). There is no proprietary, commercial, or application-specific material in this repository.

## 1. Invariants — do not distort
- **Maturity:** TRL 1-3. The integrated system is not built. "verify PASS" = model-consistency, not empirical.
- **Material-agnostic.** Reward verified positional construction of a specified object across any chemistry;
  do not reintroduce a diamondoid-only framing. Single-site catalysis is one allowed generality route.
- **The reframed prize (`knowledge/feynman-prize-reframed.pdf`) is a PROPOSAL for discussion**, not an
  official Foresight/XPRIZE rule. Always label it as such.
- **Authoritative task/obligation data:** `knowledge/program_tasks_feynman_path.csv` and
  `knowledge/vv_matrix_feynman_path.xlsx`. Cite leaf IDs (e.g. `A1.1`, `J3.1`), not prose paraphrases.
- If a claim is not traceable to a file here, say so rather than inventing it.

## 2. The GPD lens
GPD workflow = **Formulate -> Plan -> Execute -> Verify.** Each physics phase (`GPD/ROADMAP.md`) is a
derive+simulate+verify unit whose success criterion is its leaf acceptance predicate
(`vv_matrix_feynman_path.xlsx`) plus the verification targets in `GPD/REQUIREMENTS.md`
(dimensional consistency, limiting cases, symmetry/conservation, numerical stability, literature
cross-check). State temperature and operating medium in every phase. kBT = 4.142 pN.nm at 300 K.

## 3. Guardrails
- Cite the source file (and leaf ID) for every nontrivial claim. Preserve caveats and uncertainty.
- Do not overstate readiness or present "PASS" as empirical.
- Contributions are accepted under the repository license (Apache-2.0); see CONTRIBUTING expectations
  in `GPD-INGEST.md`.
