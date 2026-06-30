# Part VIII — Application to Neuroscience and Mechanistic Interpretability

Here we apply the framework (Parts IV/VI) to the methods the brief names, asking for each: **what
epistemic object does it recover?**, **where does it sit on the UKG `(KA, UO)`?**, **does it cross
the understanding line, and under what added assumptions/validation?** This is where the title
distinction does its work: most of these methods are superb engines of *knowledge about* the
brain/network and are routinely over-read as delivering *understanding of* it.

The compact verdicts are in `tables/methods_comparison.md`; this file is the reasoning.

---

## A. Neuroscience methods

### A1. fMRI analysis (mass-univariate activation; localization)
- **Epistemic object.** Correlation between BOLD (a slow, indirect hemodynamic proxy) and
  task/stimulus, localized to voxels/regions. **Rung-1, descriptive-localizational.**
- **UKG.** High-ish `KA` (predicts/decodes some task structure), low `UO` (no mechanism; "region X
  activates" is neither necessary nor sufficient for function — fails mutual manipulability without
  lesion/stim). Large gap `G`.
- **Crosses the line?** Only when paired with **causal perturbation** (TMS/lesion/stim) establishing
  mutual manipulability, and even then yields coarse localization (`C10` conditional), not the
  mechanism. *Blobology* is the field's own term for the over-read.
- **Failure cases.** Reverse inference ("region active ⇒ cognitive process present"); double-dipping;
  vibration/motion artifacts; the dead-salmon cautionary tale. **Paradigm of knowledge-about
  mistaken for understanding.**

### A2. Encoding models (voxelwise/neuronal receptive-field models)
- **Epistemic object.** A predictive stimulus-feature→response mapping; *which feature space
  predicts responses.* **Predictive (rung 1), with a representational claim.**
- **UKG.** High `KA` (state-of-the-art response prediction; `P` high). `UO` is **conditional**: a
  good fit shows the feature space is *sufficient to predict*, not that the brain *computes via* it
  (multiple feature spaces fit comparably — underdetermination). `F` not established by fit.
- **Crosses the line?** Toward `UO` when (i) the feature space is *constrained by a normative/why
  account* (efficient coding predicting Gabors — `Δ` up), and (ii) validated by **intervention**
  (does perturbing the posited feature channel change responses as predicted?). Otherwise it is
  excellent `KA`.
- **Failure cases.** Attributing the model's features to the brain's algorithm; ignoring closed-loop/
  inside-out dynamics (Buzsáki).

### A3. Decoding models ("mind-reading")
- **Epistemic object.** **Decodability** — information *present and linearly/nonlinearly available*
  in neural signals. **Rung-1, availability.**
- **UKG.** High `KA`; `UO ≈ 0` by itself. The **encoding/decoding asymmetry**: decodable ≠ used by
  the brain ≠ how. A classic *probing* situation (cf. A-side analogue of interpretability probes).
- **Crosses the line?** No, unless the decoded variable is shown to be **used** (intervene: does
  disrupting the decodable code change behavior/computation?). Decoding is a *necessary clue*, not a
  mechanism.

### A4. Representational Similarity Analysis (RSA)
- **Epistemic object.** Second-order **representational geometry** (dissimilarity structure), and its
  match across brains/models/behavior. **Representational-level correlation.**
- **UKG.** Strong `KA` and a genuine *constraint* on `UO` (rules out models with the wrong
  geometry). But **a geometry match is multiply realizable** — same RDM, different mechanisms — so
  `F` is not established. Moves `UO` only as a *comparative/constraining* tool.
- **Crosses the line?** Partially: RSA + DNN models (Yamins–DiCarlo) gives *algorithmic-level*
  evidence (a model class that reproduces geometry and behavior), strengthening `UO`; still needs
  causal validation to claim the brain's *mechanism*.

### A5. Linear probes / neural decoders of latent variables
- Same structure as A3 at finer grain. **Decodability ≠ usage.** `KA` high, `UO` only after
  intervention. (Mirror of interpretability probes — B6.)

### A6. Network neuroscience (graph analysis of connectivity)
- **Epistemic object.** **Topological/statistical description** of structural/functional
  connectivity (modules, hubs, small-worldness, controllability). **Descriptive/correlational
  structure (often `C13` candidate modularity).**
