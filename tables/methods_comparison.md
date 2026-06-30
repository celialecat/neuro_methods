# Comparison Table of Methods: Epistemic Object, Knowledge-vs-Understanding, and UKG Placement

For each method: the **epistemic object** it recovers, the **Part-III goal category**, **Pearl
rung**, typical **`KA`** (knowledge-about) and **`UO`** (understanding-of) levels, whether it
**crosses the understanding line** (and under what added validation), and the **dominant failure/
over-read.**

Legend: `KA`/`UO` ∈ {lo, med, hi}; "crosses line?" = N / N→Y(condition) / Y.

## A. General scientific / data-analysis methods

| Method | Epistemic object | Goal (Part III) | Rung | KA | UO | Crosses line? | Dominant over-read / failure |
|---|---|---|---|---|---|---|---|
| Regression / curve fitting | predictive map; coefficients | A Prediction | 1 | hi | lo | N→Y(if coeffs interventionally validated) | coefficients read as causes |
| Classification (supervised) | decision boundary | B Classification | 1 | hi | lo | N | spurious/shortcut features |
| Lossless/lossy compression | short code | C Compression | — | med | lo | N | opaque code ≠ mechanism |
| PCA / factor analysis | linear subspace / variance directions | D/E Representation | 1 | med | lo | N | components reified as mechanisms |
| t-SNE / UMAP | 2-D neighborhood projection | E Visualization | — | lo | lo | N | cluster size/distance artifacts |
| Correlation / mutual information | statistical dependence | F Correlation | 1 | med | lo | N | correlation→causation |
| Granger causality / TE | predictive (lagged) dependence | F Correlation | 1 | med | lo | N | "causality" in name only; confounds |
| Taxonomy / phenomenology | catalog of phenomena/parts | G Description | 0 | med | lo | N | description = explanation (connectome fallacy) |
| Dynamical-systems analysis | attractors/bifurcations/manifold geometry | H/J | 1–2 | med | med→hi | N→Y(if causal/perturbation-validated) | geometry without implementing mechanism |
| Agent-based / detailed simulation | runnable generative model | J Simulation | 1(+gen) | hi | lo→med | N→Y(if Rosen-commuting under intervention) | "right for wrong reasons"; opaque sim |
| **Randomized experiment / RCT** | treatment effect | L Intervention | 2 | med | med | Y | effect ≠ full mechanism |
| **Causal discovery (w/ interventions)** | causal graph + mechanisms | M/Theory | 2–3 | med | hi | Y | obs-only variant capped (T1) |
| **ICP / IRM (multi-environment)** | invariant causal predictors | M Reverse-eng | 2 | med | hi | Y | needs heterogeneous environments |
| Mechanistic/biophysical modeling | entities+activities+organization | I Mechanistic | 2–3 | hi | hi | Y | sketch mistaken for how-actually |
| Normative/optimality theory | computational *why* | H/N | — | med | hi(Δ) | Y(if predicts mechanism) | just-so optimality stories |

## B. Neuroscience methods

| Method | Epistemic object | Goal | Rung | KA | UO | Crosses line? | Over-read / failure |
|---|---|---|---|---|---|---|---|
| fMRI activation/localization | BOLD–task correlation, localized | F/G/D | 1 | hi | lo | N→Y(+TMS/lesion ⇒ coarse C10) | blobology; reverse inference; double-dipping |
| Encoding models (RF/voxelwise) | stimulus-feature→response map | A Prediction | 1 | hi | lo→med | N→Y(+normative why +perturbation) | fitted features = brain's algorithm |
| Decoding / "mind-reading" | information availability | A/D | 1 | hi | lo | N | decodable = used by brain |
| RSA | representational geometry (2nd-order) | D/F | 1 | hi | med | N→Y(constrains; +model+causal) | geometry match = same mechanism |
| Linear probes (neural) | decodability of latent var | D | 1 | hi | lo | N→Y(+ablation) | decode ≠ use |
| Network neuroscience (graphs) | connectivity topology/stats | G/F (C13?) | 1 | hi | lo→med | N→Y(+interventional module validation) | graph metrics as artifacts; hub worship |
| Connectomics | structural parts-list+wiring | G Description | 0 | hi | lo | N (substrate only) | wiring = function (C. elegans lesson) |
| Optogenetics / lesion / microstim | interventional dependence | L Intervention | 2 | med | hi | Y | fat-handed; compensation; off-target |
| Hodgkin–Huxley / channel biophysics | how-actually ionic mechanism | I Mechanistic | 2–3 | hi | hi | Y | (exemplar of UO; few failures) |
| Predictive/efficient coding, RL-dopamine | computational *why* + algorithm | H/N | 2 | med | hi(Δ) | Y(predicts mechanism) | over-broad free-energy claims |
| Neural manifolds / dynamics (RNN reverse-eng) | closed low-D dynamical mechanism | I/H | 2 | hi | hi | Y(+perturbation) | manifold as PCA artifact (descriptive) |

