# Part IX — Deep Theory and Original Reflections

Parts I–VIII assembled the literature, the taxonomy, the criteria, and a first framework (the
Understanding–Knowledge Gradient, UKG). This Part goes deeper. It does four things the earlier
material only gestured at:

1. **Gives a precise formal object for "mechanistic compression"** — the **ι-machine**
   (iota-machine), the intervention-closed analogue of the ε-machine of computational mechanics —
   and with it a notion of **causal/mechanistic complexity** distinct from statistical complexity.
2. **Turns the framework's claims into stated propositions with proof sketches**: the data ceiling
   (T1), the clever-predictor gap (T2), and a new **indeterminacy theorem** (T3) identifying the
   *resolution limit* of understanding.
3. **Proposes an original thesis — the Genesis (Provenance) Principle** — that explains *why* some
   complex systems are intelligible and others are not, reframing Jonas–Kording/Lazebnik as a claim
   about how a system was *built*, and predicting that interpretability of trained networks is a
   structurally harder problem than reverse-engineering a microprocessor.
4. **Takes the reflexive turn**: the understander is itself a complex system subject to Ashby's
   requisite variety, which yields a **cost of understanding**, an **understanding horizon**, and a
   reframing of scientific instruments as variety amplifiers.

These are intended as the thesis's genuinely novel content; they are speculative where marked, but
each is stated so as to be criticizable and, where possible, testable.

---

## 1. The ι-machine: intervention-closed minimal models

### 1.1 Background: the ε-machine is only predictively minimal

Computational mechanics (Crutchfield & Young 1989; Shalizi & Crutchfield 2001) defines, for a
stochastic process, the **causal states** as equivalence classes of pasts that induce the same
*conditional distribution over futures*:
`x⁻ ∼_ε x'⁻  ⇔  P(X⁺ | x⁻) = P(X⁺ | x'⁻)`.
The **ε-machine** is the minimal automaton over these states; its **statistical complexity**
`C_μ = H[causal states]` is the amount of history one must remember to predict optimally. The
ε-machine is provably the *minimal sufficient statistic for prediction* — the smallest model that
loses no predictive information.

This is exactly the object the UKG calls high-`KA`, low-`UO`: **it is minimal for prediction, and it
is built entirely from the observational distribution.** Two systems with identical input–output
statistics have the *same* ε-machine even if their internal mechanisms differ — the ε-machine cannot
see the difference, because the difference only shows up under intervention. The ε-machine is the
formal fixed point of "knowledge about."

### 1.2 The construction: causal states under intervention

We propose the natural upgrade. Equip the system with an **intervention algebra** `𝓘` (the
well-defined `do(·)` operations, in Pearl's sense, possibly including interventions on internal
variables). Define an equivalence on histories *and* on the system's configurations by demanding
agreement of *intervention-conditioned* futures, for **every** intervention in `𝓘`:

> **Definition (ι-causal states).** Configurations `s, s'` are ι-equivalent,
> `s ∼_ι s'`, iff for *all* ι ∈ 𝓘 and all futures,
> `P(X⁺ | s, do(ι)) = P(X⁺ | s', do(ι))`.
> The **ι-machine** is the minimal automaton over the ι-causal states, with transitions labeled by
> both spontaneous dynamics and elements of 𝓘. Its size is the **causal (mechanistic) complexity**
> `C_ι = H[ι-causal states]`.

Equivalently: collapse two states only if they are indistinguishable *no matter how you poke the
system*. This is strictly finer than ε-equivalence whenever interventions reveal structure that
passive observation hides.

### 1.3 Why this is the right object for "understanding"

- **It is the minimal sufficient statistic for *control*, not just prediction.** By construction the
  ι-machine retains exactly the information needed to answer every `do`-query in 𝓘 — Pearl rung 2,
  and (with counterfactual closure on the structural equations) rung 3. It is the smallest object
  that makes the modeling relation of Part VI *commute under intervention*.
- **It formalizes "mechanism-structured compression" (the `K` dimension done right).** The UKG asked
  for a description that is short *and* in a vocabulary of interventionally-meaningful parts. The
  ι-machine is precisely that: the minimal description that is **closed under the intervention
  algebra**. "Compression done right" = MDL *relative to 𝓘*, not relative to the raw data stream.