- **UKG.** `KA` high (rich organizational description); `UO` low until topology is **tied to
  mechanism and validated by intervention** (does targeted perturbation of a "hub" produce the
  predicted functional change?). Risk: graph metrics as artifacts of thresholding/preprocessing.
- **Crosses the line?** Toward `UO` when modules/hubs are *interventionally* validated (locality of
  perturbation effects) — i.e., used to recover the **decomposability profile** (Part V), not just
  describe it.

### A7. Connectomics
- **Epistemic object.** **Complete structural parts-list + wiring** (the static mechanism skeleton).
- **UKG.** Maximal *descriptive* `KA` about structure; **`UO` strikingly low alone** — the
  *C. elegans* lesson: full wiring of 302 neurons does not yield behavior, because function needs
  dynamics, neuromodulation, and physiology absent from the wiring. **The strongest real-world case
  of "complete low-level description ≠ understanding"** — the connectome is a *mechanism sketch with
  the activities missing* (low `CC`).
- **Crosses the line?** Only as the *substrate* for dynamical/causal models built on top; necessary,
  far from sufficient.

### A8. Encoding-via-DNN & computational/normative models (efficient/predictive coding, Bayesian,
RL/dopamine, Hodgkin–Huxley)
- **Epistemic object.** Varies: **computational-level *why*** (normative theories) and/or
  **how-actually mechanism** (Hodgkin–Huxley).
- **UKG.** **Hodgkin–Huxley is the field's exemplar of high `UO` (achievement 6 at its level):**
  mechanism (ion channels), counterfactual/intervention competence (voltage clamp), `CC` high,
  obtained *interventionally* not by black-box fitting. Normative theories raise `Δ` (the *why*) and,
  when they *predict mechanism* (efficient coding → receptive fields), genuinely raise `UO`.
- **Crosses the line?** Yes — these are where neuroscience *does* understand. Note the contrast with
  A1–A7: the high-`UO` methods are **mechanistic/interventional/normative**, the low-`UO` ones are
  **correlational/descriptive**, exactly as the framework predicts.

### A9. Neural manifolds / computation-through-dynamics
- **Epistemic object.** **Dynamical/geometric structure of population activity** (low-D manifolds,
  fixed points, attractors, rotations) — the *right collective variables* (a closed low-D level,
  Part V), and via RNN reverse-engineering (Sussillo–Barak) an *algorithmic-level* mechanism.
- **UKG.** Among the **highest-`UO` modern systems-neuroscience approaches**: it finds an autonomous
  level (`HC` up), supports `CF`/`IV` (perturb along/off manifold and predict), and yields
  intelligible dynamical mechanisms (`X`, `Δ`). Still must validate that the manifold is *causal*
  (used), not just *descriptive* (a PCA artifact) — closed-loop perturbation tests do this.
- **Crosses the line?** Yes, when the dynamical structure is interventionally validated — a leading
  exhibit for "understanding via the right relevant variables."

**Neuroscience summary.** The field's `(KA, UO)` map is bimodal: a large, mature **knowledge-about**
arm (fMRI localization, decoding, RSA, network graphs, connectomes — high `KA`, low `UO`, the
*correlation menagerie* Jonas–Kording warn about) and a smaller **understanding** arm
(biophysical/normative models, manifold-dynamics reverse-engineering — high `UO`), distinguished by
**interventional validation + the *why* + recovery of the right level**. The framework's
prescription for neuroscience: *report the `(KA, UO)` cell; treat decoding/correlation/connectome as
clues; reserve "understanding" claims for interventionally-validated, level-closed, why-bearing
mechanisms.*

---

## B. Mechanistic interpretability methods

### B1. The MI program (circuits/features) as reverse-engineering
- **Epistemic object (aspiration).** Features (entities) + weighted connections (activities) +
  organization = the **MDC mechanism** of a network; i.e., achievement 5–6.
- **UKG.** *When validated causally* (interchange interventions), MI targets high `UO` directly — it
  is the clearest deliberate attempt to cross the understanding line *inside* a learned system.
  Successes (modular addition, induction heads, IOI) reach achievement 6 at their level.
- **Caveat.** MI's central risk is **plausibility over faithfulness** (Jacovi–Goldberg): a
  human-legible circuit story that isn't the model's actual computation. The framework's `F`
  (interchange-intervention agreement) is the required guard.