## C. Machine-learning / mechanistic-interpretability methods

| Method | Epistemic object | Goal | Rung | KA | UO | Crosses line? | Over-read / failure |
|---|---|---|---|---|---|---|---|
| Representation learning (general) | task-useful features | D | 1 | hi | lo | N | features = concepts/causes |
| Disentanglement (β-VAE etc.) | independent generative factors | D | 1 | med | lo→med | N→Y(needs supervision/bias; Locatello) | unsupervised identifiability impossible |
| World models / learned simulators | generative env. model | J/2 | 1(+gen) | hi | lo→med | N→Y(CRL identifiability) | next-state fit = understands env. |
| **Sparse autoencoders / dictionary** | candidate feature inventory (un-mix superposition) | D Representation | 1 | hi | lo→med | N→Y(+causal validation/composition) | reconstruction features = causal features; splitting/absorption |
| Feature visualization / act-max | unit tuning characterization | E/G | 0–1 | med | lo | N | polysemantic units; what≠role |
| Saliency / IG / LIME / SHAP / Grad-CAM | local input→output sensitivity | F/E | 1 | lo→med | lo | N | fails sanity checks; not faithful |
| Linear probes (NN) | concept decodability | D | 1 | hi | lo | N→Y(+ablation) | decode ≠ use; selectivity (control tasks) |
| TCAV (concept vectors) | concept sensitivity (directional) | F/D | 1 | med | lo | N→Y(+intervention) | correlational unless load-bearing |
| **Activation patching / causal tracing** | interventional internal dependence | L Intervention | 2 | med | hi | Y | fat-handed/off-distribution patches |
| **Interchange interventions / causal abstraction / DAS** | causal-model isomorphism (faithfulness) | M/I | 2–3 | med | hi | Y | over-flexible alignment overstates F |
| **Ablation-validated circuits (IOI, induction, modular-add)** | how-actually network algorithm | I/M Reverse-eng | 2–3 | hi | hi | Y | (exemplar of UO) plausibility>faithfulness if unvalidated |
| Model editing (ROME/MEMIT) | locate+edit = repair/redesign test | L/redesign | 2 | med | med→hi | N→Y(specific+generalizing edits) | edit success ≠ storage localization |
| Causal representation learning | latent causal variables+graph | M Reverse-eng | 2–3 | med | hi | Y | identifiability needs interventions/biases |
| Probing-then-claiming (generic) | decodability | D | 1 | hi | lo | N | the canonical MI over-read |

## D. Summary placement on the UKG `(KA, UO)` plane

- **Top-left (hi KA, lo UO) — "knowledge about," the over-read zone:** regression/classification,
  PCA/t-SNE/UMAP, correlation/Granger, taxonomy, fMRI localization, decoding, network graphs,
  connectomics, linear probes, TCAV, feature visualization, saliency/attribution, SAEs-by-
  reconstruction, raw world-model fit. *These are the methods Jonas–Kording/Lazebnik show can be
  maximized on a fully-known system while recovering no mechanism.*
- **Upper-right (hi KA, hi UO) — "understanding of":** RCT/causal-discovery-with-interventions, ICP,
  mechanistic/biophysical models (Hodgkin–Huxley), normative theories that predict mechanism,
  manifold-dynamics reverse-engineering, optogenetic/lesion-validated mechanisms, activation
  patching, interchange interventions/causal abstraction/DAS, ablation-validated circuits, CRL,
  specific-generalizing model edits.
- **The discriminator is always the same:** the upper-right methods supply **interventionally-
  validated, faithfulness-bearing, level-appropriate** structure (`F/CF/CC/HC`); the top-left supply
  **fit/decoding/description** (`P/decodability`). No top-left method becomes upper-right without
  adding intervention/faithfulness — the empirical content of theorems T1 and T2 (Part VI).
