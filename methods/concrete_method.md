# A Concrete Method for Understanding a Complex System
### An operational protocol, with worked instantiations for a brain and for a large language model

> **Purpose.** Parts I–IX argue *what* understanding is and *why* it is distinct from prediction. This
> document answers the practical question the framework provokes: **given a real system — a brain, a
> neural network — what do you actually *do*?** It is a step-by-step protocol whose output is not a
> plausible story but a pair of coordinates `(KA, UO)`, a **decomposability profile**, and an explicit
> **ι-machine hypothesis** that has been *tested against intervention*. The protocol is the framework's
> theorems turned into an experimental loop.
>
> It is a *disciplined default*, not a universal algorithm (cf. Feyerabend, Part 0 §0.5): every step is
> defeasible and must be domain-adapted. But the **invariant** is non-negotiable — a claim of
> understanding is licensed only by a model that *commutes with intervention* at a stated level
> (Theorems T1–T3; the modeling relation of Part IX).

---

## 0. The invariant, stated once

A method has produced **understanding of** (not merely **knowledge about**) a system `S` to the extent
that it yields a model `M` such that, for interventions `i` in a declared algebra `𝓘` applied to both
the system and the model, the diagram **commutes**:

```
        do_S(i)
   S  ----------->  S'
   |                |
 enc|              |enc          understanding  ⇔  enc(do_S(i)·s) ≈ do_M(i)·enc(s)
   v                v                              for all i ∈ 𝓘, to tolerance τ, at level ℓ
   M  ----------->  M'
        do_M(i)
```

In words: *the model predicts the effect of interventions you have not merely observed but performed*
(or could perform). Pure prediction asks only that the **top edge** be reproducible from observation;
understanding asks that the **whole square** commute under `do(·)`. Every step below exists to build
`M`, declare `𝓘` and `ℓ`, and *test the square*.

The protocol has **eight phases**. Phases 1–3 set up the problem (level, variables, baseline). Phases
4–6 are the core understanding loop (hypothesize mechanism → intervene → score). Phases 7–8 are
consolidation (decomposability, reporting). It is **iterative**: phase 6 feeds back into phase 4.

---

## Phase 1 — Fix the level and the question (operationalize `ℓ` and the explanandum)

Understanding is level-relative (Part V; T3). Before any data, commit on paper to:

1. **The explanandum.** *What behavior of `S` are we trying to understand?* Not "the brain" / "the
   model" but a specific phenomenon: "how V1 represents oriented edges", "how this transformer performs
   indirect-object identification". A diffuse target guarantees a diffuse verdict.
2. **The candidate level(s) `ℓ`.** Enumerate the description scales you will consider (e.g., for a
   brain: ion channels → neurons → microcircuits → areas → systems; for an LLM: weights → neurons →
   sparse features → attention heads → circuits → modules). You will *report* which level admits a
   closed description; you do **not** assume one (this is the decomposability profile, Phase 7).
3. **Marr's three questions, kept separate.** State, even tentatively, the *computational* (what
   problem is solved, and why), *algorithmic* (what representation/algorithm), and *implementational*
   (what physical substrate) levels. Confusing them is the most common way "understanding" claims
   equivocate.
4. **The success tolerance `τ` and the contrast set.** "Understood" relative to *which* alternatives and
   to *what* error bar? Pre-register them.

> **Anti-pattern caught here:** starting from a method ("let's do RSA / train an SAE") rather than from an
> explanandum and a level. Method-first work reliably lands in the knowledge-about arm.

---

## Phase 2 — Inventory variables and declare the intervention algebra `𝓘`

This is the step that separates this protocol from a data-analysis pipeline.

1. **Variable inventory.** List the candidate mechanistic variables at level `ℓ` (neurons, populations,
   features, heads, edges). These are the *handles* a mechanism could use.
2. **Declare `𝓘` — what you can actually *do*, not just observe.** For each variable, state the
   interventions available, their **granularity**, **specificity** (off-target effects), **temporal
   resolution**, and **reversibility**. This declaration *defines the resolution limit of any
   understanding you can earn* (T3): you cannot distinguish mechanisms that `𝓘` cannot pull apart.
