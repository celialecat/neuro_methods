# Part VII — Evaluation Benchmarks: Separating Prediction from Mechanism Recovery

The framework (Part VI) is only useful if its dimensions can be *measured*. The natural test-beds
are **systems whose ground-truth mechanism is fully known** — exactly the Jonas–Kording/Lazebnik
move: apply a method to a system we built, then check whether the method recovers the mechanism we
*know* is there. This Part designs a **benchmark suite** in which the ground truth is available, so
that `F` (faithfulness), `HC` (hierarchy), `MO` (modularity), and `CC` (causal completeness) can be
scored against truth, and `P/CF/IV/T/R` can be scored against an oracle.

---

## 1. Design principles for an "understanding benchmark"

A benchmark *separates prediction from understanding* iff it satisfies:

1. **Known ground-truth mechanism.** The system's parts, dynamics, causal graph, and hierarchy are
   known by construction, so recovered structure can be scored against truth (`F, CC, HC, MO`).
2. **A rich, well-defined intervention algebra.** One can perform clean, surgical interventions
   (set a variable, ablate a part, swap a sub-mechanism) to evaluate `CF, IV` against the true
   post-intervention behavior — the dimension passive data cannot reach (T1).
3. **An OOD / novel-regime test set** disjoint from any plausible "training distribution," to defeat
   the clever predictor (T2): the benchmark must include behaviors the predictor could not have
   fit.
4. **A predictor baseline that achieves high `P` with low `F`.** Crucially, the benchmark must
   *include* a strong black-box predictor (overfit net / lookup table / fitted surrogate) so we can
   **demonstrate the gap** `G = KA − UO` — a method that "wins on prediction" should be shown to
   *lose on mechanism*. *A benchmark without this control cannot establish the distinction.*
5. **A family of related systems** (parameter variants, isomorphic re-implementations) for `T`
   (transfer) and to test multiple-realizability handling.
6. **A graded difficulty axis along decomposability** — from cleanly modular to genuinely integrated
   (high synergy/Φ) — so we can map *where* methods break (Part V's profile).
7. **Faithfulness scored causally, not by plausibility.** Recovered "explanations" are validated by
   interchange interventions / ablations against ground truth, never by human convincingness
   (Jacovi–Goldberg; Adebayo).

---

## 2. The candidate benchmark systems (with what each uniquely tests)

### 2.1 The radio (and analog circuits) — *repair as the criterion*
- **Why.** Lazebnik's system. Known schematic (amplifier/oscillator/filter stages); clean
  interventions (change R/C/L, cut a trace); a clear **repair** task (inject a fault, require
  diagnosis + fix).
- **Tests.** `F` (recover stage decomposition), `MO` (stage interfaces), `C3` repair (first-try,
  minimal), `CF` (predict effect of component changes), `Δ` (range of invariance of stage models).
- **Predictor control.** Fit an input→output transfer function (great `P`), show it cannot localize
  or repair a fault (low `F`, fails C3) — the gap, demonstrated.

### 2.2 The microprocessor (e.g., MOS 6502) — *reverse-engineering at scale*
- **Why.** Jonas & Kording's system; full netlist known; rich behavior (runs real programs:
  Donkey Kong, Pitfall). Clean interventions (lesion a transistor, force a wire). The canonical
  test that *neuroscience-style analyses fail* (tuning curves, lesions, dimensionality reduction,
  connectomics, Granger causality) to recover the known architecture.
- **Tests.** Whole-stack: `F` (recover ALU/registers/decoder/clocking), `HC` (transistor→gate→
  module→ISA levels with commuting maps), `MO`, `CC`, `IV`. **The definitive multi-level
  reverse-engineering benchmark.**
- **Predictor control.** A model predicting transistor on/off states from neighbors (high `P`,
  near-zero architectural `F`) — Jonas–Kording's actual finding, re-cast as `G` large.