- **It separates two complexities.** `C_μ ≤ C_ι` always (you never need *fewer* states to support
  interventions than to support prediction). The **understanding gap of Part VI becomes a
  complexity gap**:
  `G_struct = C_ι − C_μ ≥ 0`.
  When `G_struct = 0`, the predictive model already encodes the full causal structure — prediction
  *coincides* with understanding (typical of small, designed, transparent systems). When
  `G_struct ≫ 0`, there is a large reservoir of mechanism invisible to any observational method —
  **this is the microprocessor/brain regime, now a number.** `G_struct` is, we propose, the right
  formal measure of "how much understanding is being left on the table by prediction-only methods."

### 1.4 Worked intuition (the two-mechanism trap)

Consider two coupled toggles whose *observed* output is their XOR, driven by the same input
distribution by (a) a direct XOR gate, vs. (b) a redundant majority-of-three with a tied vote. For a
suitable input distribution the **observational distributions coincide** → identical ε-machine,
identical `C_μ`, identical predictive score. But `do(set one internal line)` produces different
outputs → **different ι-machines**, different `C_ι`. A method confined to rung 1 (the ε-machine, a
linear probe, an encoding model) *cannot* tell these apart; only an interventional method can. This
is the abstract skeleton of Jonas–Kording's finding and of the probing-vs-patching gap in
interpretability — and it shows the distinction is not sociological but **information-theoretic**:
the missing bits are `C_ι − C_μ`, and they are not in the data.

### 1.5 Hierarchy as ι-machine quotients (link to Part V)

A *level* in the sense of Part V is a **quotient of the ι-machine that is still an ι-machine** — a
coarse-graining of ι-causal states that remains closed under the (coarse-grained) intervention
algebra. This is exactly the causal-abstraction commuting condition (Beckers–Halpern), now phrased
inside computational mechanics. The **decomposability profile** becomes: *for each candidate
quotient, does closure-under-𝓘 survive?* Causal emergence (Hoel) is the statement that some quotient
can have **lower** `C_ι` per unit of effective information — a genuinely better level. Holism (no
clean level) is the statement that **no nontrivial closed quotient exists**: the ι-machine is
quotient-irreducible. This gives "irreducible complexity" a crisp meaning: *the ι-machine has no
proper congruence respecting 𝓘.*

---

## 2. Three propositions (stated and sketched)

Throughout, fix a system `S` with intervention algebra `𝓘`, observational distribution `P_obs`, and
a model `M` scored by the UKG dimensions. Let `UO` and `KA` be as in Part VI.

### T1 — The data ceiling (no understanding from observation alone)

> **Proposition (T1).** Let `𝔐_obs` be the set of all models inferable from `P_obs` alone (any amount
> of passive data). Then `sup_{M ∈ 𝔐_obs} UO(M)` is bounded by a ceiling determined solely by the
> observational equivalence class of `S`; in particular, if two systems `S, S'` with different
> ι-machines share `P_obs`, no `M ∈ 𝔐_obs` can have high `UO` for both, and at least one incurs
> understanding error ≥ `½·d(ι-machine(S), ι-machine(S'))`.

*Proof sketch.* Observational data identifies `S` only up to its ε-machine (its `P_obs`-equivalence
class). `UO` depends (via `CF`, `F`, `CC`) on intervention-conditioned distributions, which are
constant within an ε-class only if `C_ι = C_μ`. Where `C_ι > C_μ`, distinct ι-machines populate the
same ε-class; any single observational model misallocates interventional probability for at least one
of them, bounding `UO` below 1 by the ι-machine distance. ∎ (This is the formal core of Pearl's
rung-1→rung-2 impossibility, ICP's need for multiple environments, and the unidentifiability results
of causal representation learning — they are three instances of one bound.)

**Corollary (what raises the ceiling).** Adding interventions (enlarging the *realized* part of `𝓘`),
multiple environments, or structural inductive biases is the *only* way to lift the ceiling — each
shrinks the observational equivalence class toward the ι-machine.

### T2 — The clever-predictor gap (prediction does not estimate understanding)

> **Proposition (T2).** Whenever `C_ι > C_μ`, there exists a model `M*` with maximal `KA`
> (predictively optimal, maximally compressed in the ε-sense) and `UO(M*) ≈ 0`. Hence `KA` is not a
> consistent estimator of `UO`: `E[UO | KA]` is not monotone, and no threshold on `KA` certifies
> understanding.