### B2. Sparse autoencoders (SAEs) / dictionary learning
- **Epistemic object.** A candidate **feature inventory** (the mechanism's *entities*) recovered by
  unsupervised sparse reconstruction — addressing **superposition** (the right *level*, not neurons).
- **UKG.** Produces a **representation** (high `KA` about activation geometry). `UO` is **not
  established by reconstruction**: identifiability is not guaranteed (cf. disentanglement —
  Locatello), and recent work flags feature **splitting/absorption** and questions whether SAE
  features are the ones the model **causally uses**. So SAEs sit *left* (representation) until their
  features are **causally validated** (ablate/steer and confirm predicted behavior change → `F` up).
- **Crosses the line?** *Conditionally* — SAE features become mechanism only after interventional
  validation and composition into circuits (`MO`/`F`). As of now, a powerful **knowledge-about /
  hypothesis-generating** tool whose `UO` is realized only with downstream causal tests.

### B3. Activation patching / causal tracing
- **Epistemic object.** **Interventional (rung-2) dependence** among internal activations — a
  `do`-operation inside the network. Directly targets `CF`/`F`.
- **UKG.** Among the **highest-`UO`** MI methods: it establishes *which components causally matter*
  for a behavior. Caveats: **fat-handed/off-distribution** patches create artifacts (the network is
  pushed off its manifold), and "matters for this behavior" is *local* causal knowledge that must be
  *organized* into a circuit (`MO`) and given a *why* (`Δ`) for full mechanistic understanding.
- **Crosses the line?** Yes — it is the method that most directly supplies the interventional content
  the data ceiling (T1) forbids passive methods.

### B4. Interchange interventions / causal abstraction / DAS
- **Epistemic object.** Whether the network **implements a hypothesized high-level causal algorithm**
  — checked by aligning interchange interventions in the net with interventions in the abstract
  model. **This is the operationalization of `F` (faithfulness as causal-model isomorphism) and of
  Rosen's commuting diagram.**
- **UKG.** The **most `UO`-aligned** interpretability method in principle: it tests achievement-5/6
  faithfulness directly and *gradably* (how much of the behavior the abstraction covers = `CC`).
  Caveats: DAS can find *an* alignment that overstates faithfulness if the hypothesis space is too
  flexible (an identifiability worry) — must be regularized/validated OOD.
- **Crosses the line?** Yes — by construction it measures mechanism recovery, not prediction.

### B5. Model editing (ROME, MEMIT)
- **Epistemic object.** A **locate-then-edit** intervention; editing success + specificity +
  generalization is a **repair/redesign** test (`C3`/`C4`) of whether the located component is the
  mechanism.
- **UKG.** Moderate-to-high `UO` *as a test* (successful, specific, generalizing edits are strong
  evidence the localization is causal); but edit success can be achieved by *off-mechanism* shortcuts
  (editing a correlate), so specificity/generalization must be stringent. Localization claims from
  editing have been contested (edit success doesn't prove the edited site *stores* the fact).
- **Crosses the line?** Conditionally — a clean, specific, generalizing edit is good `F`/`CF`
  evidence; a brittle edit is `KA`.

### B6. Linear probes / concept probing
- **Epistemic object.** **Decodability** of a concept from activations. **Correlational/availability**
  (rung 1). *Identical epistemic structure to neuroscience decoding (A3/A5).*
- **UKG.** High `KA`, `UO ≈ 0` alone. **Probe selectivity / control tasks** (Hewitt–Liang) and the
  decode-vs-use gap mean a probe can read information the model never uses. Upgrades to `UO` only via
  **ablation/intervention** (does removing the probed direction change behavior?).
- **Crosses the line?** No, unless causally validated. *The MI twin of A3.*

### B7. Concept Activation Vectors (TCAV)
- Between probing and attribution; **correlational sensitivity** to human-concept directions.
  `KA` with a causal-flavored metric; `UO` requires the concept direction to be *interventionally*
  load-bearing. Same verdict as B6.

### B8. Feature visualization / activation maximization
- **Epistemic object.** A **descriptive characterization** of a unit/feature's tuning (what maximally
  drives it). **Descriptive (rung 0–1).**
- **UKG.** `KA` (tells you *what* a feature responds to); `UO ≈ 0` about its *causal role* in the
  circuit. Polysemantic/superposed units make single-unit visualizations misleading.
- **Crosses the line?** No — hypothesis-generation/communication aid (the MI analogue of
  visualization, Part III §E), with the same over-read risk.

### B9. Feature attribution / saliency (Integrated Gradients, LIME, SHAP, Grad-CAM)
- **Epistemic object.** **Local input→output sensitivity/correlation.** Explains *the output's*
  dependence on inputs, **not the mechanism.**
- **UKG.** `KA` (sometimes), `UO ≈ 0`; many methods **fail sanity checks** (Adebayo) and **lack
  faithfulness**. The clearest interpretability example of "knowledge-about (which inputs matter
  locally) ≠ understanding."
