# When Have We Understood a Complex System? From Prediction to Mechanism

### A framework for distinguishing knowledge *about* a system from understanding *of* a system

*Position paper — written in the style of Nature Reviews / PNAS Perspectives.*

---

## Abstract

Two thought experiments — *Could a Neuroscientist Understand a Microprocessor?* and *Could a
Biologist Fix a Radio?* — show that the standard analytic toolkit of data-rich science (tuning
curves, lesions, correlations, dimensionality reduction, connectomes) can be applied in full to a
system whose mechanism is completely known and still fail to recover that mechanism. The lesson is
epistemological, not technical: **prediction, compression, representation, and correlation are
achievements of *knowledge about* a system that do not, by themselves, constitute *understanding of*
it.** We make this distinction precise. Drawing on the philosophy of explanation (Hempel→Woodward→
Craver→Strevens), complexity and systems science (Simon, the renormalization group, Rosen),
information theory (Kolmogorov/MDL, the information bottleneck, computational mechanics, effective
information), and causal inference (Pearl's ladder, invariant prediction, causal abstraction), we
propose that understanding is a **graded profile over measurable dimensions** — predictive power,
counterfactual competence, intervention capability, mechanistic faithfulness, hierarchical
consistency, modularity, transferability, robustness, depth, and intelligibility — gated so that no
amount of predictive or compressive performance counts as understanding without
*interventionally-validated, faithfulness-bearing, level-appropriate* structure. We formalize an
**epistemic ladder** (knowing → predicting → modeling → explaining → understanding →
reverse-engineering → mechanistic understanding) and an **Understanding–Knowledge Gradient** whose
two coordinates, `KA` (knowledge-about) and `UO` (understanding-of), turn the Jonas–Kording/Lazebnik
worry into a coordinate and two theorems: passive data cannot move a model above the
understanding line, and predictive score is not a consistent estimator of understanding. We propose
benchmarks on systems with *known* ground-truth mechanism (microprocessors, cellular automata, logic
circuits, small transformers, synthetic causal graphs) that separate methods which merely predict
from methods which recover mechanism, and we apply the framework to neuroscience (fMRI, encoding/
decoding, RSA, network neuroscience, connectomics, manifold dynamics) and mechanistic
interpretability (probes, saliency, sparse autoencoders, activation patching, causal abstraction,
model editing). In both fields the methods split identically: a large *knowledge-about* arm
routinely over-read as understanding, and a smaller *understanding* arm distinguished by
**intervention, faithfulness, and recovery of the right level**. The central recommendation is
simple and enforceable: *for every method, name the epistemic object it recovers and the validation
regime it used; reserve "understanding" for claims backed by intervention, faithfulness, the right
level, and the competence battery.*

---

## 1. The problem: prediction is masquerading as understanding

Modern science is awash in predictive success. Deep networks predict protein structure and the next
token; high-dimensional neural recordings decode intentions; foundation models pass professional
exams. It is tempting to equate this flood of predictive and representational achievement with
growing understanding. Jonas and Kording (2017) and Lazebnik (2002) constructed the decisive
counterexample. Take a system we understand *completely* because we built it — a microprocessor, a
radio — generate the kind of data neuroscience and systems biology collect, and apply the field's
standard analyses. The result: tuning curves, lesion effects, "functional connectivity," and
low-dimensional projections that *look* like insight but do **not** reconstruct the known
architecture. A method can be maximally successful by the field's own metrics and recover no
mechanism.

This is not a complaint about any one technique. It is a claim about a **category error**: confusing
the epistemic goal a method serves with the goal we ascribe to it. The aim of this paper is to
dissolve the error by making the distinction it rests on precise, measurable, and enforceable — and
to do so in a way that transfers to the two fields the question ultimately targets: neuroscience and
the mechanistic interpretability of neural networks.

Our thesis, following the requirement that motivates this project: **methods that improve
prediction, representation, or accuracy produce *knowledge about* a system; understanding *of* a
system additionally requires recovering its causal-mechanistic, hierarchical structure and the
competences that structure confers. Higher accuracy is not more understanding.**

## 2. Why the gap is real and cannot be closed by more data

Five independent literatures converge on the same conclusion (developed in the companion review,
Part I).

- **Explanation is asymmetric, relevant, and causal; prediction is none of these.** Hempel's
  covering-law model foundered precisely on cases — the flagpole and its shadow, the barometer and
  the storm — where derivation/prediction runs in the wrong direction or rides on a common cause.
  Salmon, Woodward, and the New Mechanists relocated explanation in *difference-making causal/
  mechanical structure*: entities and activities, organized, whose dependences are *invariant under
  intervention*.
- **Pearl's ladder proves the gap.** Association (rung 1), intervention (rung 2), and counterfactual
  (rung 3) are strictly increasing in expressive power, and **one cannot climb from rung 1 to rungs
  2–3 from observational data alone** — only from interventions or structural assumptions. Prediction
  lives on rung 1; understanding lives on rungs 2–3.
- **Identifiability results in machine learning say the same thing.** Disentangled and causal
  representations are *unidentifiable* without inductive biases, interventions, or multiple
  environments (Locatello et al.; Schölkopf et al.). Passive fit underdetermines mechanism.
- **Compression is necessary but not sufficient.** Structure shows up as compressibility (Kolmogorov,
  MDL, Simon's redundancy, Kitcher's unification), but the shortest code can be opaque, merely
  *predictively* (not causally) sufficient (the information bottleneck discards causal-but-redundant
  variables; an ε-machine is the minimal *predictive* model, not necessarily the mechanism), and is
  multiply realizable. *A short description in the wrong vocabulary is not understanding.*
- **A complete low-level description is not understanding.** The *C. elegans* connectome — every
  neuron and synapse of a 302-cell nervous system — does not yield its behavior, because function
  depends on dynamics and physiology absent from the wiring. The connectome is a mechanism sketch
  with the activities missing.

These are not five observations; they are one, stated five ways: **there is a gap between the
statistical structure of a system's behavior and its causal-mechanistic structure, and the gap is
not a data-volume problem.**

## 3. The framework: understanding as a gated profile

We treat a candidate understanding as a **model** `M` held by an **agent** `A` about a **system**
`S`, related by encode/decode/inference maps, evaluated at a chosen **level** `L` against a
**question battery** `Q`. The single condition that separates prediction from understanding is that
the modeling relation **commute under intervention**:

> doing an intervention *in the model* and decoding it should match doing the intervention *in the
> world* and observing — not merely matching outputs under passive observation.

Passive-observation match is prediction (rung 1); commuting-under-intervention is understanding
(rungs 2–3). This is Rosen's modeling relation made operational with Pearl/Woodward machinery, and
it is the formal location of the Jonas–Kording/Lazebnik gap.

### 3.1 An epistemic ladder

We distinguish seven achievements, each adding a specific epistemic object:

**Knowing** (facts/descriptions) → **Predicting** (rung-1 forecasts) → **Modeling** (a runnable
generative simulator) → **Explaining** (difference-making structure) → **Understanding** (a grasped,
intervention-faithful, abstracted model usable across a broad counterfactual battery) →
**Reverse-engineering** (that understanding decomposed into the system's *actual* organized parts,
validated by part-level intervention) → **Mechanistic understanding** (hierarchically consistent
across levels, with the computational *why*).

The first three are reachable with more data/compute alone; crossing from *modeling* to *explaining/
understanding* requires interventional content that, by §2, data cannot supply. Lazebnik's "fix the
radio" is reverse-engineering; Jonas–Kording's challenge demands mechanistic understanding;
Hodgkin–Huxley's action potential and the reverse-engineered modular-arithmetic circuit in a small
transformer are existence proofs that the top of the ladder is reachable.

### 3.2 Measurable dimensions

Understanding is not scalar. We define dimensions in [0,1] (full definitions in Part VI):
**predictive power** `P` (weighted to out-of-distribution), **counterfactual competence** `CF`
(the commuting-diagram score), **intervention capability** `IV`, **mechanism-structured
compression** `K` (short *and* in a vocabulary of composable parts), **mechanistic faithfulness** `F`
(do the model's parts map onto the system's, validated by interchange interventions),
**hierarchical consistency** `HC` (does a closed, low-dimensional, intervention-respecting
description exist at each scale, with commuting inter-level maps), **modularity** `MO`,
**transferability** `T`, **robustness** `R` (explains failure modes), **depth** `Δ` (range of
invariance + the *why*), **intelligibility** `X` (can a bounded agent produce the step-by-step
mechanism), and **causal completeness** `CC` (no unexplained interventional variance, no black
boxes). The object dimensions {`F,CC,HC,MO,K`} say *what structure was recovered*; the competence
dimensions {`P,CF,IV,T,R,Δ,X`} say *what the agent can do with it*.

### 3.3 The Understanding–Knowledge Gradient and two theorems

Aggregate the predictive/compressive dimensions into a **knowledge-about index** `KA` and the
causal-mechanistic-competence dimensions into an **understanding-of index** `UO`, where `UO` is
*gated* — it is near zero whenever faithfulness `F` or counterfactual competence `CF` is near zero,
**regardless of how high `KA` is.** Every (model, system, level) tuple then has coordinates
`(KA, UO)` and an **understanding gap** `G = KA − UO`.

- *(T1, the data ceiling.)* No amount of observational data raises `UO` above the understanding line;
  ascending requires interventions, multiple environments, or inductive biases.
- *(T2, the clever-predictor gap.)* For any system with a nontrivial intervention algebra there exist
  models that maximize `KA` yet fail the interventional battery, so **`KA` is not a consistent
  estimator of `UO`.**

T2 *is* the Jonas–Kording statement: a perfectly predictive model of the microprocessor can be
mechanistically empty. The framework's payoff is that "improving prediction moves you rightward in
`KA` but not upward in `UO`" is now a theorem, and any study can be placed by its measured
coordinates. The pathological-and-common regime is the **top-left**: high `KA`, low `UO`, large gap —
prediction dressed as understanding.

## 4. A definition

> **An agent understands a system at a level to a degree iff it possesses a model whose modeling
> relation *commutes under intervention* at that level (faithful, counterfactually competent,
> causally complete), which is *short in a vocabulary of composable parts organized into the
> system's actual, possibly hierarchical, structure* (compressed, modular, hierarchically
> consistent), and which the agent can *use* to answer a broad, anti-gameable battery of
> out-of-distribution, counterfactual, interventional, failure-mode, and cross-system-transfer
> questions and to produce a step-by-step generative account.** The degree is the gated aggregate
> `UO`; the understanding is *mechanistic* when it spans levels with commuting maps and supplies the
> computational *why*. **Knowledge about** the system is the predictive/descriptive achievement
> *without* the commuting-under-intervention clause — the large-gap regime.