*Proof sketch.* Take `M* =` the ε-machine itself (or any rung-1-optimal predictor). It maximizes
`KA` by definition and carries zero interventional content beyond what `P_obs` forces; where
`C_ι>C_μ` this leaves `CF`/`F` arbitrarily low, gating `UO→0`. ∎

**Reading.** T2 is the precise statement of "more accuracy ≠ more understanding" demanded by the
brief. It also licenses the **predictor-control** requirement of the Part VII benchmarks: a benchmark
that cannot exhibit an `M*` cannot demonstrate the distinction.

### T3 — The indeterminacy theorem (the resolution limit of understanding)

This one is new and, we think, the most interesting.

> **Proposition (T3).** Understanding is determined *only up to ι-machine isomorphism*. Two
> mechanisms that induce the *same* intervention-conditioned distributions for *every* ι ∈ 𝓘 are
> **indistinguishable by any method whatsoever**, with unbounded data and unbounded interventions in
> 𝓘. Consequently the maximal achievable understanding of `S` is `UO = 1` *relative to `𝓘`*, and the
> identity of the "true mechanism" beyond the ι-machine is **not a scientific question** for that
> agent.

*Proof sketch.* `UO` is a functional of intervention-conditioned distributions over 𝓘 (Part VI's
commuting condition). If two structural models agree on all of these, every UexO dimension scores
identically; no experiment in the agent's repertoire (= 𝓘) separates them. ∎

**Why this matters.**
- **The intervention algebra is the "resolution limit" of understanding**, exactly as the aperture
  sets the resolution limit of a microscope. You cannot understand *below* the grain of the
  interventions you can perform. Multiple realizability (Part-IV problem) is not a nuisance to be
  eliminated but the *generic* situation: there is always a residual equivalence class, and its size
  is set by 𝓘.
- It **dissolves a pseudo-problem**: arguing about which of two ι-equivalent mechanisms is "really"
  there is, for that agent, meaningless — a structural-realist's selective realism falls out
  naturally (be a realist about the ι-machine, agnostic below it). This is a principled middle
  ground between scientific realism and instrumentalism (Part I §1): **realism up to the resolution
  limit.**
- It gives a **growth path**: enlarging 𝓘 (finer interventions — optogenetics at single-cell
  resolution, single-weight edits) *refines* the equivalence class and is the only thing that can.
  Progress in understanding = improving the resolution of the intervention repertoire, not
  accumulating observations.

**Three theorems, one picture.** T1 says observation caps you below the ι-machine; T2 says the cap is
real and prediction won't tell you you've hit it; T3 says the ι-machine itself is the ceiling — you
cannot, even in principle, resolve finer than your interventions. Prediction undershoots
understanding (T1/T2); understanding undershoots "the whole truth" (T3); and both gaps are
*quantified* (`C_ι−C_μ`, and the residual ι-equivalence class).

---

## 3. A category-theoretic home for the modeling relation

The commuting-diagram language of Part VI is naturally categorical, which sharpens "faithfulness"
and "abstraction."

- Let **Sys** be the category whose single object's structure is `S`'s state space with morphisms
  generated by the dynamics and by the intervention algebra `𝓘` (a "causal category": objects =
  variable-contexts, morphisms = interventions/mechanisms). Pearl's `do` makes this a monoidal
  category of interventions (cf. categorical probability / Markov categories, Fritz 2020).
- A **model** is a functor `M: Sys → Mdl` into the model's causal category.
- **Faithfulness (`F`)** = the functor *preserves the intervention structure*: it sends `do_S(ι)` to
  `do_M(ι)` and commutes with composition — i.e., the Part-VI diagram is the naturality square of `M`.
  A merely-predictive model is a functor that preserves only the *observational* (marginal) structure
  — it factors through the "forget the interventions" functor `Sys → Stoch`. **The understanding line
  is the gap between functors into Stoch and functors that preserve 𝓘.**
- **Causal abstraction / levels (`HC`)** = the coarse-graining is a (monoidal) functor `Sys → Sys_L`
  such that the macro-model is a natural transformation making the square commute — Rubenstein/
  Beckers–Halpern exactly. A *level* is a quotient functor under which 𝓘 descends.
- **Multiple realizability / T3** = two models are "the same understanding" iff naturally isomorphic
  as 𝓘-preserving functors. The ι-machine is the **terminal** such object (the universal minimal
  faithful model), giving T1–T3 a one-line statement: *understanding = the terminal 𝓘-preserving
  functor; observation only determines the terminal Stoch-functor; their difference is `C_ι−C_μ`.*