3. **Map your position on Pearl's ladder.** Mark, per variable, whether you have rung-1 (observe), rung-2
   (`do`), or rung-3 (counterfactual / nested) access. **If everything is rung-1, stop and acquire
   intervention capability or accept that you are doing knowledge-about** (T1 forbids ascending past the
   data ceiling by observation alone).

---

## Phase 3 — Build the knowledge-about baseline (and label it as such)

Do the predictive/representational work — *and book it on the `KA` axis, not the `UO` axis*.

1. Fit the best **predictive/encoding/decoding** model you can; record predictive power **on held-out
   and, critically, out-of-distribution** data (`P`). OOD is where memorization and mechanism diverge.
2. Compute **descriptive** structure: dimensionality, representational geometry (RSA), graph/network
   statistics, feature dictionaries. Record a **compression** figure (`C_μ`-like: the size of the
   minimal *predictive* summary).
3. **Explicitly tag** every artifact with its epistemic object (regularity / representation /
   correlation). This baseline is indispensable — it generates hypotheses and substrates — **but it is
   not yet understanding**, and saying so out loud is part of the method (it is the discipline the
   Jonas–Kording/Lazebnik results demand).

---

## Phase 4 — Hypothesize a mechanism (a candidate ι-machine)

Turn clues into a **causal-mechanistic hypothesis**: a set of entities + activities + organization
(Machamer–Darden–Craver) at level `ℓ` that would *produce* the explanandum.

1. State it as a **causal model** (a structural causal model / wiring diagram / circuit): variables,
   directed dependencies, and the computation each node performs.
2. The hypothesis must be **generative and minimal**: it should re-derive the Phase-3 regularities, and
   you should prefer the smallest such model (the ι-machine is the *minimal model closed under `𝓘`*; its
   size is `C_ι`).
3. Make it **falsifiable by intervention**: for each edge/node, write down *the intervention that would
   break it and the predicted effect*. A hypothesis with no such predictions is a story, not a mechanism.

---

## Phase 5 — Intervene (the heart of the method)

Execute the interventions declared in Phase 2 to test the Phase-4 hypothesis. **This is the phase that
manufactures `UO`.** Three intervention classes, in increasing strength:

- **(a) Ablation / knockout.** Remove or silence a variable; does the predicted function fail
  *specifically* (necessity)? Guard against compensation and off-target effects.
- **(b) Activation / sufficiency.** Force a variable to a value; does it *produce* the predicted effect
  in the absence of normal input (sufficiency)? Necessity + sufficiency ≈ Craver's **mutual
  manipulability** — the criterion for a component being a genuine part of the mechanism.
- **(c) Interchange / counterfactual.** Swap a variable's state with the state it would have on a
  *different* input and check the output changes *as the hypothesis predicts*. This is the strongest
  test — it asks the **whole square to commute**, not just an edge to matter — and corresponds to
  rung-3.

For each intervention, record **whether the model's predicted effect matched the system's actual effect**.
The fraction of `𝓘` over which the square commutes (to tolerance `τ`) is your direct estimate of
**faithfulness `F`** and **causal completeness `CC`**.

> **Stopping/iteration rule.** If interventions falsify the hypothesis, return to Phase 4 with the
> *pattern of failures* as data (often the failures localize the missing mechanism). Iterate. The loop
> terminates when the square commutes across `𝓘` at tolerance `τ`, or when you hit the `𝓘`-resolution
> limit (T3) — at which point report the residual indeterminacy rather than papering over it.

---

## Phase 6 — Score the dimensions (compute the `(KA, UO)` coordinates)

Score the model on the Part VI dimensions, separating the two axes. Minimal scorable set:

