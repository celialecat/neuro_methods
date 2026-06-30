# Part II — What Is Understanding? A Survey of Proposed Notions

This Part surveys every major proposed *notion* of understanding (each a candidate answer to
"what is it to understand X?"). For each we give: **definition**, **supporting literature**,
**strengths**, **limitations**, **example(s)**, and a verdict on **whether it captures *scientific*
understanding** — using a fixed rubric:

> **Verdict scale:** *Constitutive* (part of what understanding is) · *Necessary* (understanding
> requires it but it isn't enough) · *Sufficient* (having it guarantees understanding) ·
> *Symptom/Indicator* (reliably co-occurs but isn't constitutive) · *Neither* (neither necessary
> nor sufficient, though often valuable).

Throughout, recall the title distinction: a notion may characterize a fine *epistemic achievement*
(knowledge about a system) without amounting to *understanding of* it. The tag **[epistemic
object]** names what the notion's possessor has recovered.

The compact version of this survey is in `tables/notions_taxonomy.md`; this file is the prose.

---

## 1. Understanding as **prediction**

- **Definition.** To understand X is to be able to predict X's behavior (future states, responses
  to inputs) accurately. [epistemic object: a predictive input/state→output mapping; statistical
  regularity.]
- **Literature.** Hempel's structural identity of explanation and prediction (1965); instrumentalism
  / constructive empiricism (van Fraassen 1980); the predictive-processing view in neuroscience
  (Friston); in ML, generalization error as the dominant success metric.
- **Strengths.** Operational, measurable, falsifiable; prediction is a genuine and demanding
  achievement; out-of-distribution prediction is strong evidence of captured structure.