This is not decoration: it tells you *what to check* (naturality squares = interchange-intervention
tests), *what abstraction is allowed* (quotient functors preserving 𝓘 = legitimate coarse-grainings),
and *what is indeterminate* (everything below natural-iso of 𝓘-functors).

---

## 4. The Genesis Principle: intelligibility is a fossil of construction

Here is the Part's central original thesis. It answers a question the literature mostly leaves
implicit: **why are some complex systems intelligible and others not?** Simon answers "because they
are nearly decomposable" — but *why* are they nearly decomposable? Our answer:

> **The Genesis (Provenance) Principle.** A system's intelligibility is upper-bounded by the
> structure imprinted on it by the *process that built it*. Construction processes that themselves
> proceed by understanding (design) necessarily imprint a decomposable, modular, hierarchical
> organization — the designer's own ι-machine — and so produce *intelligible* artifacts.
> Construction processes that proceed *without* understanding (natural selection, gradient descent,
> self-organization) are under **no such constraint**: they can, and under pressure for performance/
> compactness routinely do, produce **entangled, non-decomposable, holistic** organizations that are
> intelligible only to the extent that *incidental* pressures (modularity-for-evolvability, weight
> decay, dropout, architectural bottlenecks) happen to imprint structure.

### 4.1 The argument

- **Design is a homomorphism from the designer's understanding to the artifact.** An engineer builds
  a radio/CPU by *composing modules she understands* across *interfaces she specifies*. The artifact
  therefore *inherits* a near-decomposable hierarchy — not by physical necessity but because **the
  build process is itself a hierarchical, intervention-closed plan** (the designer's ι-machine).
  Decomposability is, literally, the trace of the designer's bounded rationality (Simon's "satisficing"
  + requisite variety): a designer who cannot hold the whole system in her head *must* modularize to
  build at all. **The intelligibility of engineered systems is therefore not a lucky fact about them —
  it is the same bound that made them buildable.**
- **Optimization carries no such guarantee.** Evolution and SGD search the space of *behaviors*, not
  the space of *understandable mechanisms*. They are free to exploit dense, distributed, polysemantic,
  superposed solutions — and these are often *cheaper* (fewer parameters/components for given
  performance: superposition is literally compression that violates modularity). Where modularity
  appears in evolved/trained systems it is because of *secondary* selection (modular networks adapt
  faster — Kashtan & Alon; modularly-varying goals) or *regularization* (architectural bottlenecks,
  weight sparsity), not because the generator needed to understand its product.

### 4.2 The reframing of Jonas–Kording / Lazebnik

This dissolves a puzzle in the two motivating papers. They are usually read as "our methods are bad."
The Genesis Principle gives a deeper reading:

