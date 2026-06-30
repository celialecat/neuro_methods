# When Have We Understood a Complex System? From Prediction to Mechanism

**A framework for distinguishing knowledge *about* a system from understanding *of* a system**

*Perspective — formatted in the style of a Nature Reviews / PNAS Perspective. ~6,000 words main text, 3 Boxes, 3 figure specifications, 1 table.*

*Running head:* Knowledge about vs. understanding of complex systems

---

## Significance statement

Predictive performance is accelerating across the sciences — in neuroscience, systems biology, and
artificial intelligence — and is widely read as evidence of growing understanding. Two thought
experiments (could a neuroscientist understand a microprocessor; could a biologist fix a radio) show
this inference is unsafe: the standard analytic toolkit can be applied in full to a system whose
mechanism is completely known and still fail to recover it. We argue the gap is principled, not
technical, and make it measurable. We separate *knowledge about* a system (prediction, compression,
representation, correlation) from *understanding of* it (interventionally validated, faithful,
level-appropriate mechanism), give a graded definition and two coordinates that turn the worry into
theorems, and propose ground-truth benchmarks. The framework reclassifies methods in neuroscience and
in the mechanistic interpretability of neural networks, and explains *why* trained networks resist
interpretation.

## Abstract

The analytic toolkit of data-rich science — tuning curves, lesions, correlations, dimensionality
reduction, connectomes, decoders — can be applied in full to a system whose mechanism is completely
known, such as a microprocessor or a radio, and still fail to recover that mechanism (Lazebnik 2002;
Jonas & Kording 2017). The lesson is epistemological: **prediction, compression, representation, and
correlation are achievements of *knowledge about* a system that do not, by themselves, constitute
*understanding of* it.** We make the distinction precise. Building on the philosophy of explanation
(Hempel; Salmon; Woodward; Craver; Strevens), systems and complexity science (Simon; the
renormalization group; Rosen; Ashby), information theory (Kolmogorov/MDL; the information bottleneck;
computational mechanics; effective information), and causal inference (Pearl; invariant prediction;
causal abstraction), we cast understanding as a **graded profile over measurable dimensions**, gated
so that no amount of predictive or compressive performance counts as understanding without
interventionally validated, faithfulness-bearing, level-appropriate structure. We formalize an
**epistemic ladder** and an **Understanding–Knowledge Gradient** whose coordinates `(KA, UO)` convert
the Jonas–Kording/Lazebnik worry into three theorems: observation cannot lift a model above the
understanding line (T1); predictive score does not estimate understanding (T2); and understanding is
determined only up to the resolution of the available interventions (T3). We give the minimal object
that supports understanding — the **ι-machine**, the intervention-closed analogue of the ε-machine —
so that the gap becomes a complexity difference `C_ι − C_μ`. We propose **benchmarks with known
ground-truth mechanism** and a **decomposability profile** that reports, rather than assumes,
hierarchy. Applied to neuroscience and to mechanistic interpretability, the framework splits both
fields identically into a large knowledge-about arm, routinely over-read as understanding, and a
smaller understanding arm distinguished by intervention, faithfulness, and level. Finally, the
**Genesis Principle** explains *why* some complex systems are intelligible and others are not:
intelligibility is a fossil of construction, so that designed artifacts inherit a decomposable
structure that evolved and trained systems need not — making the interpretability of neural networks
structurally more like reverse-engineering biology than like reverse-engineering a chip.

**Keywords:** scientific understanding · mechanistic explanation · causal inference · complex
systems · interpretability · computational mechanics · philosophy of science

---

## 1. Introduction

Modern science is awash in predictive success. Deep networks predict protein structures and the next
word; high-dimensional neural recordings decode intentions and movements; foundation models pass
professional examinations. It is natural — and increasingly common — to read this flood of predictive
and representational achievement as a proxy for understanding: if our models are this accurate, surely
we are coming to understand the systems they model.

Two thought experiments warn that the inference is unsafe. Lazebnik (2002) asked whether a biologist,
equipped with the methods of molecular biology, could fix a radio; Jonas and Kording (2017) asked
whether a neuroscientist, equipped with the methods of systems neuroscience, could understand a
microprocessor. Both took a system understood *completely* because it was engineered, generated the
kinds of data their fields collect, and applied the field's standard analyses. The results — tuning
curves, lesion effects, "functional connectivity", low-dimensional projections — *look* like insight
but do **not** reconstruct the known architecture. A method can be maximally successful by a field's
own metrics and recover no mechanism at all.

This is not a complaint about any one technique, nor a counsel of despair. It is a diagnosis of a
**category error**: conflating the epistemic goal a method actually serves with the goal we ascribe
to it. The aim of this Perspective is to dissolve that error by making the distinction it rests on
*precise, measurable, and enforceable*, and to do so in a way that transfers to the two fields the
question ultimately targets — neuroscience and the mechanistic interpretability of artificial neural
networks.