### 2.3 Conway's Game of Life & elementary cellular automata — *emergence & weak-emergence*
- **Why.** Rule fully known; exhibits **weak emergence** (gliders, guns, universality) where the
  inter-level map is non-analytic (must simulate). ECAs (Wolfram classes; Rule 110 universal) give a
  difficulty gradient and ε-machine ground truth (computational mechanics).
- **Tests.** `HC`/`C16` (recover the *glider*-level closed description and the *why* it is
  autonomous), `C6` (derive macro patterns from the rule), the **integration index** (where no
  closed macro level exists), and ε-machine recovery (`F` at the predictive level).
- **Predictor control.** A next-state CNN predictor (perfect `P` by construction) that has *no*
  glider-level concepts (low `HC`) — prediction without higher-level understanding.

### 2.4 Logic circuits & finite-state machines — *exact mechanism, exact scoring*
- **Why.** Boolean circuits / FSMs with known gates and state graphs; exact, small, fully
  interpretable; clean interventions (force a gate). Includes the **modular-arithmetic** task that
  trained transformers solve (Nanda et al.) — bridging to interpretability.
- **Tests.** `F`, `CC`, `MO`, `CF` with *exact* ground truth; the cleanest place to validate the
  `F`/`CC` estimators themselves.

### 2.5 Artificial neural networks & small transformers — *the interpretability target*
- **Why.** We *train* them, so we know training data/objective but **not** the learned mechanism —
  the realistic case. Subcases with *known* intended algorithm: modular addition (Fourier
  algorithm), IOI (GPT-2 circuit), induction heads, toy superposition models (known feature
  geometry by construction).
- **Tests.** Recover the algorithm (`F` via interchange interventions / DAS), `MO` (circuit
  modularity), superposition handling (does the method find the *known* feature directions, not
  neurons?), `T` across seeds/sizes (universality). **The benchmark that most directly grades
  mechanistic-interpretability methods** (SAEs, patching, probes) against the framework.
- **Predictor control.** A linear probe with high decoding accuracy but whose probed direction,
  when ablated, doesn't change behavior (high `P`/decodability, `F≈0`) — the probing-vs-patching gap.

### 2.6 Gene-regulatory networks & toy biological networks — *biology's decomposability gradient*
- **Why.** Synthetic GRNs / Boolean networks / reaction networks with known topology and dynamics;
  realistic features (feedback, redundancy/degeneracy, robustness, noise). Tunable from modular
  (operon-like) to integrated.
- **Tests.** `MO`/`C13` (recover regulatory modules), `R`/`C15` (explain robustness/perfect
  adaptation via integral feedback), `C7` (infer micro-rules from macro phenotype — the hard
  inverse), knockout `CF`. Mirrors Lazebnik's actual domain (cell biology).

### 2.7 Simple physical simulations (n-body, oscillator lattices, fluids, Ising) — *scale separation & RG*
- **Why.** Known micro-laws; genuine **scale separation** and **universality** (Ising/RG); known
  relevant variables (order parameters).
- **Tests.** `HC`/`C6` (derive macro/thermodynamic behavior; recover order parameters as the closed
  level), max-EI level selection (causal emergence), `Δ` (range of invariance), `C16` (explain phase
  transitions/emergence).

### 2.8 Synthetic causal graphs / SCMs — *the pure causal-discovery benchmark*
- **Why.** Ground-truth DAG + structural equations by construction; the cleanest test of recovering
  **causal variables and structure** under interventions vs. observations only.
- **Tests.** `C8` (identify causal variables), `F`/`CC` (recover the graph + mechanisms), and a
  *direct demonstration of T1*: show that observational data caps recovery and that **adding
  interventions/multiple environments** is what raises `F`/`CF` — the framework's core claim,
  empirically exhibited. Also the natural home for **causal-abstraction** scoring (`HC`).

### 2.9 (Bridge) Reverse-engineering an evolved/learned artifact — *build-without-understanding*
- **Why.** An evolved FPGA (Thompson) or a network trained to a function: the system *works*, the
  "designer" (evolution/SGD) did *not* understand it. Directly tests `C4`'s caveat and the
  achievement-5 boundary.