| Axis | Dimension | Operational measurement |
|---|---|---|
| **KA** | `P` predictive power | held-out + OOD accuracy of the predictive model |
| **KA** | `C_μ` statistical compression | size of minimal predictive summary |
| **UO** | `IV` intervention capability | rung reached in `𝓘`; fraction of variables with `do`-access |
| **UO** | `CF` counterfactual competence | accuracy on interchange/counterfactual interventions |
| **UO** | `F` mechanistic faithfulness | fraction of `𝓘` over which the square commutes at `τ` |
| **UO** | `CC` causal completeness | fraction of the explanandum's variance attributable to identified, intervention-validated mechanism |
| **UO** | `HC` hierarchical consistency | do cross-level claims cohere (Phase 7)? |
| **UO** | `MO` modularity | recovered near-decomposability (Phase 7) |
| **both** | `T` transferability | does the mechanism predict behavior in a *related* system/condition? |
| **UO** | `K`/`C_ι` mechanism description length | size of the intervention-closed minimal model |

**Gating rule (the load-bearing step).** `UO → 0` whenever `F → 0` or `CF → 0`, *regardless of how high
`P` and `C_μ` are*. A model that predicts perfectly (`P=1`) but whose interventions do not commute
(`F≈0`) scores high `KA` and ~zero `UO`. This is Theorem T2 made arithmetic, and it is the entire point:
**you cannot buy `UO` with `KA`.**

The **understanding gap** for this system at this level is `G = C_ι − C_μ` (Box 2 of the paper): the
mechanistic bits that no amount of passive prediction recovers.

---

## Phase 7 — Build the decomposability profile (report hierarchy, don't assume it)

For each candidate level `ℓ` from Phase 1, report **whether a closed, low-dimensional,
intervention-respecting description exists**:

- Does the level admit modules with **sparse, near-decomposable** inter-module interaction (Simon)?
- Do interventions *respect* the proposed module boundaries (intervening inside a module stays inside)?
- Is there a valid **coarse-graining** to the next level up that **commutes with intervention** (a causal
  abstraction in the Geiger/Beckers–Halpern sense)? If yes, the hierarchy is *real*, not imposed.

The output is a table over levels: `{closed? low-dim? intervention-respecting? abstracts upward?}`. This
*replaces* the unargued assumption "the system is hierarchical" with an empirical finding — and is where
the **Genesis Principle** (Part IX §7) makes its falsifiable prediction: *designed* systems should show
clean profiles; *trained/evolved* systems may not.

---

## Phase 8 — Report honestly (the verdict)

The deliverable is **not** "we understand `S`." It is:

1. The `(KA, UO)` coordinates with error bars, at the stated level `ℓ` and tolerance `τ`.
2. The decomposability profile.
3. The **validated ι-machine hypothesis** (or the best current one) *and the interventions that
   validated it*.
4. The **residual indeterminacy** (what `𝓘` could not resolve — T3) and the **gap `G`**.
5. A one-line classification on the epistemic ladder (knowing → predicting → modeling → explaining →
   understanding → reverse-engineering → mechanistic understanding).

If you cannot fill in (3) with intervention-validated content, the honest verdict is *knowledge-about*,
however impressive the prediction.

---

# Worked instantiation A — Understanding a brain (a cortical circuit)

**Explanandum (Phase 1).** Not "vision" but, e.g., *how a local circuit in primary visual cortex (V1)
computes orientation selectivity*, at level `ℓ = ` microcircuit (neurons/populations). Computational
question: estimate local edge orientation (efficient/predictive-coding rationale). Algorithmic:
feedforward filtering + recurrent normalization? Implementational: specific excitatory/inhibitory
populations.

**Variables & `𝓘` (Phase 2).** Variables: identified cell types (excitatory pyramidal, PV/SST/VIP
interneurons), thalamic input, recurrent connections. Intervention algebra:
- **optogenetics** (cell-type-specific activation/silencing; ms resolution; reversible) — rung-2/3,
- **chemogenetics / pharmacology** (slower, population-level),
- **microstimulation** (coarse, spatially imprecise),
- **reversible inactivation** (cooling, muscimol) — rung-2, coarse,
- **lesions** — rung-2, irreversible, low specificity,
- **two-photon holographic stimulation** (single-cell-resolution, patterned) — the current frontier of
  fine-grained `𝓘`.