- **Crosses the line?** No.

### B10. World models / learned simulators (in agents)
- **Epistemic object.** A **generative/predictive simulator** of an environment. Achievement 2
  (modeling) by default.
- **UKG.** High `KA`; `UO` iff the latent transitions are **causally/mechanistically faithful**
  (support correct counterfactuals/transfer — `CF`/`T`), which requires causal-representation-learning
  guarantees (interventions/multi-environment), not next-state-prediction alone.
- **Crosses the line?** Conditionally, exactly when CRL identifiability conditions are met.

### B11. Causal representation learning (as an interpretability tool)
- **Epistemic object.** Latent **causal variables + graph** — directly the `F`/`C8` target.
- **UKG.** Designed to maximize `UO`; bound by **identifiability** (needs interventions/multiple
  environments/inductive bias — T1 in ML clothing). The principled route to raising `UO` inside
  learned systems.

**Interpretability summary.** MI's methods split exactly as neuroscience's do:
- **Knowledge-about arm** (saliency, probes, TCAV, feature visualization, SAEs-by-reconstruction,
  raw world-model fit): high `KA`, low `UO` until causally validated — the *interpretability
  correlation menagerie*.
- **Understanding arm** (activation patching, interchange interventions/causal abstraction/DAS,
  ablation-validated circuits, specific-generalizing model edits, CRL): target `UO` directly via
  **intervention** and are gradable by `F`/`CF`/`CC`.
This split is the same `KA`/`UO` distinction as in neuroscience, which is the framework's central,
domain-independent prediction. **Mechanistic interpretability is, in our terms, the project of
moving learned systems from achievement 1–2 (predicting/modeling) to 5–6 (reverse-engineering/
mechanistic understanding); the methods that do so are precisely the interventional ones, and the
field's own faithfulness-vs-plausibility debate is its rediscovery of the prediction-vs-
understanding distinction.**

---

## C. Which methods genuinely improve understanding? (the bottom line)

Across both domains, the framework gives a single, sharp verdict criterion: **a method improves
`UO` (understanding) iff it adds interventionally-validated, faithfulness-bearing, level-appropriate
structure (`F`, `CF`, `CC`, `HC`); a method that only improves fit/decoding/description improves
`KA` (knowledge about) and, by T1/T2, *cannot* substitute for the former.**

- **Genuinely improve understanding** (high or conditional-high `UO`): biophysical/normative models
  and Hodgkin–Huxley-style mechanism; manifold/computation-through-dynamics with perturbation;
  activation patching; interchange interventions / causal abstraction / DAS; ablation-validated
  circuits; specific-generalizing model edits; causal representation learning; interventionally-
  validated network modules. *(All interventional/mechanistic/normative.)*
- **Improve knowledge-about, routinely over-read as understanding** (high `KA`, low `UO` alone):
  fMRI localization, decoding/mind-reading, RSA (as a sole tool), network-graph description,
  connectomics, linear probes, TCAV, feature visualization, saliency/attribution, SAEs-by-
  reconstruction, raw world-model/next-token fit. *(All correlational/descriptive/representational —
  valuable, necessary clues and substrates, but not understanding until causally upgraded.)*

The practical recommendation for both neuroscience and interpretability is identical and follows
directly from the framework: **state the epistemic object and the `(KA, UO)` cell; treat
correlational/representational results as hypotheses; and reserve "we understand" for claims backed
by intervention, faithfulness against (where possible) ground truth, recovery of the right level,
and the competence battery (counterfactual/transfer/failure/repair).** That discipline is exactly
what Jonas & Kording and Lazebnik were asking the field to adopt.