The definition is relativized (level, battery), graded, anti-gameable (interventional/OOD battery,
parts-vocabulary), and multiple-realizability-aware (faithfulness is to intervention behavior at a
level, so legitimate abstraction is allowed).

## 5. Does understanding require hierarchy?

Almost universally, the structure that makes complex systems understandable is the same:
**near-decomposable hierarchy of nearly-closed levels** (Simon's near-decomposability and
spectral-gap aggregation; the renormalization group's relevant variables and universality;
Anderson's "more is different"; causal abstraction's commuting levels; causal emergence's
effective-information-maximizing scale). Our position is nuanced: hierarchy is **not conceptually
necessary** for understanding *per se* (a pendulum needs none), but for complex systems it is
**de facto necessary**, because a bounded agent cannot build or grasp an un-hierarchized causal model
of a large, densely-interacting system — the only known route is to find levels at which the
description *closes and compresses*. We therefore recommend that "discovering hierarchy" be treated
not as an assumed precondition but as a **reported empirical result**: every understanding-seeking
study should output a **decomposability profile** — for each candidate scale, does a closed,
low-dimensional, intervention-respecting description exist, and how good is it? Where clean levels
exist, understanding *is* the recovered hierarchy of mechanisms; where they do not (genuinely
integrated systems — high integrated information, synergistic computation), understanding *relocates*
from parts to global/dynamical variables, and the demonstration of irreducibility is itself the
finding. This is exactly where Lazebnik's localization fails, now stated quantitatively.