Declaring `𝓘` honestly sets the resolution: with only lesions, you cannot resolve cell-type-specific
mechanism; with holographic single-cell stimulation, you can. *This is why the protocol treats new
instruments as variety amplifiers (Part IX) — they enlarge `𝓘` and raise the T1 ceiling.*

**Baseline `KA` (Phase 3).** Tuning curves, encoding models (predict spikes from stimuli), RSA across
conditions, population geometry / neural manifold, decoders (predict stimulus from activity),
connectomic graph statistics. *All of this is knowledge-about V1* — the very analyses Jonas–Kording
showed can be maximally successful and still miss mechanism. Booked on the `KA` axis.

**Mechanism hypothesis (Phase 4).** A circuit model: thalamic drive sets initial orientation bias;
recurrent excitation sharpens; SST/PV inhibition implements divisive normalization. Written as a
structural/dynamical model with per-cell-type roles and *predicted intervention effects* (e.g.,
"silencing PV broadens tuning and raises gain"; "activating SST sharpens and lowers gain").

**Intervene (Phase 5).**
- *Ablation/necessity:* optogenetically silence PV → measure tuning width and gain; does it match the
  predicted broadening?
- *Sufficiency:* drive SST in the absence of normal input → does the predicted normalization appear?
- *Interchange/counterfactual:* use holographic stimulation to impose the population state the circuit
  *would have* under a different orientation → does the readout shift as the model predicts?
Each result is logged as commute / not-commute. Biophysical models (Hodgkin–Huxley-grade) and normative
predictive-coding models that *derive* receptive fields live on the **understanding arm** precisely
because they make and survive such interventional predictions.

**Score, profile, report (Phases 6–8).** Compute `(KA, UO)`: encoding-model `P` may be high while `F`
is low until interventions confirm the causal roles. Decomposability profile across
channel→neuron→microcircuit→area asks at which level a closed, intervention-respecting description
exists. Per the **Genesis Principle**, expect the profile to be *messier* than an engineered chip:
the cortex was *optimized by evolution and learning*, not *designed for decomposability*, so module
boundaries may be approximate and degenerate (many circuits realize the same function) — a *prediction*,
not a lament.

