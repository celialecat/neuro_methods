# Part III — A Taxonomy of Epistemic Goals: Separating Understanding from Its Neighbors

The Jonas–Kording/Lazebnik worry is, at bottom, that we routinely **mistake the achievement of one
epistemic goal for the achievement of another** — specifically, mistaking prediction/description/
correlation for understanding. This Part builds a taxonomy of the goals a scientific method can
pursue and, for each, states:

- **What information is obtained** (the epistemic object recovered);
- **What information is lost / not obtained**;
- **Whether genuine understanding is achieved** (using Part II's verdict scale);
- **Necessary assumptions** for the goal to be met;
- **Failure cases** (where the method misleads).

The goals are ordered roughly along an **epistemic gradient** from "knowledge *about*" toward
"understanding *of*." The boundary we draw — the *understanding line* — falls between **Description/
Correlation/Prediction/Representation** (knowledge about) and **Explanation/Mechanistic
understanding** (understanding of), with **Simulation/Control/Intervention/Reverse-engineering/Theory-
building** straddling or spanning the line depending on *how* they are done.

> **Key organizing claim.** The position of a *method* on this gradient is not fixed by its
> output format but by **the epistemic object it actually recovers and validates**. A regression is
> "mere prediction" if validated only by fit, but can contribute to mechanistic understanding if its
> coefficients are interventionally validated and mapped to parts (3M). Hence each category below is
> a *goal/validation regime*, not a fixed list of techniques.

---

## A. Prediction

- **Goal.** Forecast future/unseen values or responses.
- **Information obtained.** A mapping inputs/history → outputs minimizing predictive error; the
  **statistical/predictive sufficient structure** (ideally an ε-machine-like sufficient statistic).
- **Information lost.** Asymmetry and direction of dependence; causal/interventional structure;
  *why*; the distinction between difference-makers and mere correlates; behavior off the training
  distribution and under intervention.
- **Understanding achieved?** *Generally no* (knowledge about). In-distribution prediction is the
  weakest evidence; **OOD/post-intervention** prediction is strong evidence but only because it
  smuggles in counterfactual/causal competence.
- **Necessary assumptions.** Stationarity / i.i.d. or known shift; the future resembles the past;
  the chosen feature space is predictively sufficient.
- **Failure cases.** Confounded prediction (barometer→storm); shortcut learning / spurious
  correlations (Clever-Hans, background-texture classifiers); distribution shift; predicting effects
  from effects. *Canonical:* a model that predicts a microprocessor's outputs perfectly while
  affording no account of its logic.

## B. Classification

- **Goal.** Assign instances to categories.
- **Information obtained.** Decision boundaries; **discriminative structure** (which features
  separate classes).
- **Information lost.** Generative/causal structure; *why* an instance is in a class; whether the
  separating features are causal or spurious; within-class mechanism.
- **Understanding achieved?** *No* (a focused form of prediction). Classifies without explaining.
- **Necessary assumptions.** Class definitions are valid; features carry class information; stable
  class-conditional distributions.
- **Failure cases.** Spurious/biased features (skin-tone, hospital-tag artifacts in medical imaging);
  label leakage; brittle boundaries; "taxonomy without theory."

## C. Compression

- **Goal.** Represent the data with fewer bits.
- **Information obtained.** A short code = a captured **regularity / minimal description** (MDL's
  model part = "structure," residual = "noise"); evidence that *some* structure exists.
- **Information lost.** Whether the compression is **modular, causal, or mechanism-aligned**;
  *which* structure (multiple short codes, multiple realizers); the *meaning* of the code.
- **Understanding achieved?** *Necessary, not sufficient.* Compression is the footprint of structure
  but can be opaque or merely predictive.
- **Necessary assumptions.** The chosen code class can express the system's regularities; the
  regularities are stationary.
- **Failure cases.** Opaque maximal compression (an incompressible-looking but actually structured
  cipher; a giant fitted polynomial); compressing *data* artifacts rather than *phenomena*
  (Bogen–Woodward); over-compression that discards causally-relevant-but-predictively-redundant
  variables (IB).

## D. Representation

- **Goal.** Learn/extract features or embeddings that make data tractable for downstream tasks.
- **Information obtained.** A geometry of the data; **task-useful features**; possibly disentangled
  factors of variation.
- **Information lost.** Whether features are **causal, used by the system, identifiable, or
  generative**; the mapping from features to mechanism. Decodability ≠ usage.
- **Understanding achieved?** *No by itself* (knowledge about the representation/geometry). Becomes
  a *component* of understanding only when features are shown to be **causal/used** (intervention)
  and **composable** into a mechanism.
- **Necessary assumptions.** The representation objective (reconstruction, prediction,
  contrastive) aligns with the structure of interest; identifiability conditions hold (often they
  don't — Locatello et al.).
- **Failure cases.** Polysemantic/superposed features mistaken for concepts; SAE features that are
  reconstruction artifacts; probes reading out information the system doesn't use; representational
  geometry matches (RSA) with different underlying mechanisms.

## E. Visualization

- **Goal.** Render structure perceptible to a human (dimensionality reduction, attention maps,
  feature visualizations, graphs).
- **Information obtained.** A human-consumable **projection/summary**; hypotheses and salient
  patterns.
- **Information lost.** Faithfulness (projections distort: t-SNE/UMAP do **not** preserve global
  geometry or densities reliably); causality; quantitative relations; everything off the chosen
  axes.
- **Understanding achieved?** *No* — visualization is a **hypothesis-generation and communication**
  aid, frequently mistaken for evidence. Feeling of insight ≠ understanding (IOED risk).
- **Necessary assumptions.** The projection preserves the features of interest; the eye is reading
  signal not artifact.
- **Failure cases.** Over-interpreting t-SNE cluster shapes/sizes/distances; saliency maps that pass
  visual muster but fail sanity checks (Adebayo et al.); "neuron X looks like a curve detector" without
  causal validation.

## F. Correlation / Association

- **Goal.** Quantify statistical dependence (correlation, mutual information, functional
  connectivity, regression coefficients).
- **Information obtained.** **Rung-1 (associational) structure**; that variables co-vary and how
  strongly; candidate relationships.
- **Information lost.** Direction; confounding vs. causation; mechanism; behavior under intervention.
- **Understanding achieved?** *No.* The paradigm of "knowledge about." (Pearl rung 1.)
- **Necessary assumptions.** Often *none beyond measurement* — which is exactly why correlations are
  cheap and seductive; for *causal reading*, strong unverified assumptions (no confounding).
- **Failure cases.** Confounding, reverse causation, selection bias, nonsense correlations,
  functional-connectivity artifacts, "the correlation menagerie" of high-dimensional neuroscience and
  genomics. *The single most over-claimed category.*

## G. Description

- **Goal.** Characterize *what* the system does/contains (taxonomies, phenomenology, parts lists,
  connectomes, statistics of behavior).
- **Information obtained.** Catalog of **phenomena, components, and regularities** (Bogen–Woodward
  phenomena if done well); the explanandum, precisely stated.
- **Information lost.** *Why* and *how* (the explanans); organization and dynamics linking parts;
  causal roles.
- **Understanding achieved?** *No, but it is the indispensable substrate* — you cannot explain what
  you have not described. Description defines targets for explanation.
- **Necessary assumptions.** The description carves the system at meaningful joints (right variables/
  categories — itself nontrivial).
- **Failure cases.** Mistaking a complete description for an explanation — the **connectome fallacy**
  (full wiring of *C. elegans* ≠ understanding of behavior); "stamp-collecting"; mislabeled
  categories that fossilize wrong variables.

--- **(the understanding line — below: understanding of)** ---

## H. Explanation

- **Goal.** Answer why/how questions about phenomena.
- **Information obtained.** Depending on the explanatory mode: laws (Hempel), **difference-making
  causal structure** (Salmon/Woodward/Strevens), **unifying patterns** (Kitcher), or **mechanisms**
  (Craver). On the good (causal/mechanistic) accounts: the **asymmetric, relevant, intervention-
  supporting** structure that produces the phenomenon.
- **Information lost.** Possibly fine-grained dynamics/implementation (if the explanation is
  abstract) — by design (Strevens); possibly the *other levels*.
- **Understanding achieved?** *Yes — constitutively,* when the explanation is **correct and grasped**
  (de Regt). This is the category that *defines* the understanding side.
- **Necessary assumptions.** The explanatory relations are real (realism about the posited structure
  at the chosen level); the right contrast class/variables (van Fraassen, variable-choice).
- **Failure cases.** **How-possibly mistaken for how-actually** (a plausible story that isn't the
  real mechanism); explanatorily irrelevant detail; unification that violates causal asymmetry;
  *just-so stories*.

## I. Mechanistic understanding

- **Goal.** Identify the actual entities, activities, and organization that produce the phenomenon,
  validated by intervention and mapped across levels.
- **Information obtained.** A **how-actually mechanism**: parts + operations + organization, with
  **constitutive relevance** established by mutual manipulability, and (ideally) a **multi-level**
  account (Marr). Subsumes intervention + counterfactual + decomposition + (often) hierarchy.
- **Information lost.** Little *at its level* if complete; may still abstract away lower-level
  implementation detail (legitimately) and may not deliver the *computational-level why* unless
  paired with a normative theory.
- **Understanding achieved?** *Yes — the target of this project.* The richest form, especially when
  it spans levels and answers *why* as well as *how*.
- **Necessary assumptions.** The system is (at least approximately) **decomposable/localizable** at
  the chosen level, or its non-decomposability is itself characterized; interventions are
  well-defined and clean; the right variables/level have been found.
- **Failure cases.** **Mislocalization** in non-decomposable systems (Lazebnik); **fat-handed /
  off-target interventions** that create artifacts; mistaking a **sketch** (with black boxes) for a
  complete mechanism; superposition/synergy defeating part-localization; recovering a mechanism that
  is faithful at one level but wrong about *why* (no computational-level account).

## J. Simulation

- **Goal.** Reproduce the system's behavior by executing a model.
- **Information obtained.** A **generative/dynamical model** that, if faithful, supports prediction,
  what-if exploration, and (if causal) intervention.
- **Information lost.** *If the simulation is a black-box fit:* difference-makers, minimality,
  transparency (an opaque sim is as hard to understand as the system — weak emergence). *If
  causal/mechanistic:* possibly nothing at its level.
- **Understanding achieved?** *Spans the line.* A **mechanism-faithful, abstracted, runnable** model
  = understanding (notion 3 done right, Rosen-commuting). A **tuned data-replicating** sim = knowledge
  about (predicts without illuminating).
- **Necessary assumptions.** The model's transitions correspond to the system's causal transitions
  (Rosen commuting), not merely its outputs; the modeled factors are sufficient *and* are
  difference-makers.
- **Failure cases.** "Right for the wrong reasons" (overfit/over-parameterized sims); 1:1 maps;
  simulations validated only on the data they were tuned to.

## K. Control

- **Goal.** Drive the system to desired states / keep essential variables in bounds.
- **Information obtained.** A **policy/regulator**; effective intervention knowledge; and — by the
  **Good Regulator Theorem** — implicitly a **model** of the system (every good regulator is a model
  of the system).
- **Information lost.** Control can be achieved by **model-free** policies (RL, PID tuning) that
  encode *no explicit, inspectable mechanism*; the *why* and the decomposition may be absent.
- **Understanding achieved?** *Spans the line.* **Model-based, robust, transferable** control is
  strong evidence of understanding; **model-free, narrowly-tuned** control is knowledge-about
  (works without insight). Conant–Ashby gives a *conditional* bridge (optimal+simple control ⇒
  model), not an unconditional one.
- **Necessary assumptions.** Requisite variety (Ashby); for model-based control, an accurate
  forward/causal model; controllability of the relevant variables.
- **Failure cases.** Brittle controllers that fail under novel disturbances (had a correlational, not
  causal, model); reward-hacking; control that exploits a quirk rather than the intended mechanism.

## L. Intervention (experimental difference-making)

- **Goal.** Establish what changes what, by manipulating and observing.
- **Information obtained.** **Rung-2 causal structure**: intervention-supporting dependences;
  **constitutive relevance** (mutual manipulability) when interventions cross levels.
- **Information lost.** A *set* of interventional facts is not yet an *organized mechanism* or a
  *why*; effects may be measured without the mediating process; range of invariance may be untested.
- **Understanding achieved?** *Necessary and core, but partial.* Intervention is the chief
  *discriminator* of understanding from prediction; *organizing* interventional facts into a
  mechanism/hierarchy is the further step to full understanding.
- **Necessary assumptions.** Interventions are surgical (modular: change only the target),
  well-defined, and not fat-handed; effects are measured at the right level/timescale.
- **Failure cases.** Fat-handed/off-target interventions (lesions that damage passing fibers;
  knockouts with compensatory rewiring; ablations that shift the network off-distribution);
  context-dependent effects mistaken for stable mechanisms; over-generalizing from one background.

## M. Reverse engineering

- **Goal.** Recover the design/algorithm of an engineered (or evolved/trained) system from its
  structure and behavior.
- **Information obtained.** Ideally a **how-actually mechanism + computational-level account** (the
  algorithm and *what problem it solves*); the union of decomposition, causal validation, and
  abstraction. This is the *explicit* analogue of "understanding the microprocessor / the trained
  network."
- **Information lost.** For learned systems, possibly the *training-time rationale* vs. *inference-
  time mechanism*; non-decomposable/superposed parts resist recovery.
- **Understanding achieved?** *Yes when successful* — reverse engineering is essentially "achieve
  mechanistic + computational understanding of an artifact," and its **success criteria are exactly
  our criteria** (predict, intervene, repair, redesign, transfer). The Jonas–Kording and
  interpretability programs *are* reverse engineering.
- **Necessary assumptions.** Recoverable modular/compositional structure (or characterizable lack
  thereof); access to internals and to interventions.
- **Failure cases.** The microprocessor study (standard analyses fail to recover the architecture);
  superposition (no clean neuron→feature map); attributing human-legible algorithms to systems that
  implement something genuinely different (over-projecting our concepts).

## N. Theory building

- **Goal.** Construct a general, unifying account that explains many phenomena and predicts new
  kinds.
- **Information obtained.** **Unifying patterns / laws / generative principles** (Kitcher,
  structural realism); the *why* at the deepest level; novel-kind predictions; transferable invariants.
- **Information lost.** Local mechanistic/implementational detail (by abstraction); risk of
  empirical underdetermination.
- **Understanding achieved?** *Yes — the broadest/deepest form (breadth + depth),* when the theory is
  correct, intelligible, and empirically constrained. Complements mechanistic understanding (which is
  deep-but-local) with breadth.
- **Necessary assumptions.** The domain admits unification (shared structure across phenomena);
  empirical adequacy + the realist bet that the unifying structure is real.
- **Failure cases.** Over-unification / spurious analogy; elegant-but-false theories; unfalsifiable
  frameworks; mistaking mathematical for empirical adequacy.

---

## O. The taxonomy as a 2×N grid: epistemic object × validation regime

A compact way to see the **understanding line** is a grid whose rows are *epistemic objects* and
whose columns are *validation regimes*; understanding requires both the right object **and** the
right validation.

| Epistemic object recovered | Typical goals (above) | Validated by fit/decoding only → | Validated by intervention/transfer → |
|---|---|---|---|
| Statistical regularity / correlation | A,B,F,G | **Knowledge about** | (correlation can't be intervention-validated without becoming causal) |
| Predictive sufficient statistic | A,C,J(fit) | **Knowledge about** | OOD/post-intervention test ⇒ moves toward understanding |
| Representation / geometry | D,E | **Knowledge about** | feature-ablation/usage test ⇒ moves toward mechanism |
| Causal/interventional dependence | K,L | partial | **Understanding (rung 2/3)** |
| Mechanism (entities+activities+org) | I,J(mech),M | n/a (requires intervention to establish) | **Understanding (how-actually)** |
| Inter-level map / hierarchy | (Part V) | n/a | **Deepest understanding** |
| Unifying principle / invariant | N | partial (fit across data) | **Breadth understanding** (novel-kind prediction, transfer) |

**The diagnostic question for any study:** *(1) which row is the actual epistemic object, and (2)
which column is the actual validation?* Most "we understand X" claims in high-dimensional science
sit in the top-left (regularity/representation, validated by fit/decoding) while *talking* as if
they were bottom-right. Naming the cell is the antidote, and it is the discipline this entire
document tries to enforce.

---

## P. Summary: where each category sits relative to understanding

- **Knowledge *about* (do not, alone, yield understanding):** Prediction, Classification,
  Compression, Representation, Visualization, Correlation, Description. *They recover regularities,
  features, and phenomena — the substrate and the symptoms of structure, not the structure's
  causal/mechanistic identity.*
- **Understanding *of* (yield understanding when correct + grasped):** Explanation, Mechanistic
  understanding, Theory building. *They recover difference-making, organized, level-linked,
  unifying structure.*
- **Spanning (yield understanding only in their causal/mechanistic, intervention-validated,
  transferable form):** Simulation, Control, Intervention, Reverse engineering. *Their epistemic
  status is set by the validation regime, not the technique.*

This taxonomy is the conceptual map for Part IV (criteria), Part VI (measurable dimensions), and
Part VIII (classifying neuroscience/interpretability methods). The methods table
(`tables/methods_comparison.md`) assigns concrete techniques to these cells.