## 6. Testing the framework: benchmarks with known ground truth

Because the framework's object dimensions (`F, HC, MO, CC`) are defined against the true mechanism,
they can be *measured* on systems we built. We propose a benchmark suite — radios and analog
circuits (the *repair* test), microprocessors (multi-level reverse-engineering), Game of Life and
cellular automata (weak emergence and the right macro level), logic circuits and finite-state
machines (exact scoring), small transformers with known intended algorithms (modular addition,
indirect-object identification, induction heads, toy superposition), gene-regulatory and toy
biological networks (the decomposability gradient), simple physical simulations (scale separation and
the renormalization group), and synthetic causal graphs (the pure causal-discovery test). Three
design rules make a benchmark *separate prediction from understanding*: it must include a **strong
black-box predictor control** (to exhibit the gap `G`), a **rich intervention algebra** (to score
`CF`/`F` against truth), and a **decomposability sweep** from modular to integrated (to locate where
methods break). The framework makes falsifiable predictions: correlational/representational methods
will score high `KA`, low `F`, and fail the first intervention/OOD test; interventionist methods will
score higher `F`, and their advantage will *grow* with the number of interventions (T1 made visible)
and *collapse* as integration crosses a threshold (Part V made visible). If a purely observational
method recovered the microprocessor's architecture, the framework would be refuted.