Our thesis is a single sentence: **methods that improve prediction, representation, compression, or
accuracy produce *knowledge about* a system; understanding *of* a system additionally requires
recovering its causal-mechanistic, hierarchical structure together with the competences that
structure confers. Higher accuracy is not, by itself, more understanding.** Everything below is an
attempt to give this sentence teeth — a definition, coordinates, theorems, a minimal formal object,
benchmarks, and a reclassification of the methods that matter.

We use a small running lexicon (Box 1). Throughout, the **epistemic object** a method recovers
(statistical regularity, representation, causal relation, mechanism, abstraction, hierarchy,
invariant, generative principle) is the unit of analysis: for each method we ask *what object did you
recover, and is that object sufficient for understanding?*

> **Box 1 — A lexicon.**
> **Knowledge about (`KA`):** what a model captures of a system's *observable, predictive* structure —
> regularities, representations, descriptions, correlations. Built from observation alone.
> **Understanding of (`UO`):** what a model captures of a system's *causal-mechanistic* structure,
> validated by intervention, at an appropriate level, together with the competences (counterfactual,
> interventional, repair, redesign, transfer, failure-explanation) it confers.
> **Epistemic object:** the kind of thing a method recovers. The paper's recurring question is whether
> the recovered object is sufficient for `UO`.
> **Intervention algebra `𝓘`:** the set of well-defined manipulations (Pearl's `do(·)`) an agent can
> actually perform on the system, including on internal variables.
> **Level:** a coarse-graining of the system that remains a self-contained, intervention-respecting
> description. **Faithfulness:** the model's parts and their manipulations correspond to the system's,
> as checked by matched interventions.

---

## 2. The knowledge/understanding distinction, sharpened

It helps to state what is *not* being claimed. We are not reviving a mystical residue that prediction
leaves out, nor denying that prediction is an epistemic achievement; predictive success is necessary,
hard-won, and often the only handle we have. Nor are we claiming that understanding is binary or
purely human. The claim is structural: understanding requires a *different kind of object* than
prediction does, an object that observation under-determines.

The cleanest way to see this is to ask what information each goal needs. Prediction needs the
system's **observational distribution** `P(behaviour)`: enough of the joint statistics to forecast
unseen-but-same-regime data. Understanding needs the system's **interventional and counterfactual
distributions** `P(behaviour | do(ι))` for the manipulations `ι` we care about: what the system would
do *were we to change it*. These are different objects, and — crucially — the second is not a function
of the first. Two systems can share every observable statistic yet respond differently to the same
intervention; no quantity of passive data distinguishes them, because the distinguishing evidence
only exists once someone intervenes (Pearl 2009; Woodward 2003). This is the seed of everything that
follows.

The distinction lines up with a long tradition that located **explanation** not in derivation or
forecast but in *difference-making structure*. Hempel's covering-law model foundered on cases — the
flagpole and its shadow, the barometer and the storm — where lawful derivation runs in the wrong
direction or rides on a common cause (Salmon 1989). Salmon relocated explanation in causal-mechanical
processes; Woodward (2003) in relations that are *invariant under intervention*; Machamer, Darden and
Craver (2000) and Craver (2007) in *mechanisms* — entities and activities, organized, productive of a
phenomenon. Strevens (2008) made difference-making the criterion of explanatory relevance. Across
these accounts the through-line is the same as ours: **what explains is causal-mechanical structure,
and that structure is read off interventions, not correlations.**

---

## 3. Why the gap is principled, not a shortage of data

Five independent literatures converge on one conclusion (developed in the companion review, Part I).

1. **Explanation is asymmetric, relevant, and causal; prediction is none of these** (Hempel→Salmon→
   Woodward→Craver, above). A predictively perfect model can encode the symmetry-broken, common-cause,
   and irrelevant structure that explanation must exclude.
2. **Pearl's ladder proves the gap.** Association (rung 1), intervention (rung 2), and counterfactual
   (rung 3) are strictly increasing in expressive power, and one cannot climb from rung 1 to rungs 2–3
   *from observational data alone* — only from interventions or structural assumptions (Pearl 2009;
   Bareinboim et al. 2022). Prediction lives on rung 1; understanding on rungs 2–3.
3. **Identifiability results in machine learning say the same thing.** Disentangled and causal
   representations are unidentifiable without inductive biases, interventions, or multiple environments
   (Locatello et al. 2019; Schölkopf et al. 2021). Passive fit under-determines mechanism.
4. **Compression is necessary but not sufficient.** Structure shows up as compressibility (Kolmogorov;
   Rissanen's MDL; Simon's redundancy; Kitcher's unification), but the shortest code can be opaque,
   merely *predictively* sufficient, and multiply realizable. The information bottleneck discards
   causal-but-redundant variables; the ε-machine of computational mechanics (Crutchfield 2012) is the
   minimal *predictive* model, not necessarily the mechanism. *A short description in the wrong
   vocabulary is not understanding.*
5. **A complete low-level description is not understanding.** The *C. elegans* connectome — every
   neuron and synapse of a 302-cell nervous system — does not yield its behaviour, because function
   depends on dynamics and neuromodulation absent from the wiring (Bargmann & Marder 2013). The
   connectome is a mechanism sketch with the activities missing.

These are not five observations but one, stated five ways: **there is a gap between the statistical
structure of a system's behaviour and its causal-mechanistic structure, and the gap is not a
data-volume problem.** §5 turns this informal claim into a formal object and quantifies the gap.

---

## 4. The framework: understanding as a gated profile

We treat a candidate understanding as a **model** `M` held by an **agent** `A` about a **system** `S`,
related by encode/infer/decode maps, evaluated at a chosen **level** `L` against a **question battery**
`Q`. The single condition that separates prediction from understanding is that the modeling relation
**commute under intervention** (Fig. 1):

> Performing an intervention *in the model* and decoding the result should match performing the
> intervention *in the world* and observing it — not merely matching outputs under passive observation.

Passive-observation match is prediction (rung 1); commuting-under-intervention is understanding (rungs
2–3). This is Rosen's (1985) modeling relation made operational with Pearl/Woodward machinery, and it
is the formal location of the Jonas–Kording/Lazebnik gap.

### 4.1 An epistemic ladder

We distinguish seven achievements, each adding a specific epistemic object:

**Knowing** (facts/descriptions) → **Predicting** (rung-1 forecasts) → **Modeling** (a runnable
generative simulator) → **Explaining** (difference-making structure) → **Understanding** (a grasped,
intervention-faithful, abstracted model usable across a broad counterfactual battery) →
**Reverse-engineering** (that understanding decomposed into the system's *actual* organized parts,
validated by part-level intervention) → **Mechanistic understanding** (hierarchically consistent
across levels, supplying the computational *why*).

The first three rungs are reachable with more data and compute alone; crossing from *modeling* to
*explaining/understanding* requires interventional content that, by §3, data cannot supply.
Lazebnik's "fix the radio" is reverse-engineering; Jonas–Kording's challenge demands mechanistic
understanding; the Hodgkin–Huxley action potential and the reverse-engineered modular-arithmetic
circuit in a small transformer (Nanda et al. 2023) are existence proofs that the top of the ladder is
reachable.

### 4.2 Measurable dimensions

Understanding is not scalar. We define dimensions in `[0,1]` (full definitions in Part VI; Table 1):
**predictive power** `P` (weighted to out-of-distribution), **counterfactual competence** `CF` (the
commuting-diagram score), **intervention capability** `IV`, **mechanism-structured compression** `K`
(short *and* in a vocabulary of composable parts), **mechanistic faithfulness** `F` (do the model's
parts map onto the system's, validated by interchange interventions), **hierarchical consistency**
`HC` (does a closed, low-dimensional, intervention-respecting description exist at each scale, with
commuting inter-level maps), **modularity** `MO`, **transferability** `T`, **robustness** `R`
(explains failure modes), **depth** `Δ` (range of invariance + the *why*), **intelligibility** `X`
(can a bounded agent reproduce the step-by-step mechanism), and **causal completeness** `CC` (no
unexplained interventional variance). The *object* dimensions `{F, CC, HC, MO, K}` say what structure
was recovered; the *competence* dimensions `{P, CF, IV, T, R, Δ, X}` say what the agent can do with
it.

### 4.3 The Understanding–Knowledge Gradient and three theorems

Aggregate the predictive/compressive dimensions into a **knowledge-about index** `KA` and the
causal-mechanistic-competence dimensions into an **understanding-of index** `UO`, where `UO` is
**gated**: it is near zero whenever faithfulness `F` or counterfactual competence `CF` is near zero,
*regardless of how high `KA` is*. Every `(model, system, level)` tuple then has coordinates `(KA, UO)`
and an **understanding gap** `G = KA − UO` (Fig. 2). The framework yields three propositions (stated
and proved in Part IX; here in words).

- **T1 — the data ceiling.** No amount of observational data raises `UO` above the understanding line;
  ascending requires interventions, multiple environments, or inductive biases. T1 unifies Pearl's
  rung-1→2 impossibility, the need for multiple environments in invariant causal prediction (Peters
  et al. 2016), and the unidentifiability results of causal representation learning as *one* bound.
- **T2 — the clever-predictor gap.** For any system with a nontrivial intervention algebra there exist
  models that maximize `KA` yet fail the interventional battery; hence **`KA` is not a consistent
  estimator of `UO`.** T2 *is* the Jonas–Kording statement: a perfectly predictive model of the
  microprocessor can be mechanistically empty.
- **T3 — the indeterminacy theorem.** Understanding is determined only up to the equivalence the
  intervention algebra can resolve: two mechanisms agreeing on all `P(· | do(ι))` for every `ι ∈ 𝓘`
  are indistinguishable by any method whatever. The intervention algebra is therefore the **resolution
  limit** of understanding, and multiple realizability is generic, not a defect. The honest stance is
  *realism up to the resolution limit*: be a realist about what your interventions can resolve,
  agnostic below it.

The payoff is that "improving prediction moves you rightward in `KA` but not upward in `UO`" is now a
theorem, and any study can be placed by its measured coordinates. The pathological-and-common regime
is the **top-left**: high `KA`, low `UO`, large gap — prediction dressed as understanding.

### 4.4 A definition

> **An agent understands a system at a level, to a degree, iff it possesses a model whose modeling
> relation *commutes under intervention* at that level (faithful, counterfactually competent, causally
> complete), which is *short in a vocabulary of composable parts organized into the system's actual,
> possibly hierarchical, structure* (compressed, modular, hierarchically consistent), and which the
> agent can *use* to answer a broad, anti-gameable battery of out-of-distribution, counterfactual,
> interventional, failure-mode, and cross-system-transfer questions and to produce a step-by-step
> generative account.** The degree is the gated aggregate `UO`; the understanding is *mechanistic*
> when it spans levels with commuting maps and supplies the computational *why*. **Knowledge about**
> the system is the predictive/descriptive achievement *without* the commuting-under-intervention
> clause — the large-gap regime.

The definition is relativized (to level and battery), graded, anti-gameable (interventional/OOD
battery, parts vocabulary), and multiple-realizability-aware (faithfulness is to intervention
behaviour at a level, so legitimate abstraction is allowed).

---

## 5. The minimal object: the ι-machine and the resolution limit

The framework's claims acquire a clean formal home in computational mechanics, suitably upgraded
(Box 2). Computational mechanics defines the **ε-machine** as the minimal model sufficient for
prediction — its states are equivalence classes of pasts inducing the same future distribution, and
its size, the **statistical complexity** `C_μ`, is the memory needed to predict optimally
(Crutchfield 2012). The ε-machine is built entirely from `P_obs`; two systems with identical
input–output statistics have the *same* ε-machine even if their internals differ. It is the formal
fixed point of *knowledge about*.

We propose the natural upgrade. Equip the system with its intervention algebra `𝓘` and merge two
configurations only if they are indistinguishable under *every* intervention, not merely in their
passive futures. The minimal automaton over these **ι-causal states** is the **ι-machine**, and its
size is the **causal complexity** `C_ι ≥ C_μ`. The ι-machine is the minimal sufficient statistic for
*control*, not just prediction; it is exactly the object that makes the modeling relation of §4
commute under intervention; and it makes "mechanism-structured compression" precise — minimal
description length *relative to the intervention algebra*. The knowledge/understanding gap then becomes
a **complexity gap**

```
G_struct = C_ι − C_μ ≥ 0,
```

the number of bits of mechanism that *no quantity of passive data can reveal*. For a designed
calculator `G_struct ≈ 0` — predicting it and understanding it nearly coincide. For a brain or a large
language model `G_struct` is enormous: this is the microprocessor/brain regime, now a number. T1–T3
acquire one-line statements: observation determines only the ε-machine (T1); the ε-machine maximizes
`KA` with `UO ≈ 0` whenever `G_struct > 0` (T2); and the ι-machine itself is the ceiling — nothing
below the grain of `𝓘` is resolvable (T3). A *level* (§6) is then a quotient of the ι-machine that
remains an ι-machine; an irreducible system is one whose ι-machine has no such proper quotient.

> **Box 2 — From ε-machine to ι-machine.**
> **ε-machine (prediction).** `x⁻ ∼ x'⁻ ⇔ P(X⁺ | x⁻) = P(X⁺ | x'⁻)`; minimal predictor; statistical
> complexity `C_μ`. Built from `P_obs`.
> **ι-machine (understanding).** `s ∼ s' ⇔ P(X⁺ | s, do(ι)) = P(X⁺ | s', do(ι))` for **all** `ι ∈ 𝓘`;
> minimal model closed under intervention; causal complexity `C_ι ≥ C_μ`.
> **Gap.** `G_struct = C_ι − C_μ` = bits of mechanism absent from any observational data.
> **Resolution (T3).** The ι-machine — hence understanding — is defined only up to the equivalence
> `𝓘` can resolve. Finer interventions (single-cell optogenetics; single-weight edits) refine it;
> more observation cannot.

---

## 6. Does understanding require hierarchy?

Almost universally, the structure that makes complex systems understandable is the same:
**near-decomposable hierarchy of nearly-closed levels** (Simon 1962; the renormalization group's
relevant variables and universality, Wilson 1979; Anderson's "more is different", 1972; causal
abstraction's commuting levels, Beckers & Halpern 2019; causal emergence's effective-information-
maximizing scale, Hoel et al. 2013). Our position is nuanced. Hierarchy is **not conceptually
necessary** for understanding *per se* — a pendulum needs none — but for complex systems it is **de
facto necessary**, because a bounded agent cannot build or grasp an un-hierarchized causal model of a
large, densely interacting system; the only known route is to find levels at which the description
*closes and compresses*. (§8 derives this necessity from the agent's side.)

We therefore recommend that "discovering hierarchy" be treated not as an assumed precondition but as a
**reported empirical result**: every understanding-seeking study should output a **decomposability
profile** — for each candidate scale, does a closed, low-dimensional, intervention-respecting
description exist, and how good is it (spectral gap, effective information, interface sparsity)? Where
clean levels exist, understanding *is* the recovered hierarchy of mechanisms. Where they do not —
genuinely integrated systems with high integrated information or synergistic computation — understanding
*relocates* from parts to global, dynamical, order-parameter variables, and the demonstration of
irreducibility is itself the finding. This is precisely where Lazebnik's localization strategy fails,
now stated quantitatively.

---

## 7. Why are some systems intelligible? The Genesis Principle

The framework so far says *what* understanding is and *why* prediction undershoots it. It does not say
*why some complex systems are intelligible at all* while others resist us. Simon answers that
persistent complex systems are nearly decomposable — but leaves open *why* they are. We propose an
answer (Box 3), and take it to be this Perspective's most consequential and most testable claim.

> **The Genesis (Provenance) Principle.** A system's intelligibility is bounded by the structure
> imprinted on it by the process that built it. A builder that proceeds *by understanding* — a
> designer — necessarily stamps a modular, hierarchical, intervention-closed plan (its own ι-machine)
> onto the artifact, and so produces *intelligible* systems. A builder that proceeds *without*
> understanding — natural selection, gradient descent, self-organization — is under no such
> constraint, and will produce entangled, distributed, holistic solutions wherever they are cheaper or
> fitter.

The argument is short. **Design is a homomorphism from the designer's understanding to the artifact:**
an engineer builds a radio or a CPU by composing modules she understands across interfaces she
specifies, so the artifact *inherits* a near-decomposable hierarchy. Decomposability is the trace of
the designer's bounded rationality — a designer who cannot hold the whole system in her head *must*
modularize to build at all (Simon 1962). Intelligibility and buildability-by-an-understander are the
same constraint seen twice. **Optimization carries no such guarantee:** evolution and stochastic
gradient descent search the space of behaviours, not of comprehensible mechanisms, and routinely
exploit dense, polysemantic, superposed solutions that pack more function into fewer parts precisely
by violating clean modularity. Superposition in neural networks (Elhage et al. 2022) is not an
anomaly; it is the expected signature of an understanding-free compressor.

This reframes the founding thought experiments and points past them. The microprocessor is the *easy*
case — a designed system is maximally intelligible — so the failure of neuroscience methods *even
there* is doubly damning. But it also means the brain is **not merely a harder chip**: built by
evolution, development, and learning (three understanding-free processes), it need not carry a clean
decomposition at all, and methods calibrated on engineered intelligibility will be systematically
over-optimistic about it. The correct null hypothesis for an evolved or trained system is *partial
holism*, not hidden modularity. Mechanistic interpretability inherits this exactly: a trained
transformer, built by SGD, is **biology-like, not CPU-like**; interpretability successes will cluster
on sub-tasks with incidental modularity pressure (induction heads, modular arithmetic, narrow
circuits) and stall on densely optimized capabilities — which is what we observe.

The principle is falsifiable. Holding behaviour fixed and varying only the *generator* — hand design,
evolutionary search, gradient descent with varying regularization and bottlenecks — the achievable
faithfulness `F` and the decomposability profile should be ordered by the structure-imprinting
pressure of the generator (design > regularized optimization > unconstrained optimization), and
`G_struct` should grow as construction becomes more understanding-free. This is directly runnable on
the §9 benchmark suite. It also yields an actionable corollary for AI: **interpretability is partly a
training-time decision** — modularity priors, bottlenecks, sparsity, and compositional curricula
imprint a fossil that post-hoc analysis can later read.

> **Box 3 — The Genesis Principle in one line.** *Intelligibility is a fossil of construction:*
> design imprints decomposability; optimization need not. Corollaries: (i) the microprocessor is the
> easy case; (ii) the right null model for brains and trained networks is partial holism; (iii)
> interpretability of trained nets is biology, not engineering; (iv) we can *choose* to imprint
> intelligibility at training time.

---

## 8. The reflexive turn: bounded understanders and the understanding horizon

The accounts above idealize the agent as an unbounded knower. Dropping that idealization — taking
seriously that the understander is itself a finite, complex system — adds structure that the framework
needs.

Ashby's Law of Requisite Variety, and the Conant–Ashby theorem that every good regulator of a system
contains a model of it (Conant & Ashby 1970), apply to the *understander*: to instantiate a system's
ι-machine, the agent's representational medium must have at least `C_ι` bits of effective variety.
Hence a **variety bound**: a bounded agent `A` with capacity `V(A)` can fully understand `S` only if
`V(A) ≥ C_ι(S)`; when `C_ι` exceeds `V(A)`, understanding is possible *only after coarse-graining `S`
to a level whose `C_ι` fits inside `V(A)`*. This re-derives §6 from the agent's side: **we build
hierarchies because we must**, and the levels we find are partly a projection of our own capacity —
which is why a child, an undergraduate, and an expert "understand" the same engine at different grains.

Two consequences follow. First, **understanding has a cost asymmetry**: prediction needs `C_μ`;
understanding needs `C_ι` *plus* the interventional sampling to pin it down (T1's corollary). For
systems with `C_ι ≫ C_μ`, understanding is categorically, not marginally, more expensive than
prediction — which is exactly why prediction races ahead and understanding lags. Second, there may be
an **understanding horizon**: systems understandable *in principle* (their ι-machine is well-defined)
but *understandable by no bounded agent* — `C_ι` exceeds any feasible `V(A)` *and* the ι-machine
admits no closed coarse-graining. For such systems no hierarchy rescues us; the best a bounded agent
can do is predict and demonstrate the irreducibility. We conjecture that whole brains and frontier
networks may lie partly beyond the horizon at the mechanistic level — not for mystical reasons but
because the only faithful model is as large and entangled as the system itself (Rosen 1985).

This reframes methodology. If `V(A)` and `𝓘` are the binding constraints, then **scientific
instruments are variety amplifiers**: the microscope, the oscilloscope, optogenetics, the
activation-patching harness extend the agent's effective capacity and intervention repertoire, raising
the T1 ceiling and refining the T3 resolution. The decisive advances in understanding complex systems
will therefore be *instrumental* (new ways to intervene at fine grain) more than *analytical* (new
ways to fit observational data). And when an automated system holds a faithful but human-ungraspable
ι-machine, "understanding it" for us becomes the concrete problem of computing the maximal
human-graspable quotient that remains intervention-closed — automated interpretability as *translation*
between levels.

---

## 9. Testing the framework: benchmarks with known ground truth

Because the object dimensions `{F, HC, MO, CC}` are defined against the *true* mechanism, they can be
measured on systems we built. We propose a benchmark suite (detailed in Part VII): radios and analog
circuits (the *repair* test); microprocessors (multi-level reverse-engineering); the Game of Life and
cellular automata (weak emergence, the right macro level); logic circuits and finite-state machines
(exact scoring); small transformers with known intended algorithms — modular addition, indirect-object
identification, induction heads, toy superposition (Nanda et al. 2023; Wang et al. 2023; Elhage et al.
2022); gene-regulatory and toy biological networks (the decomposability gradient); simple physical
simulations (scale separation and the renormalization group); and synthetic causal graphs (the pure
causal-discovery test).

Three design rules make a benchmark *separate prediction from understanding*: a **strong black-box
predictor control** (to exhibit the gap `G`), a **rich intervention algebra** (to score `CF`/`F`
against truth), and a **decomposability sweep** from modular to integrated (to locate where methods
break). The framework makes falsifiable predictions: correlational and representational methods will
score high `KA`, low `F`, and fail the first intervention/OOD test; interventionist methods will score
higher `F`, their advantage will *grow* with the number of interventions (T1 made visible), and it
will *collapse* as integration crosses a threshold (§6 made visible). The Genesis prediction (§7) adds
a generator sweep. If a purely observational method recovered the microprocessor's architecture, the
framework would be refuted.

---

## 10. Application: neuroscience and interpretability split the same way

Applying the `(KA, UO)` lens (Part VIII) yields a striking, domain-independent regularity: in **both**
fields the methods fall into two arms (Fig. 3).

- **A knowledge-about arm** (high `KA`, low `UO`, routinely over-read as understanding): fMRI
  localization, neural decoding, representational similarity analysis used alone, network-graph
  description, connectomics — and, in interpretability, linear probes, concept activation vectors,
  feature visualization, saliency/attribution, sparse autoencoders evaluated by reconstruction, and
  raw next-token or world-model fit. These recover correlations, representations, and descriptions —
  indispensable clues and substrates, but not mechanism.
- **An understanding arm** (high `UO`, distinguished by intervention/faithfulness/level): biophysical
  and normative models (Hodgkin–Huxley; efficient and predictive coding that *predicts* receptive
  fields); manifold and computation-through-dynamics accounts validated by perturbation; optogenetic-
  and lesion-validated mechanisms — and, in interpretability, activation patching, interchange
  interventions / causal abstraction / distributed alignment search (Geiger et al. 2021), ablation-
  validated circuits, specific-and-generalizing model edits, and causal representation learning.

The discriminator is invariant: the understanding arm supplies **interventionally validated,
faithfulness-bearing, level-appropriate** structure; the knowledge-about arm supplies fit and
decodability. Decoding is not usage; reconstruction is not causation; a region "lighting up" is not a
mechanism; a sparse feature is a hypothesis until an intervention confirms it is the unit the model
*uses*. Notably, the interpretability community's own *faithfulness-versus-plausibility* debate
(Jacovi & Goldberg 2020) is that field independently rediscovering the prediction-versus-understanding
distinction. Mechanistic interpretability, in our terms, *is* the project of moving learned systems
from predicting/modeling to reverse-engineering/mechanistic understanding — and the methods that
achieve it are precisely the interventional ones, against the Genesis-Principle headwind of §7.

---

## 11. Recommendations

1. **Name the cell.** For every result, state (i) the epistemic object recovered (regularity,
   representation, causal relation, mechanism, hierarchy, invariant) and (ii) the validation regime
   (fit/decoding vs. intervention/transfer). Most "we understand X" claims live in the top-left;
   saying so is the antidote.
2. **Make the battery interventional and out-of-distribution.** In-distribution prediction is
   near-zero evidence of understanding; counterfactual, interventional, failure-mode, novel-kind, and
   transfer questions are the discriminating — and hard to game — tests.
3. **Validate faithfulness causally, never by plausibility.** A human-convincing story is not a
   correct mechanism; require interchange-intervention or ablation agreement, ideally against ground
   truth.
4. **Report a decomposability profile.** Treat the discovery (or absence) of closed, modular levels as
   a measured output, not an assumption; expect — and accept — that some systems are genuinely
   integrated and resist part-wise mechanism.
5. **Build ground-truth benchmarks with predictor controls, and sweep the generator.** Only a benchmark
   that includes a strong predictor which *fails* the mechanism tests can demonstrate that a method
   recovers understanding rather than prediction; varying the construction process tests the Genesis
   Principle and tells us how to *build* intelligible systems.

---

## 12. Limitations and open problems

The framework is a proposal, and several of its load-bearing pieces are conjectural or unvalidated.
(i) The object dimensions require a *ground-truth* mechanism to score directly; on natural systems they
must be estimated, and good estimators of `F`, `CC`, and especially `C_ι` do not yet exist. (ii) The
aggregation of dimensions into scalar `KA`/`UO` indices is a modelling choice; the dimensions may admit
only a Pareto frontier, not a meaningful scalar. (iii) The variable- and level-choice problem is
upstream of everything: the framework scores understanding *relative to* a chosen variable set and
level, and choosing them well is itself part of understanding. (iv) The theorems T1–T3 are stated with
proof sketches under idealized assumptions (well-defined `𝓘`, access to interventional distributions);
fat-handed and confounded interventions complicate them in practice. (v) The Genesis Principle is
offered as a falsifiable principle and the understanding-horizon as a conjecture; neither has been
tested. (vi) Whether understanding is one concept or a family — and whether machine-held,
human-ungraspable mechanism counts as understanding — remains genuinely open (Part IX §5.4; twenty-five
open problems are catalogued in the companion `open_problems.md`). We regard these as an agenda, not a
retreat: each is stated so as to be attackable.

---

## 13. Conclusion

Jonas, Kording, and Lazebnik were not making a narrow methodological joke; they were pointing at a
permanent feature of inquiry into complex systems. **Prediction, compression, representation, and
correlation are genuine and necessary epistemic achievements — knowledge *about* a system — but they
are not understanding, and accumulating more of them does not, by itself, produce understanding.**
Understanding *of* a system is the recovery of its causal-mechanistic, hierarchical structure,
validated by intervention and manifested as the ability to predict the unseen, answer counterfactuals,
intervene, repair, redesign, transfer, and explain failure — at the right level, in a vocabulary of
composable parts, graspable by a bounded agent. The Understanding–Knowledge Gradient turns this
distinction into coordinates, three theorems, and measurable dimensions; the ι-machine turns the gap
into a quantity, `C_ι − C_μ`; the decomposability profile turns "discover the hierarchy" into a
reported result; the Genesis Principle explains why some systems yield to us and others do not; and the
`(KA, UO)` lens sorts the methods of neuroscience and interpretability into those that genuinely deepen
understanding and those that, however powerful, deepen only knowledge about. The discipline this
demands is modest but transformative: *say what you recovered, and how you validated it — and reserve
the word "understand" for the cases that earn it.*

---

## Display items

**Figure 1 | The modeling relation that must commute under intervention.** Two squares share the
system state `s` and model state `m = encode(s)`. *Top (prediction, rung 1):* applying the system's
spontaneous dynamics then encoding equals applying the model's dynamics then decoding — outputs match
under passive observation. *Bottom (understanding, rungs 2–3):* applying a world intervention
`do_S(ι)` then encoding equals applying the model intervention `do_M(ι)` then decoding — the diagram
commutes for every `ι ∈ 𝓘`. Prediction requires only the top square; understanding requires the
bottom. The size of the smallest model for which the bottom square commutes is the ι-machine; for the
top square alone it is the ε-machine.

**Figure 2 | The Understanding–Knowledge plane.** Axes: `KA` (knowledge-about) horizontal, `UO`
(understanding-of) vertical. The diagonal `UO = KA` marks balanced progress; the shaded **top-left**
region (high `KA`, low `UO`) is the Jonas–Kording/Lazebnik regime where prediction is over-read as
understanding. Arrows: adding data/compute moves a method *rightward only* (T1, T2); adding
interventions, environments, or inductive biases moves it *upward*. Example placements: linear
probe and fMRI decoding in the top-left; Hodgkin–Huxley and an interchange-validated circuit in the
upper-right; a raw next-token predictor far right at low `UO`. The vertical extent reachable by any
method is capped by the intervention algebra (T3).

**Figure 3 | Methods of neuroscience and interpretability split identically.** Two columns
(neuroscience; interpretability), each sorted top-to-bottom by `UO`. The knowledge-about arm (fMRI
localization, decoding, RSA-alone, network description, connectomics | probes, CAVs, feature
visualization, saliency, reconstruction-scored SAEs) clusters at low `UO`; the understanding arm
(biophysical/normative models, perturbation-validated dynamics, optogenetic/lesion-validated mechanism
| activation patching, interchange interventions/causal abstraction, ablation-validated circuits,
model editing, CRL) clusters at high `UO`. The dividing line is the same in both fields: presence of
interventional validation, faithfulness, and an appropriate level.

**Table 1 | The dimensions of understanding** (full definitions in Part VI; comparison tables in
`tables/`).

| Dim | Name | What it measures | Arm | Gates `UO`? |
|----|------|------------------|-----|-------------|
| `P` | Predictive power | OOD-weighted forecast accuracy | KA | no |
| `K` | Compression | MDL in a vocabulary of composable parts | both | no |
| `CF` | Counterfactual competence | commuting-diagram score over `𝓘` | UO | **yes** |
| `IV` | Intervention capability | optimal action / control success | UO | no |
| `F` | Mechanistic faithfulness | model parts ↔ system parts (interchange) | UO | **yes** |
| `HC` | Hierarchical consistency | closed, commuting levels exist | UO | no |
| `MO` | Modularity | thin, stable, intervention-local interfaces | UO | no |
| `T` | Transferability | reuse across related systems | UO | no |
| `R` | Robustness | explains failure modes and own stability | UO | no |
| `Δ` | Depth | range of invariance + computational *why* | UO | no |
| `X` | Intelligibility | bounded agent can reproduce the mechanism | UO | no |
| `CC` | Causal completeness | no unexplained interventional variance | UO | **yes** |

`KA = aggregate{P, K, descriptive coverage}`; `UO = gated mean{CF, IV, F, HC, MO, T, R, Δ, X, CC}`,
with `UO → 0` when `F` or `CF → 0`. Gap `G = KA − UO`; structurally, `G_struct = C_ι − C_μ`.

---

## Methods / data availability / competing interests

*Nature of the work.* This is a theoretical Perspective; it reports no new empirical data. The
benchmark suite of §9 and Part VII is a proposed protocol, not an executed study; the theorems T1–T3
are stated with proof sketches in Part IX and are intended as targets for formal proof. *Data and
materials availability.* All supporting documents — the full literature review (Parts I–III), the
notion survey, the criteria analysis (Part IV), the hierarchy treatment (Part V), the formal framework
(Part VI), the benchmark designs (Part VII), the application (Part VIII), the deep theory (Part IX),
the comparison tables, the open-problems catalogue, and the bibliography — are available in the
companion repository. *Competing interests.* The author(s) declare no competing interests. *Author
contributions.* Conceptualization, formal framework, and writing: as listed in the repository metadata.
*Acknowledgements.* This work synthesizes a large prior literature; seminal sources are credited in
`references.md`, which should be consulted for exact editions and page numbers before formal
submission.