> **Rigor note (the user's caution, applied).** Nothing here says "neuroscience = correlation." The
> protocol's `KA` phase uses neuroscience's *correlational* tools; its `UO` phase uses neuroscience's
> *interventional and biophysical/normative* tools (optogenetics, Hodgkin–Huxley, efficient coding).
> Both are neuroscience. The field's mechanistic arm is exactly what carries a circuit across the
> understanding line; the data-intensive arm, alone, does not.

---

# Worked instantiation B — Understanding a large language model (a transformer behavior)

The protocol is *identical in structure* — which is the framework's main empirical claim (Part VIII/§10)
— with the great advantage that an LLM grants **total, cheap, reversible, rung-3 intervention access**
to every internal variable. `𝓘` is essentially unrestricted; the binding constraints are *which
variables to read* and *agent variety* (the model may be human-ungraspable at full resolution — Part IX).

**Explanandum (Phase 1).** A *specific, scorable* behavior, e.g., **indirect-object identification**
("When Mary gave a drink to John, John gave it to ___" → "Mary"), or **modular addition** in a small
trained transformer, or **induction** ("…[A][B]…[A]→[B]"). Level `ℓ`: choose among weights → MLP neurons
→ **sparse features** → attention heads → **circuits** (subgraphs of heads/MLPs) → modules. Marr:
computational = the task; algorithmic = the circuit; implementational = the weights.

**Variables & `𝓘` (Phase 2).** Variables: residual-stream directions, attention heads, MLP neurons, and
— crucially — **sparse-autoencoder (SAE) features** as candidate interpretable units. Intervention
algebra (all rung-2/3, exact, reversible):
- **activation patching / resampling** (replace an activation with its value on another input),
- **ablation** (zero / mean-ablate a head, neuron, feature, or edge),
- **interchange interventions / distributed alignment search (DAS)** (align an abstract variable to a
  subspace and swap it — a *causal-abstraction* test, Geiger et al.),
- **causal scrubbing** (replace activations according to a hypothesized computational graph and check
  behavior is preserved — a direct test that the **square commutes**),
- **path patching / edge interventions** (test specific connections),
- **weight editing** (ROME/MEMIT-style) to test *sufficiency* of a localized mechanism.

**Baseline `KA` (Phase 3).** Train **linear probes** (decode concepts from activations), compute **CAVs**,
**feature-visualization**, **attention maps**, and a **sparse autoencoder** scored by
reconstruction/sparsity. Measure next-token `P`. *Every one of these is knowledge-about the model* — a
probe that decodes a concept does **not** show the model *uses* it (decoding ≠ usage; reconstruction ≠
causation). Booked on the `KA` axis. An SAE feature is a **hypothesis** at this stage, not a mechanism.

**Mechanism hypothesis (Phase 4).** A **circuit**: e.g., for IOI (after Wang et al.), "duplicate-token
heads detect the repeated name → S-inhibition heads suppress it → name-mover heads copy the remaining
name to the output." Stated as a computational subgraph with predicted patching effects per edge.

**Intervene (Phase 5).**
- *Necessity:* ablate name-mover heads → does IOI accuracy drop specifically?
- *Sufficiency / localization:* patch the name-mover output from a clean run into a corrupted run → is
  behavior restored?
- *Interchange (rung-3):* patch the "subject" variable with its value from a sentence with names swapped
  → does the model output flip as the circuit predicts (the square commutes)?
- *Causal scrubbing:* replace all activations consistent with the hypothesized graph; if behavior is
  preserved and *only* the hypothesized connections matter, the hypothesis is faithful.
- *SAE feature validation:* a candidate feature graduates from `KA` to `UO` **only** when patching it
  changes behavior in the predicted, specific way.

**Score, profile, report (Phases 6–8).** Compute `(KA, UO)`: a probe-rich, patch-poor analysis sits at
high `KA`, low `UO`; a causal-scrubbing-validated circuit crosses into `UO`. Decomposability profile
across neuron→feature→head→circuit→module reports at which level a closed, intervention-respecting
description exists — directly relevant to **superposition** (features in linear combination), which
*predicts the neuron level will NOT be cleanly decomposable* while the sparse-feature level might be.
The **Genesis Principle** prediction is sharp here: because the network was **trained by SGD, not
designed for modularity**, its mechanistic decomposition need not be clean; interpretability is
biology-like reverse-engineering, not chip-like, and *training-time choices* (sparsity, modularity
pressure) partly determine downstream interpretability.

> **Why the LLM case is the framework's best test.** On an LLM you have *ground-truth-ish* access
> (you can read and set every variable) and, for toy tasks, a *known intended algorithm* — so the
> benchmarks of Part VII can be run end-to-end. If a purely observational/probing method ever recovered
> the verified circuit *without* intervention, Theorem T1 would be refuted. It has not.

---

## Appendix — One-page checklist

```
[ ] 1. Explanandum + level ℓ + Marr triple + tolerance τ pre-registered
[ ] 2. Variable inventory; intervention algebra 𝓘 declared (granularity/specificity/reversibility);
       Pearl rung per variable. If all rung-1 → STOP (knowledge-about only).
[ ] 3. KA baseline built and LABELED as KA (predictive P incl. OOD; descriptive structure; C_μ)
[ ] 4. Mechanism hypothesis = causal model, generative, minimal, with predicted intervention effects
[ ] 5. Interventions executed: ablation (necessity), activation (sufficiency), interchange (rung-3);
       commute / not-commute logged per intervention; iterate to Phase 4 on failure
[ ] 6. Dimensions scored; (KA, UO) computed; GATING applied (UO→0 if F or CF →0); gap G = C_ι − C_μ
[ ] 7. Decomposability profile across all candidate levels (closed? low-dim? intervention-respecting?
       abstracts upward?)
[ ] 8. Honest report: (KA,UO)±err, profile, validated ι-machine, residual indeterminacy (T3), ladder rung
```

*This protocol instantiates Parts IV (criteria), VI (dimensions), VII (benchmarks), and IX (ι-machine,
Genesis, reflexive turn). It is referenced from the position paper §11 (Recommendations).*