## 7. Application: neuroscience and mechanistic interpretability split the same way

Applying the `(KA, UO)` lens (Part VIII) yields a striking, domain-independent regularity. In **both**
fields the methods fall into two arms:

- **A knowledge-about arm** (high `KA`, low `UO`, over-read as understanding): fMRI localization,
  neural decoding, representational similarity analysis used alone, network-graph description,
  connectomics — and, in interpretability, linear probes, concept activation vectors, feature
  visualization, saliency/attribution, sparse autoencoders evaluated by reconstruction, and raw
  next-token/world-model fit. These recover correlations, representations, and descriptions —
  indispensable clues and substrates, but not mechanism.
- **An understanding arm** (high `UO`, distinguished by intervention/faithfulness/level): biophysical
  and normative models (Hodgkin–Huxley; efficient/predictive coding that *predicts* receptive
  fields), manifold/computation-through-dynamics with perturbation, optogenetic/lesion-validated
  mechanisms — and, in interpretability, activation patching, interchange interventions / causal
  abstraction / distributed alignment search, ablation-validated circuits, specific-and-generalizing
  model edits, and causal representation learning.

The discriminator is invariant: the understanding arm supplies **interventionally-validated,
faithfulness-bearing, level-appropriate** structure; the knowledge-about arm supplies fit and
decodability. Decoding is not usage; reconstruction is not causation; a region "lighting up" is not a
mechanism; a sparse feature is a hypothesis until an intervention confirms it is the unit the model
*uses*. Notably, the interpretability community's own debate — *faithfulness versus plausibility* — is
that field independently rediscovering the prediction-versus-understanding distinction. Mechanistic
interpretability, in our terms, **is** the project of moving learned systems from predicting/modeling
to reverse-engineering/mechanistic understanding, and the methods that achieve it are precisely the
interventional ones.

## 8. Recommendations

1. **Name the cell.** For every result, state (i) the epistemic object recovered (regularity,
   representation, causal relation, mechanism, hierarchy, invariant) and (ii) the validation regime
   (fit/decoding vs. intervention/transfer). Most "we understand X" claims live in the top-left;
   saying so is the antidote.
2. **Make the battery interventional and out-of-distribution.** In-distribution prediction is near-zero
   evidence of understanding; counterfactual, interventional, failure-mode, novel-kind, and transfer
   questions are the discriminating tests (and are hard to game).
3. **Validate faithfulness causally, never by plausibility.** A human-convincing story is not a
   correct mechanism; require interchange-intervention/ablation agreement, ideally against ground
   truth.
4. **Report a decomposability profile.** Treat the discovery (or absence) of closed, modular levels
   as a measured output, not an assumption; expect — and accept — that some systems are genuinely
   integrated and resist part-wise mechanism.
5. **Build ground-truth benchmarks with predictor controls.** Only a benchmark that includes a strong
   predictor which *fails* the mechanism tests can demonstrate that a method recovers understanding
   rather than prediction.

## 9. Conclusion

Jonas, Kording, and Lazebnik were not making a narrow methodological joke; they were pointing at a
permanent feature of inquiry into complex systems. **Prediction, compression, representation, and
correlation are genuine and necessary epistemic achievements — knowledge *about* a system — but they
are not understanding, and accumulating more of them does not, by itself, produce understanding.**
Understanding *of* a system is the recovery of its causal-mechanistic, hierarchical structure,
validated by intervention and manifested as the ability to predict the unseen, answer counterfactuals,
intervene, repair, redesign, transfer, and explain failure — at the right level, in a vocabulary of
composable parts, and graspable by a bounded agent. The Understanding–Knowledge Gradient turns this
distinction into coordinates, two theorems, measurable dimensions, and falsifiable benchmarks; the
decomposability profile turns "discover the hierarchy" into a reported result; and the `(KA, UO)`
lens sorts the methods of neuroscience and interpretability into those that genuinely deepen
understanding and those that, however powerful, deepen only knowledge about. The discipline this
demands is modest but transformative: *say what you recovered, and how you validated it — and reserve
the word "understand" for the cases that earn it.*