- **Limitations.** The barometer/flagpole cases: prediction can ride on correlation or effects of a
  common cause; **prediction is symmetric and non-causal**, understanding is asymmetric and causal.
  Pearl's ladder: rung-1 prediction cannot answer interventions/counterfactuals. The
  Jonas–Kording microprocessor and a memorizing lookup table can predict without understanding.
  Predictive success is *level-* and *distribution-bound* (Cartwright's nomological machines).
- **Example.** A deep net predicting protein structure or next tokens superbly while affording no
  account of *why*; Ptolemaic epicycles predicting planetary positions with no correct mechanism.
- **Verdict.** *Necessary but not sufficient.* In-distribution prediction is weak evidence;
  **out-of-distribution / post-intervention** prediction is strong evidence — but the latter
  already imports counterfactual/interventional competence (notion 8), which is where understanding
  actually lives. The single most important thing the framework must *not* conflate with
  understanding.

## 2. Understanding as **compression**

- **Definition.** To understand X is to possess a description of X much shorter than X itself that
  regenerates/predicts it — to have found the regularity that compresses the data. [epistemic
  object: a short generative code / minimal sufficient statistic.]
- **Literature.** Kolmogorov/Solomonoff/Chaitin (AIT); Rissanen (MDL); Kitcher (unification as
  compression of derivations); Simon (hierarchy as short description); "understanding as compression"
  in ML folklore (and the Hutter Prize).
- **Strengths.** Quantitative and general; captures the link between *finding structure* and
  *shortening description*; explains the value of laws and unification; rules out lookup-table
  "understanding" (no compression = no captured regularity).
- **Limitations.** (i) Shortest codes can be **opaque/non-modular** (no recoverable parts);
  (ii) **predictive** compression (IB, ε-machine) need not be **causal/mechanistic**; (iii)
  **multiple realizability** — same compressed description, different mechanisms; (iv) K is
  uncomputable. Compression tracks *structure* but not necessarily *the system's own causal
  structure*.
- **Example.** A 6-parameter chaotic map reproducing a complex time series (compression that *is*
  illuminating) vs. a tuned 50-term Fourier series fitting the same series (compression that
  isn't). The contrast shows compression alone doesn't settle understanding.
- **Verdict.** *Necessary but not sufficient.* Understanding requires *mechanism-structured*
  compression (short description in a vocabulary of interventionally meaningful, composable parts),
  not compression per se.

## 3. Understanding as **simulation** (runnable models / mental models)

- **Definition.** To understand X is to possess a *runnable* model that, when executed, reproduces
  X's behavior — to be able to "run the system in your head/computer." [epistemic object: a
  generative simulator.]
- **Literature.** Craik (1943) and Johnson-Laird (mental models); Rosen's anticipatory systems;
  world models in ML (Ha & Schmidhuber); agent-based and multiscale simulation.
- **Strengths.** Captures the felt sense of "I can see how it works"; supports prediction *and*
  what-if exploration; integrates dynamics that static descriptions miss.
- **Limitations.** A faithful simulation can be **as opaque as the system** (Borges' 1:1 map; a
  detailed biophysical sim you can run but not comprehend) — *weak emergence* (Bedau): derivable by
  simulation yet not transparently understood. Simulation establishes *sufficiency of the modeled
  factors* but not *which are difference-makers* (Strevens) nor the *minimal* mechanism. A
  simulation can be right for the wrong reasons (fit by tuning).
- **Example.** A whole-cell or detailed cortical-column simulation that reproduces data but whose
  behavior is no more intelligible than the original; vs. a *reduced* model whose few variables you
  can reason about.
- **Verdict.** *Necessary-ish, not sufficient.* Runnability + faithfulness is strong, but
  understanding additionally requires **abstraction to difference-makers** and **decomposition**.
  Rosen's caveat: the simulation must *commute* with the system's causation, not merely match
  output.

## 4. Understanding as **explanation**

- **Definition.** To understand X is to have an explanation of X — an answer to why/how X is or
  behaves as it does. [epistemic object: depends on the theory of explanation — laws (Hempel),
  causes (Salmon/Woodward), unifying patterns (Kitcher), mechanisms (Craver).]
- **Literature.** The entire Part I §1; de Regt (understanding as the goal explanation serves);
  Lipton (loveliness/IBE); Khalifa (2017, *Understanding, Explanation, and Scientific Knowledge* —
  understanding is grasping a correct explanation).
- **Strengths.** Directly connects to the most developed normative theory we have; explanation is
  asymmetric, relevant, and (on good theories) causal/mechanistic — exactly the features prediction
  lacks.
- **Limitations.** "Explanation" inherits all disputes about *what* an explanation is; **possessing**
  an explanation (having a text) differs from **grasping** it (de Regt's intelligibility; the
  illusion-of-explanatory-depth gap); explanations can be how-possibly rather than how-actually.
- **Example.** Hodgkin–Huxley *explains* the action potential (mechanism); epicycles *predict* but
  don't explain planetary motion.
- **Verdict.** *Constitutive* — on essentially all accounts, understanding just is grasping a
  *correct, deep* explanation. The work is then in saying *which* explanations (we argue:
  mechanistic + interventionist + hierarchical) and what "grasp" requires (competences).

## 5. Understanding as **intervention / manipulation**

- **Definition.** To understand X is to know how X would respond to interventions — to be able to
  *change* X in predictable ways by manipulating its parts/variables. [epistemic object:
  intervention-supporting dependences; rung-2 of Pearl's ladder.]
- **Literature.** Woodward (2003) interventionism; Pearl (do-calculus); Craver (mutual
  manipulability); Ashby/Conant (regulation); experimental method generally ("to understand is to
  be able to make").
- **Strengths.** Asymmetric and causal by construction; operational (do an intervention, check the
  prediction); graded (range of invariance = depth); the basis of activation patching and of
  experimental biology.
- **Limitations.** Requires well-defined interventions (problematic for entangled/superposed
  variables, fat-handed interventions); knowing *that* X→Y under intervention is *local* causal
  knowledge, not yet the *organized whole* (a list of pairwise effects isn't a mechanism); says
  little about *why* the dependence holds.
- **Example.** Optogenetic/lesion studies establishing a brain region's causal role; ablating an
  induction head and confirming the predicted loss of in-context learning.
- **Verdict.** *Necessary (core).* Intervention competence is one of the most reliable
  discriminators of understanding-from-prediction, but a *set* of interventional facts must be
  *organized into a mechanism/hierarchy* to constitute understanding.

## 6. Understanding as **abstraction**

- **Definition.** To understand X is to represent X at the right level of abstraction — to isolate
  the features that matter and discard the rest. [epistemic object: a minimal sufficient,
  difference-making description.]
- **Literature.** Strevens (kairetic abstraction over difference-makers); RG/effective theories
  (relevant variables); causal abstraction (Rubenstein, Beckers & Halpern); Marr's computational
  level.
- **Strengths.** Explains why *idealized* models explain *better* (they isolate difference-makers);
  ties understanding to the *autonomy* of the right-level description; connects to compression done
  right.
- **Limitations.** Choosing the abstraction is the hard part (variable-choice problem); wrong
  abstractions mislead; abstraction without causal grounding is mere coarse description.
- **Example.** Thermodynamics as an abstraction of statistical mechanics; treating a transistor as a
  switch (the right abstraction for the microprocessor's logic) vs. modeling its full device
  physics.
- **Verdict.** *Constitutive* of understanding's *form* (understanding is always at *a* level), and
  *necessary* — but the abstraction must be **causally/mechanistically faithful** (a commuting
  coarse-graining), else it is description, not understanding.

## 7. Understanding as **decomposition** (mechanistic decomposition / modularity)

- **Definition.** To understand X is to decompose it into component parts/operations and their
  organization, such that the whole's behavior arises from the parts' coordinated activities.
  [epistemic object: entities + activities + organization — a mechanism.]
- **Literature.** Simon (near-decomposability); Bechtel & Richardson (decomposition & localization);
  MDC/Craver (mechanisms); Pearl (modular SCMs / autonomous equations).
- **Strengths.** This is the working method of biology, engineering, and circuits-style
  interpretability; supports localized repair/redesign; aligns with how complex systems are *built*
  and *evolved* (Simon). Decomposition + localization is the engine of mechanistic discovery.
- **Limitations.** **Fails for non-decomposable/holistic systems** (high Φ; synergistic PID; deeply
  recurrent/distributed computation; superposition) — exactly Lazebnik's worry. A decomposition can
  be *wrong* (mislocalization), and a *correct* decomposition still needs the *activities/dynamics*
  to explain behavior (a parts list ≠ a mechanism; cf. the connectome).
- **Example.** Decomposing a radio into amplifier/oscillator/filter stages (works) vs. trying to
  localize "in-context learning" to a single neuron (fails — it's a distributed circuit).
- **Verdict.** *Constitutive when the system is near-decomposable; otherwise the central
  difficulty.* Whether understanding *requires* decomposition is the topic of Part V; our answer:
  it requires discovering *whatever* decomposable/closed structure exists, and quantifying when
  none does.

## 8. Understanding as **counterfactual competence**

- **Definition.** To understand X is to be able to answer a wide range of counterfactual ("what if
  things had been different") questions about X correctly. [epistemic object: rung-3 of Pearl's
  ladder — structural counterfactuals.]
- **Literature.** Woodward (w-questions); Pearl (structural counterfactuals; abduction-action-
  prediction); Lewis (counterfactual dependence); Lipton (contrastive explanation).
- **Strengths.** Possibly the *single best operational proxy* for understanding: it subsumes
  prediction (special case), requires causal structure, and is gradable by the *range* of
  counterfactuals handled (= depth). Hard to fake by memorization.
- **Limitations.** Requires a model to *generate* the counterfactuals (you can't read them off data
  — Pearl); evaluating counterfactuals needs ground truth or interventions; "wide range" must be
  specified to avoid trivialization.
- **Example.** "Had this resistor's value doubled, the output frequency would halve" (radio
  understood); "had we ablated these 3 heads, IOI accuracy would drop to chance" (circuit
  understood).
- **Verdict.** *Necessary and nearly criterial.* Counterfactual competence over a broad,
  systematically-generated question set is, in our framework, one of the strongest *measurable*
  signatures of understanding (Part VI's *counterfactual competence* dimension).

## 9. Understanding as **causal structure**

- **Definition.** To understand X is to know its causal structure — the graph of
  cause→effect/structural equations generating X's variables. [epistemic object: an SCM / causal
  DAG with mechanisms.]
- **Literature.** Pearl (SCMs); Woodward; Spirtes-Glymour-Scheines (discovery); Salmon
  (causal-mechanical).
- **Strengths.** Subsumes intervention and counterfactual competence (an SCM answers all three
  rungs); the formally cleanest object; modular and transferable.
- **Limitations.** Causal structure is **underdetermined by observational data** (needs
  interventions/assumptions); the **variable-choice problem** (an SCM presupposes the right
  variables — itself a representation/abstraction problem); a causal graph may omit the *why*
  (computational-level rationale) and the *dynamics*.
- **Example.** A validated gene-regulatory SCM enabling predicted knockouts; a transformer's
  computational graph with causally-verified edges (path patching).
- **Verdict.** *Constitutive/core* of the *how* of understanding. Necessary; sufficient *for
  mechanistic* understanding *at a level* once paired with the right variables and validated by
  intervention — but a causal graph plus a *why* (notion 4/computational level) is the fuller good.

## 10. Understanding as **generative modeling**

- **Definition.** To understand X is to possess a generative model from which X's data could have
  been produced — to know the data-generating process. [epistemic object: a generative
  distribution/process, ideally the *true* one.]
- **Literature.** Bayesian generative modeling; the "analysis by synthesis"/Helmholtz tradition;
  probabilistic programs; world models.
- **Strengths.** If the generative model is the *true mechanism*, this is understanding; supports
  simulation, prediction, and (if causal) intervention; natural home for hierarchy (hierarchical
  generative models).
- **Limitations.** Many generative models fit the data equally well (**likelihood-equivalence /
  underdetermination**); a good generative *fit* ≠ the *true* generative *process* (a GAN
  generates faces without the biology of faces). Generative ≠ causal unless interventions
  constrain it.
- **Example.** A correct forward model of image formation (graphics) used for vision-as-inverse-
  graphics (understanding) vs. a black-box generator (knowledge about the distribution).
- **Verdict.** *Necessary for the "synthesis" sense; sufficient only if the generative process is
  the true causal mechanism.* Generativeness alone is knowledge about the distribution.

## 11. Understanding as **transfer / generalization**

- **Definition.** To understand X is to be able to carry one's account of X to new situations,
  systems, or regimes — generalization across distributions and transfer across domains. [epistemic
  object: invariant/portable structure.]
- **Literature.** Woodward/Hitchcock (depth = range of invariance); ICP/IRM (invariance across
  environments); analogy and unification (Kitcher); transfer learning; cognitive science on
  explanation-driven generalization (Lombrozo).
- **Strengths.** Operational and demanding; **invariance across environments is a hallmark of
  causal/mechanistic** (vs. spurious) structure (ICP); transferability is exactly what a fitted
  correlation lacks.
- **Limitations.** Generalization *within* a distribution can be achieved by non-understanding
  (interpolation); must specify *which* shifts/transfers count; broad transfer may reflect a
  shallow analogy rather than shared mechanism.
- **Example.** Understanding of the harmonic oscillator transferring across pendulum/circuit/molecule
  (deep, shared mechanism); a model failing under distribution shift reveals it had correlation, not
  mechanism.
- **Verdict.** *Necessary/indicator (strong).* Robust **out-of-distribution and cross-system
  transfer** is among the best behavioral signatures of understanding; it operationalizes depth and
  breadth (Part VI).

## 12. Understanding as **counterfactual repair**

- **Definition.** To understand X is to be able to *fix* X when it is broken — to diagnose a fault
  and restore function. [epistemic object: a mechanism *plus* the diagnostic mapping from
  symptoms→faults→corrective interventions.]
- **Literature.** Lazebnik (2002, "Could a Biologist Fix a Radio?" — repair as the test of
  understanding); engineering diagnosis/troubleshooting; medicine; fault localization in software.
- **Strengths.** A stringent, *practical* test: repair requires localizing the fault (decomposition),
  knowing the normal mechanism (counterfactual: what it *should* do), and intervening correctly. Hard
  to fake.
- **Limitations.** Repair can sometimes be done by **part-swapping without understanding** (replace
  the broken board) — module replacement exploits *modularity* without full mechanistic insight;
  conversely, deep understanding may not enable repair if no intervention is feasible.
- **Example.** Lazebnik's radio: a real engineer fixes it because they understand the
  amplifier/oscillator mechanism; a "biologist" applying correlational methods cannot.
- **Verdict.** *Sufficient-leaning indicator* (reliable, demanding), *not strictly necessary*
  (understanding can outrun repairability; repair can sometimes be modular trial-and-error). One of
  the best *practical* benchmarks (Parts IV, VII).

## 13. Understanding as **(re)design**

- **Definition.** To understand X is to be able to design a system that realizes X's
  behavior/function — "what I cannot create, I do not understand" (Feynman). [epistemic object: a
  constructive/generative recipe sufficient to *build* the function.]
- **Literature.** Feynman's blackboard dictum; Simon's *Sciences of the Artificial* (the synthetic
  stance); synthetic biology ("build to understand"); engineering.
- **Strengths.** The most demanding constructive test; design forces explicit, sufficient,
  composable mechanism; supports redesign/variation (a stronger form of counterfactual competence).
- **Limitations.** One can build a system that *works* by tuning/evolution without understanding
  *why* it works (evolved/learned artifacts; "we built it but can't explain it" — exactly trained
  nets!); design success shows *sufficiency of a* mechanism, not identification of *the actual*
  mechanism of a *given* natural system.
- **Example.** Designing a working oscillator from theory (understanding) vs. evolving a circuit
  that oscillates by selection without insight (Thompson's evolved FPGA — works, not understood).
- **Verdict.** *Sufficient-leaning indicator for "understanding a function"; not sufficient for
  "understanding this particular system,"* because design demonstrates *a* mechanism, not *the*
  mechanism. Strong benchmark, with the build-without-understanding caveat.

## 14. Understanding as **modularity (discovering latent modules)**

- **Definition.** To understand X is to discover its modular organization — near-decomposable
  subsystems with sparse, well-characterized interfaces. [epistemic object: a module decomposition +
  interfaces.]
- **Literature.** Simon (ND); network modularity (Newman); modularity in biology (Hartwell et al.
  1999, "From molecular to modular cell biology"); circuits/SAEs (modular features).
- **Strengths.** Modularity licenses local understanding, independent study, repair, and transfer;
  it is the structural enabler of all decomposition-based method.
- **Limitations.** Modules may be **approximate, overlapping, context-dependent, or absent**;
  imposing modularity where there is none misleads (false localization); module *boundaries* and
  *interfaces* can be the hard part.
- **Example.** Operons/regulatory modules in gene networks; attention-head "circuits" as modules.
- **Verdict.** *Constitutive of the structure that makes understanding tractable* (see Part V);
  *necessary when present, but its presence is a fact about the system, not a guarantee.*

## 15. Understanding as **robustness explanation**

- **Definition.** To understand X is to explain why X is robust (or fragile) — why function persists
  under perturbations, noise, and component variation. [epistemic object: the stabilizing
  mechanisms (feedback, redundancy, degeneracy, canalization, attractor structure).]
- **Literature.** Ashby (ultrastability, homeostasis); Kitano (biological robustness 2004);
  control theory; Wagner (robustness & evolvability); attractor dynamics.
- **Strengths.** Robustness is a *system-level* property that demands understanding of *organization*
  (feedback loops, redundancy), not just parts; explains why localization can fail (degeneracy) and
  why systems tolerate damage.
- **Limitations.** A specialized facet; necessary for understanding *robust* systems specifically,
  not a general theory of understanding.
- **Example.** Explaining bacterial chemotaxis's robust perfect adaptation via integral feedback
  (Barkai-Leibler, Yi et al.) — deep understanding of *why* it's robust.
- **Verdict.** *Constitutive for robust/biological systems; a key dimension (robustness) in Part VI*,
  not a stand-alone definition of understanding.

## 16. Understanding as **invariance**

- **Definition.** To understand X is to identify what stays invariant — the conserved quantities,
  symmetries, and relationships that hold across changes. [epistemic object: invariants/symmetries.]
- **Literature.** Noether (symmetry↔conservation); Woodward (invariant relations as the locus of
  explanation); ICP (invariance across environments); structural realism (invariant structure is
  what's real/preserved).
- **Strengths.** Invariants are the deepest, most transferable knowledge in physics; invariance
  under intervention/environment is the signature of causal/mechanistic (vs. spurious) structure.
- **Limitations.** Finding the right invariants is hard and theory-laden; invariance is a *property
  of* the explanatory relations, not by itself a full mechanism or a *why*.
- **Example.** Conservation laws explaining/constraining dynamics; invariant predictors marking the
  causal feature set (ICP).
- **Verdict.** *Constitutive/necessary* — invariance (range thereof = depth) is built into the
  interventionist core and is one of our measurable signatures, but it characterizes the *relations*
  understanding tracks rather than exhausting understanding.

## 17. Understanding as **compositionality**

- **Definition.** To understand X is to grasp how X is built by composing parts/operations according
  to combination rules, such that the meaning/behavior of the whole is a function of the parts and
  their mode of combination. [epistemic object: a compositional grammar/algebra of mechanism.]
- **Literature.** Frege (compositionality of meaning); programming-language semantics; systematicity
  (Fodor & Pylyshyn); compositional generalization in ML; category-theoretic accounts of systems
  (compositionality of mechanisms).
- **Strengths.** Compositionality is what makes understanding *scalable* (understand parts + rules ⇒
  understand exponentially many wholes); supports systematic counterfactuals and transfer; the basis
  of how we understand engineered systems.
- **Limitations.** Many systems are **non-compositional/holistic** (interaction effects, synergy,
  context-dependence — superposition, PID-synergy); imposing compositionality where absent fails.
- **Example.** Understanding a CPU's behavior by composing gate/instruction semantics; understanding
  a sentence by composing word meanings.
- **Verdict.** *Constitutive of scalable understanding* (closely tied to modularity/hierarchy); a key
  dimension (it underwrites breadth/transfer); its applicability is a system-dependent fact.

## 18. Understanding as **generalization** (across regimes/scales)

(Overlaps with 11; here the emphasis is *scale/regime* generalization rather than domain transfer.)
- **Definition.** To understand X is for one's account to remain correct across the regimes/scales in
  which X operates (limits, asymptotics, phase changes). [epistemic object: a multi-regime-valid
  theory.]
- **Literature.** RG/universality; asymptotic analysis; effective theories; cross-scale validity.
- **Verdict.** *Necessary/indicator*; relatedly *breadth* in Part VI. Same caveats as 11.

## 19. Understanding as **scalability** (of the explanation/method)

- **Definition.** A method/account "understands" to the degree it *scales* — remains tractable,
  faithful, and informative as system size/complexity grows. [meta-level property of the
  method, not of a single system.]
- **Literature.** Simon (hierarchy enables scalable description); the interpretability scaling
  problem (do circuit/SAE methods scale to frontier models?); complexity theory of inference.
- **Strengths.** Practically decisive — a notion of understanding that doesn't scale can't address
  the systems we care about (brains, frontier models).
- **Limitations.** Scalability is a *desideratum on methods*, not a theory of what understanding *is*;
  a method can scale while delivering only knowledge-about.
- **Verdict.** *Neither necessary nor sufficient for the concept,* but a **first-order criterion for
  evaluating methods** (Parts III, VI–VIII): the gap between "understands a toy" and "understands a
  brain/LLM" is largely a scalability gap.

## 20. Understanding as **hierarchy / deriving macro from micro (and micro from macro)**

- **Definition.** To understand X is to have linked its levels — to derive macroscopic behavior from
  microscopic rules (and/or infer microscopic rules from macroscopic behavior) via principled
  coarse-graining. [epistemic object: an inter-level mapping (coarse-graining + closure).]
- **Literature.** Simon (ND/hierarchy); RG/Kadanoff/Wilson; Anderson; causal abstraction; causal
  emergence (Hoel); Marr (cross-level linkage).
- **Strengths.** Connects scales, the deepest form of physical understanding; provides *why* the
  right-level description is autonomous; supports both reduction and emergence.
- **Limitations.** The two directions are *asymmetric and separately hard* (deriving macro from micro
  ≠ inferring micro from macro — the latter is an ill-posed inverse problem); many systems lack a
  clean inter-level map.
- **Verdict.** *Constitutive of the deepest understanding (and the subject of Part V);* we argue
  hierarchy is **near-necessary in practice** for understanding *complex* systems (it's the structure
  that makes them tractable) though not *conceptually* necessary for every system.

## 21. Understanding as **grasp / intelligibility** (the agentive/phenomenological notion)

- **Definition.** To understand X is for an agent to *grasp* X — to have an intelligible
  representation they can fluently use to draw consequences, see "why," and answer questions without
  brute calculation. [epistemic object: an internalized, usable model + skills.]
- **Literature.** de Regt (intelligibility, CIT); Grimm, Kvanvig, Zagzebski (understanding as a
  distinctive cognitive grasp of dependence relations); Sloman ("knowing how it works"); the
  illusion-of-explanatory-depth (the *absence* of grasp).
- **Strengths.** Captures understanding's *agent-relative, ability-based, holistic* character — what
  "understanding" means in ordinary and scientific practice; explains why a printout of a correct
  model isn't yet understanding.
- **Limitations.** Risks subjectivity (feeling vs. fact — IOED); skill-relativity makes
  inter-agent comparison hard; needs objective anchoring.
- **Verdict.** *Constitutive of the "in-an-agent" side of understanding,* necessarily paired with the
  objective side (correct mechanism). Our framework's competence battery is precisely the
  objectification of "grasp" (you grasp iff you can *do* the things).

## 22. Understanding as **prediction of *novel kinds* / explanatory surprise reduction**

- **Definition.** To understand X is to render X's behavior *unsurprising* in the right way —
  including predicting *qualitatively novel* phenomena (new kinds of behavior, not just new
  instances). [epistemic object: a theory whose consequences include unobserved *types*.]
- **Literature.** Lipton (loveliness); novel-prediction as the realist's evidence (no-miracles);
  de Regt (recognizing qualitative consequences).
- **Strengths.** Distinguishes deep theories (predict new *kinds*: antimatter, Higgs, gravitational
  waves) from curve-fits (predict new *instances* only); ties to breadth/depth.
- **Verdict.** *Strong indicator* of deep understanding; a qualitative-novelty test complements the
  counterfactual/transfer batteries (Parts IV/VII).

---

## 23. Cross-cutting synthesis: how the notions relate

The notions are not independent; they cluster and entail one another:

- **The predictive/descriptive cluster** (1 prediction, 2 compression, 10 generative-fit, 18/19
  generalization-within/scalability-as-fit): recover **statistical/predictive structure**
  ("knowledge about"). *None is sufficient.*
- **The causal/interventionist cluster** (5 intervention, 8 counterfactual, 9 causal structure, 16
  invariance): recover **difference-making structure**. *Jointly close to necessary-and-core.*
- **The mechanistic/organizational cluster** (7 decomposition, 14 modularity, 17 compositionality,
  20 hierarchy, 15 robustness): recover **organized productive structure**. *Constitutive of
  mechanistic understanding; tractability-enabling.*
- **The abstraction/level cluster** (6 abstraction, 20 hierarchy, 16 invariance): recover the
  **right relevant variables / level**. *Constitutive of understanding's form.*
- **The competence/agentive cluster** (3 simulation, 8 counterfactual, 11/12/13 transfer/repair/
  design, 21 grasp, 22 novel-kind prediction): the **abilities** that *manifest and test*
  understanding.

**The unifying picture (developed in Part VI):** *understanding of* a system = possession of a
**mechanism-structured, hierarchically-organized, interventionally-faithful model** (the
causal/mechanistic/abstraction clusters) that an agent can *use* to exercise the **competence
cluster** (predict OOD, answer counterfactuals, intervene, repair, redesign, transfer), where mere
**knowledge about** = possession of the **predictive/descriptive cluster** without the causal-
mechanistic structure or the competences it confers.

A one-line test that screens out every "knowledge-about-only" notion: **Can you correctly predict
the effect of interventions you have never observed, and explain why, in terms of organized parts?**
Prediction, compression, generative-fit, decodability, and within-distribution generalization all
fail this test; intervention, counterfactual, causal-structure, mechanistic-decomposition, and
transfer pass it. That test is the seed of Part IV's criteria and Part VI's dimensions.