---

## 3. The benchmark protocol (how a method is scored)

For a method **m** applied to system **S** at level **L**:

1. **Build the ground truth** `(parts, activities, causal graph, hierarchy, intervention oracle)`
   from S's known construction.
2. **Run m** to produce a model `M_m` (its recovered structure + a prediction/inference procedure).
3. **Score object dimensions against truth:**
   - `F` = interchange-intervention / ablation agreement between `M_m` and S's true parts.
   - `CC` = 1 − interventional variance unexplained by `M_m`.
   - `HC` = fraction of true levels recovered with commuting maps (+ correct integration reporting).
   - `MO` = recovered-vs-true module agreement, interface sparsity, intervention-locality.
   - `K` = description length of `M_m` in the parts-vocabulary vs. behavior enumeration.
4. **Score competence dimensions against the oracle:**
   - `P(OOD)` on the held-out novel-regime set; `CF` and `IV` against the intervention oracle;
     `T` on the related-systems family; `R` on injected faults/noise; `X` via a step-by-step
     reconstruction test (and, where relevant, a human/agent who must answer counterfactuals using
     only `M_m`).
5. **Compute `(KA, UO)` and the gap `G`.** Report the **profile vector**, not a single number.
6. **Compare to the predictor control** (Principle 4): confirm the control has high `KA`, low `UO`,
   large `G` — i.e., the benchmark *demonstrably* separates prediction from mechanism.
7. **Sweep the decomposability axis** (2.6/2.3/2.5 variants) to map *where m breaks* (the
   integration index at which `F` collapses).

A method "**produces understanding**" on the benchmark to the degree it achieves high `UO` (not just
`KA`) **and** its `UO` tracks the *true* mechanism (high `F` against ground truth), **across** the
decomposability sweep — and especially where it must use interventions to beat the data ceiling.

## 4. What good results would look like (predictions of the framework)

- **Correlational/representational methods** (saliency, probes, RSA, functional connectivity,
  dimensionality reduction, next-state predictors) will score **high `P/KA`, low `F/UO`, large `G`**,
  and will **fail at the first nontrivial intervention/OOD test** — reproducing Jonas–Kording on the
  microprocessor and Lazebnik on the radio/cell.
- **Interventionist methods** (activation patching, interchange interventions/DAS, causal discovery
  *with* interventions, ablation-validated circuits, ICP across environments) will score **higher
  `F/CF/UO`**, recover true modules where present, and — critically — their advantage will **grow
  with the number/quality of interventions** (T1 made visible) and **shrink as integration rises**
  (Part V).
- **The decomposability sweep** will show a **phase-transition-like collapse of `F`** as synergy/Φ
  crosses a threshold — empirically locating "where mechanistic decomposition stops working," which
  is the quantitative content of Lazebnik's worry.

These are *falsifiable predictions*: if a purely observational/correlational method achieved high
`F` against ground truth on the SCM or microprocessor benchmarks, the framework (and T1/T2) would be
refuted. That falsifiability is the point — the benchmark turns the philosophical thesis into an
empirical claim about methods.

## 5. Relation to existing benchmarks

This suite generalizes and unifies existing efforts: the **microprocessor study** (Jonas & Kording
2017) and **CA/ε-machine** analyses (computational mechanics) are special cases; recent
**mechanistic-interpretability evals** (IOI, modular addition, *Tracr*-compiled transformers with
known ground-truth circuits, RAVEL / causal-abstraction benchmarks, SAE faithfulness suites) are the
2.5 family; **causal-discovery benchmarks** (with/without interventions) are 2.8; **causal-emergence**
toy systems are 2.7. The contribution here is the **common scoring** (`(KA, UO)`, the profile vector,
the predictor control, the decomposability sweep) that lets results be compared *across* domains on
the single question: *does the method recover mechanism, or only predict?*