- **The microprocessor is the *easy* case, and that is the point being missed.** Jonas–Kording chose a
  *designed* system, which by the Genesis Principle is *maximally* intelligible (its ι-machine is the
  designers'). Their finding — that neuroscience methods fail *even here* — is therefore doubly
  damning for those methods: they fail on the *most* decomposable possible target.
- **But it also means the brain is not just "a harder microprocessor."** The brain was built by
  evolution + development + learning — three understanding-free processes. The Genesis Principle
  predicts the brain need not be decomposable to the degree a CPU is, so methods *calibrated on the
  CPU's intelligibility* may be systematically over-optimistic about the brain. **The right null
  hypothesis for a learned/evolved system is partial holism, not hidden modularity.**
- **Mechanistic interpretability inherits this exactly.** A trained transformer was built by SGD
  (understanding-free). The Genesis Principle predicts: (i) its functional organization is **not
  guaranteed** to be a clean feature→circuit→algorithm hierarchy; (ii) superposition/polysemanticity
  are the *expected* signature of an understanding-free compressor, not a surprising anomaly; (iii)
  interpretability successes will cluster on **sub-tasks with incidental modularity pressure**
  (induction heads, modular arithmetic, narrow circuits) and stall on **densely-optimized capabilities**
  — which is, empirically, what we observe. **Interpretability of trained nets is therefore not the
  same kind of problem as reverse-engineering a CPU; it is closer to reverse-engineering biology,**
  and should borrow biology's expectations (degeneracy, distributed codes, context-dependence) rather
  than engineering's.

### 4.3 A testable corollary (the Provenance–Decomposability prediction)

> **Prediction.** Hold behavior fixed and vary *only the generator*: build systems with the *same*
> input–output function via (a) hand design, (b) evolutionary search, (c) gradient descent with
> varying regularization/architectural bottlenecks. Then the **decomposability profile** (Part V) and
> the **mechanistic faithfulness `F`** achievable by any fixed interpretability method should be
> *ordered by the structure-imprinting pressure of the generator*: design > regularized/bottlenecked
> optimization > unconstrained optimization. The understanding gap `G_struct = C_ι − C_μ` should
> *grow* as construction becomes more understanding-free.

This is directly runnable on the Part-VII benchmark suite (logic circuits, small transformers, GRNs)
and would either support or refute the Genesis Principle. It also yields an **engineering
recommendation**: if we want intelligible AI, *bias the generator toward imprinting structure*
(modularity priors, bottlenecks, curricula) — i.e., **interpretability is partly a training-time
decision, not only a post-hoc analysis.** This connects the philosophy directly to AI-safety practice.

### 4.4 Relation to existing ideas (honest placement)

The Genesis Principle is a synthesis, not a bolt from the blue. Its ingredients: Simon's link between
bounded rationality and hierarchy; "modularity for evolvability" (Kashtan–Alon, Wagner, Clune et al.'s
"cost of connections"); Conant–Ashby's good-regulator theorem (a controller that *is* a model);
Thompson's evolved FPGA (an artifact its maker did not understand). The novel move is to make
**provenance the explanatory variable for intelligibility** and to derive from it a *predictive
ordering* over generators and a *recalibration* of the null hypothesis for brains and trained
networks. We state it as a falsifiable principle precisely so it can be attacked.

---

## 5. The reflexive turn: the understander is a complex system

Almost every account of understanding (including Parts I–VIII) treats the agent as an idealized,
unbounded knower. Drop that idealization and new structure appears.

### 5.1 Requisite variety, applied to the scientist

Ashby's Law of Requisite Variety says a regulator can control a system only if it has at least as much
variety as the disturbances it must counter; Conant–Ashby sharpen this to *every good regulator
contains a model of the system.* **Apply this to the understander, not the controller:** to *model*
`S` faithfully (to instantiate its ι-machine), the agent's representational medium must have at least
`C_ι(S)` bits of effective variety. Therefore:

> **The variety bound on understanding.** A bounded agent `A` with representational capacity `V(A)`
> can fully understand `S` only if `V(A) ≥ C_ι(S)` (at the chosen level). For `C_ι(S) > V(A)`,
> understanding is possible *only after coarse-graining `S` to a level whose `C_ι` fits inside
> `V(A)`* — i.e., **hierarchy is forced not by the system but by the finitude of the understander.**

This re-derives Part V's "hierarchy is de-facto-necessary for *complex* systems" from the agent side:
we coarse-grain because we *must*, and the levels we find are partly a projection of our own capacity.
(It also explains why the *same* system is "understood" at different grains by a child, an
undergraduate, and an expert — different `V`, different forced level.)

### 5.2 The cost of understanding, and the understanding horizon

If building the ι-machine of `S` costs resources (samples from 𝓘, experiments, compute, time), then
understanding has a **price** that scales with `C_ι` and with the *number of interventions* needed to
refine the observational class to the ι-class (T1's corollary). Two consequences:

- **Cost asymmetry prediction → understanding.** Prediction needs `C_μ`; understanding needs `C_ι`
  *plus* the interventional sampling to pin it down. The ratio of these costs is another face of the
  understanding gap. For systems with `C_ι ≫ C_μ` (brains, frontier models), understanding is not
  marginally but *categorically* more expensive than prediction — which is exactly why prediction
  races ahead and understanding lags.
- **The understanding horizon.** There may exist systems that are *understandable in principle* (their
  ι-machine is well-defined) but *understandable by no bounded agent* — `C_ι` exceeds any feasible
  `V(A)` *and* admits no closed coarse-graining (Part V holism: the ι-machine is
  quotient-irreducible). For such systems, **no hierarchy rescues us**, and the best any bounded agent
  can do is predict (rung 1) plus demonstrate the irreducibility. We conjecture **frontier neural
  networks and whole brains may lie partly beyond the horizon at the mechanistic level** — not because
  understanding is mystically impossible, but because the only faithful model is as big and as
  entangled as the system itself (Borges's 1:1 map; Rosen's complex systems with no largest model).
  This is a sharper, less comfortable claim than "we just need better tools."

### 5.3 Instruments as variety amplifiers; understanding as co-evolution

If `V(A)` is the binding constraint, then **scientific instruments and formalisms are variety
amplifiers** (Ashby's "amplifying intelligence"): the microscope, the oscilloscope, the activation-
patching harness, the SAE, and indeed *the computer* extend the agent's effective `V` and effective
𝓘. This reframes methodology: a method "produces understanding" partly by **enlarging the agent's
intervention algebra and representational capacity** (raising the T1 ceiling and the T3 resolution),
not only by analyzing fixed data. It predicts that the decisive advances in understanding complex
systems will be *instrumental* (new ways to intervene at fine grain — optogenetics, single-weight
edits, causal scrubbing) more than *analytical* (new ways to fit observational data). The history of
science (the telescope, the microscope, the cloud chamber) is largely a history of variety
amplification — understanding co-evolves with the apparatus that extends 𝓘.

### 5.4 Is machine-discovered, human-ungraspable mechanism *understanding*?

The reflexive turn forces the question raised in Open Problem 20. Suppose an AI recovers a faithful,
hierarchically-consistent, interventionally-validated ι-machine of a brain region that **no human can
grasp** (`F, HC, CC` high; human-`X` ≈ 0). Two positions:

- **Agent-neutral:** understanding is the *object* (the faithful 𝓘-preserving functor); whoever/whatever
  holds it understands. Then the AI understands, and humans can *inherit* it by coarse-graining to a
  human-`V` level (accepting T1's ceiling at that level).
- **Agent-relative (de Regt):** understanding requires *grasp*; an ungraspable model is "knowledge
  that the mechanism is M" without "understanding of M." Then the AI's artifact is, for us, back to
  high-`KA`/low-human-`UO` — the gap reappears one level up.

We take a **two-place** view consistent with the whole framework: understanding is always
`understanding(S, A)` — relativized to the agent's `V` and 𝓘. The AI understands at its level; we
understand at ours; and the *translation* between them is itself a causal-abstraction problem
(find the human-`V` quotient of the AI's ι-machine that still commutes). **Automated interpretability
is then literally the project of computing human-graspable quotients of machine-discovered
ι-machines** — which is a concrete research program, not a paradox.

---

## 6. Summary: what Part IX adds

| Contribution | One-line statement | Status |
|---|---|---|
| **ι-machine** | minimal model *closed under the intervention algebra* (vs ε-machine = minimal predictor) | formal definition; extends computational mechanics |
| **Causal complexity `C_ι`** | bits needed to support all interventions; `C_ι ≥ C_μ` | new measure; `G_struct = C_ι−C_μ` quantifies the understanding gap |
| **T1 data ceiling** | observation caps `UO` below the ι-machine | proposition + sketch (unifies Pearl/ICP/CRL impossibilities) |
| **T2 clever-predictor gap** | `KA` is not a consistent estimator of `UO` | proposition + sketch (formal Jonas–Kording) |
| **T3 indeterminacy** | understanding is determined only up to ι-machine iso; 𝓘 is the resolution limit | **new**; yields "realism up to resolution," dissolves multiple-realizability pseudo-problem |
| **Categorical modeling relation** | understanding = terminal 𝓘-preserving functor; prediction = Stoch-functor | new framing; faithfulness = naturality, levels = quotient functors |
| **Genesis Principle** | intelligibility is bounded by the structure the *generator* imprinted; design imprints it, optimization need not | **new thesis**; reframes JK/Lazebnik, predicts interp-of-trained-nets is biology-like, gives training-time recommendation + falsifiable Provenance–Decomposability prediction |
| **Variety bound** | full understanding requires `V(A) ≥ C_ι`; hierarchy forced by finite agents | re-derives Part V from the agent side |
| **Understanding horizon** | some systems are understandable-in-principle but by no bounded agent | **new conjecture**; brains/frontier nets may lie partly beyond it |
| **Instruments as variety amplifiers** | progress in understanding is mostly instrumental (extend 𝓘), not analytical | reframes methodology; predicts intervention-tech, not data-volume, drives understanding |

The through-line remains the project's thesis, now with teeth: **knowledge about a system is the
ε-machine (and `C_μ`); understanding of a system is the ι-machine (and `C_ι`); the difference is real,
quantified, bounded below by the intervention algebra (T3), expensive (the variety bound), and — for
understanding-free-generated systems like brains and trained networks — possibly the hardest problem
in science (the Genesis Principle + the horizon).**
