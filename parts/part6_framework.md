# Part VI — Toward a Theory of Mechanistic Understanding: An Original Framework

This Part presents the project's original contribution: a framework that (1) sharply separates
*knowing, predicting, modeling, explaining, understanding, reverse-engineering,* and *mechanistic
understanding*; (2) defines **measurable dimensions** of understanding; and (3) assembles them into
a single graded construct — the **Understanding–Knowledge Gradient (UKG)** — with an explicit,
testable definition. The framework is designed so that the Jonas–Kording/Lazebnik thesis ("more
prediction/data ≠ more understanding") is a *theorem* of the framework, not an afterthought.

---

## 1. Primitives: the modeling relation, made operational

We adopt Rosen's **modeling relation** as the backbone and make it operational with Pearl/Woodward
machinery.

- A **target system** S has states, dynamics, and a (possibly unknown) causal structure: an
  intervention algebra `I_S` (the well-defined manipulations one can perform) and a response map
  giving, for each intervention, the resulting behavior/distribution.
- A **model** M (held by an agent A) consists of: a set of **variables** V_M (with a chosen
  *level/granularity*), a **structure** (equations/graph/program) over V_M, an **encoding** map
  e: S→M (measurements → model variables) and **decoding** map d: M→S (model predictions →
  observable claims), and an **inference/simulation** procedure.
- M is **faithful** to S at level L to the degree the diagram **commutes**: for the relevant
  interventions and observations, `d(infer_M(e(x), do_M(ι)))  ≈  observe_S(do_S(ι), x)`. That is,
  *doing the intervention in the model and decoding* matches *doing it in the world and observing* —
  **not merely** matching outputs under passive observation.

This single condition already encodes the thesis: **passive-observation match** (the special case
with no `do`) is *prediction*; **commuting under interventions** is *understanding*. The gap between
them is exactly Pearl's gap between rung 1 and rungs 2–3, and it cannot be closed by more
passive data (Part I §9.1).

We also fix:
- **A level/scale L** (a choice of variables V_M and granularity) — understanding is always
  relativized to L (Part IV preliminary, Part V).
- **A question battery Q** — a distribution over questions/interventions/transfers against which M is
  scored. The battery's *coverage* (how far it ranges OOD, across interventions, failures,
  transfers) is what makes the evaluation anti-gameable.

---

## 2. The epistemic ladder: seven distinct achievements

We define seven achievements as **increasing requirements on the model M and the agent A**. Each is
a strict superset of capabilities, and each adds a specific epistemic object (Part III rows). The
ladder is the framework's answer to "distinguish knowing/predicting/modeling/explaining/
understanding/reverse-engineering/mechanistic understanding."

| # | Achievement | What A possesses | Epistemic object added | Pearl rung | Passes which Part-IV criteria |
|---|---|---|---|---|---|
| 0 | **Knowing** | True propositions/facts/observations about S (a parts list, a connectome, measured values, "that" facts) | descriptions, data, phenomena | — (data) | (substrate; none of C1–C18 alone) |
| 1 | **Predicting** | A map that forecasts S's behavior (in-distribution) | statistical/predictive sufficient structure | 1 (assoc.) | C1(in-dist) |
| 2 | **Modeling** | A runnable generative model reproducing S's behavior across observed conditions | a generative/dynamical simulator | 1 (+ generative) | C1, C17(in-dist) |
| 3 | **Explaining** | A model that answers *why/how* questions: asymmetric, relevant, difference-making structure (laws/causes/unifying patterns) | difference-making structure; contrastive answers | 2–3 (some) | C2(partial), C8, C18(partial) |
| 4 | **Understanding** | A *grasped*, *intervention-faithful*, *abstracted-to-difference-makers* model the agent can *use* to answer a broad counterfactual/interventional/transfer battery | invariant, intervention-supporting dependence + agent competence | 2–3 (broad) | C1-OOD, C2, C12, C15, C18 |
| 5 | **Reverse-engineering** | An understanding (4) whose structure is **decomposed into the system's actual organized parts/operations**, validated by part-level intervention | entities+activities+organization mapped to S's parts (3M) | 2–3 + constitutive | + C3, C4, C10/C13, C11 |
| 6 | **Mechanistic understanding** | A reverse-engineering (5) that is **hierarchically consistent across levels** and supplies the **computational *why*** (closed levels + inter-level commuting maps + normative rationale) | multi-level mechanism + relevant-variable/level account + *why* | full | all of C1–C18 (to degree) |

**Reading the ladder.**
- 0→1→2 is the **knowledge-about** zone (Part III left): facts, prediction, generative fit. *This is
  where most high-dimensional data science and much of deep learning sit.* Crucially, **you can
  ascend 0→2 with more data/compute alone.**
- The **understanding line** is between 2 and 3–4: crossing it requires **interventional/
  counterfactual** content that, by Pearl's theorem, *cannot* be obtained from rung-1 data without
  added structure (interventions, multiple environments, or inductive bias). **This is the formal
  location of the Jonas–Kording/Lazebnik gap.**
- 4→5→6 deepens *within* understanding: from "a correct usable causal model" to "decomposed into the
  actual parts" to "multi-level mechanism with the *why*." Lazebnik's "fix the radio" lives at 5;
  Jonas–Kording's "understand the microprocessor" demands 5–6; Hodgkin–Huxley and Nanda et al.'s
  modular-arithmetic circuit are exemplars of 6 (at their level).

**Two theorems (informal).**
- *(T1 — the data ceiling.)* No amount of rung-1 (observational) data moves an agent above the
  understanding line; ascending to ≥3 requires interventions, cross-environment variation, or
  inductive biases that supply causal structure. *(Direct corollary of Pearl's ladder + ICP +
  causal-representation-learning unidentifiability.)*
- *(T2 — the clever-predictor gap.)* For any system with a nontrivial intervention algebra, there
  exist models that maximize rung-1 predictive score yet fail the interventional battery — so
  predictive score is **not** a consistent estimator of understanding. *(This is the formal Jonas–
  Kording statement: a perfectly predictive model of the microprocessor can be mechanistically
  empty.)*

---

## 3. The measurable dimensions of understanding

Understanding (achievements 4–6) is not scalar; it is a **profile** over dimensions. We define each
dimension as a number in [0,1] computed from the model M, the system S, the level L, and the
question battery Q. (Exact estimators are benchmark-specific; Part VII operationalizes them on
ground-truth systems.)

Notation: `ι ~ I_S` interventions; `q ~ Q` questions; `Acc(·)` an accuracy/agreement score (1 =
perfect); `|M|` description length of the model in a fixed parts-vocabulary; `H(S)` an enumeration
length of S's behavior.

### D1. Predictive power — `P`
`P = E_{q ~ Q_pred} Acc(M answers q)`, with `Q_pred` weighted toward **out-of-distribution** and
**novel-kind** queries. *(In-distribution prediction is given near-zero weight — T2.)*
Captures C1. Necessary, low-discriminating alone.

### D2. Counterfactual competence — `CF`
`CF = E_{(x,ι) ~ Q_cf} Acc( d(infer_M(e(x), do_M(ι)))  vs  observe_S(do_S(ι), x) )`
over a **broad, compositionally-generated** set of counterfactuals/interventions. The
*commuting-diagram* score. Captures C2; the **central** dimension. (Equivalent to the expected
agreement of the model's do-distribution with the system's.)

### D3. Intervention capability — `IV`
`IV = ` performance on **goal-directed** interventional tasks: choose ι to achieve a target;
score = achieved/optimal, with side-effect penalty. Captures C9; requires CF to be broad. By
Conant–Ashby, high IV with a *simple* M implies M models S.

### D4. Compression (mechanistic MDL) — `K`
`K = 1 − |M|_parts / H(S)`, where `|M|_parts` is the description length of M **in a vocabulary of
interventionally-meaningful, composable parts** (not arbitrary code). Penalizes both
under-compression (lookup tables, `K→0`) and **opaque** compression (forbidden vocabulary doesn't
count toward parts). Captures C5. *This is the dimension that operationalizes "compression done
right": short **and** in mechanism-parts.*

### D5. Mechanistic faithfulness — `F`
The degree to which M's internal variables/transitions map onto S's actual entities/activities and
*commute under part-level interventions* (causal abstraction / interchange-intervention agreement;
3M / mutual manipulability). `F = E_{ι on parts} Acc( interchange-intervention in M  vs  in S )`.
Captures C10/C13 (correctly, including "distributed" verdicts) and is what separates **modeling**
(F may be 0) from **reverse-engineering** (F high). *The dimension Rosen's commuting diagram and
Geiger et al.'s causal abstraction make precise.*

### D6. Hierarchical consistency — `HC`
Measures the **decomposability profile** (Part V): over candidate scales {L_k}, the fraction for
which M provides a **closed, low-dimensional, intervention-respecting** description, *and* the maps
between adjacent levels **commute** (causal abstraction). `HC` rewards recovering genuine levels and
**correctly reporting** where none exist (no penalty for absent levels that are *shown* absent;
penalty for *imposing* false levels). Captures C14/C16/C6. Also yields the **integration index**
(1−HC at a scale ≈ degree of holism there; relates to Φ/synergy).

### D7. Modularity — `MO`
Degree to which M recovers near-decomposable modules with **thin, stable interfaces** validated by
**intervention locality** (interventions inside a module stay inside). `MO = ` interface sparsity ×
intervention-locality agreement. Captures C13/C11. Distinct from HC (vertical) — MO is horizontal.

### D8. Transferability — `T`
`T = E_{S' ~ related systems} [ understanding-score of M transported to S' ]` — how well M (or its
abstract form) predicts/intervenes on *different* systems sharing structure. Captures C12; the
signature of having recovered **invariant/abstract** structure (ICP/Kitcher). Hard to game.

### D9. Robustness — `R`
Two senses, both scored: (a) M **explains** S's robustness/fragility (predicts failure modes,
degradation — C15); (b) M's *own* verdicts are **stable** under nuisance variation (measurement
noise, reparametrization, benign interventions). `R` combines both. Captures C15.

### D10. Generality / breadth — `B`
The *range* of phenomena/contrast-classes/regimes M covers (how many distinct why-questions and
regimes it answers). Captures the **breadth** axis (Kitcher unification; novel-kind prediction C22).

### D11. Explainability / intelligibility — `X`
The agent-relative dimension (de Regt): can a bounded agent **draw qualitative consequences, answer
w-questions, and produce a step-by-step generative account** from M without brute calculation?
Operationalized via the **illusion-of-explanatory-depth test** (demand the stepwise mechanism) and
*human/agent counterfactual prediction from M alone*. Captures C18(grasp side)/notion 21. Guards
against "correct but ungraspable" models (a 10^9-parameter faithful sim has high F, low X).

### D12. Depth — `Δ`
Two coupled senses: (a) **range of invariance** of M's relations under intervention/background
change (Woodward–Hitchcock); (b) **proximity to the computational *why*** (Marr) — does M explain
*why* the mechanism is organized as it is (normative/optimality account that predicts structure)?
`Δ` combines invariance-range with why-content. Captures C18.

### D13. Causal completeness — `CC`
Fraction of S's behavior at level L for which M identifies the **complete set of difference-makers**
(no missing causes producing unexplained variance under intervention; no black-box "filler" terms in
the Craver sense). `CC = 1 − (unexplained interventional variance)`. Captures the sketch→how-actually
gradient (Craver). Distinguishes a **mechanism sketch** (low CC, has black boxes) from a **complete**
mechanism (high CC).

### Relationships among dimensions (not independent)
- **Gating:** `F, CF > 0` are *prerequisites* for the understanding zone; `P, K` alone (knowledge-
  about) can be high with `F=CF=0` (the clever predictor) — this *is* T2.
- **Vertical/horizontal:** `HC` (across scales) and `MO` (within a scale) jointly encode structure.
- **Object vs. competence:** {F, CC, HC, MO, K} are *object* dimensions (what structure M recovered);
  {P, CF, IV, T, R, B, X, Δ} are *competence/manifestation* dimensions (what A can do with M). The
  master criterion (Part IV) requires **both** clusters > thresholds.

---

## 4. The Understanding–Knowledge Gradient (UKG)

We summarize the profile with a single graded construct that makes the knowledge/understanding
distinction explicit.

Define two aggregate indices over the dimensions:

- **Knowledge-about index** `KA = g(P, K, descriptive-coverage)` — predictive/compressive/
  descriptive achievement *without* requiring causal-mechanistic content. (High for a great
  predictor.)
- **Understanding-of index** `UO = h(CF, IV, F, HC, MO, T, R, Δ, CC, X)` — the causal-mechanistic-
  hierarchical-competence content, **gated** so that `UO ≈ 0` whenever `F ≈ 0` or `CF ≈ 0`
  regardless of `P, K`. (i.e., `UO = min(gate, weighted-mean)` with `gate = φ(F, CF)`.)

Then the **UKG position** of a (model, agent, system, level) tuple is the pair `(KA, UO)`, and the
**understanding gap** is `G = KA − UO`.

- **Pure knowledge-about** (top-left): high `KA`, `UO≈0`, large gap `G`. *The microprocessor predictor;
  the fMRI decoder; the SAE-as-reconstruction; the LLM as-such.* **This is the Jonas–Kording/
  Lazebnik regime, now a coordinate.**
- **Understanding** (upper-right): high `KA` *and* high `UO`, small gap. *Hodgkin–Huxley; the
  reverse-engineered modular-arithmetic circuit; a validated gene-regulatory SCM; the radio fixed by
  an engineer.*
- **Shallow/none** (lower-left): low both.
- *(Empty quadrant)* high `UO`, low `KA` is essentially impossible — understanding entails
  predictive/compressive ability — which is why `KA` is necessary-but-not-sufficient and the
  *interesting* failure is always the large-gap top-left.

**The thesis as a UKG statement:** *improving prediction, representations, or accuracy moves a system
**rightward in `KA`** but **not upward in `UO`** unless it adds interventional/mechanistic/
hierarchical content; therefore `KA` is not a proxy for `UO`, and reporting `KA` while claiming `UO`
is the central methodological error this framework is designed to catch.* Every method in
`tables/methods_comparison.md` is placed by its `(KA, UO)` signature.

---

## 5. Formal definition of scientific understanding (the proposed definition)

Pulling the above together:

> **Definition (Scientific Understanding).** An agent A *understands* a system S at level L to
> degree d iff A possesses a model M and an encode/decode/inference apparatus such that:
>
> 1. **(Faithful commuting structure — object.)** The modeling relation commutes under the
>    intervention algebra at L: for interventions ι and observations x in the relevant battery,
>    `d(infer_M(e(x), do_M(ι))) ≈ observe_S(do_S(ι), x)` — i.e., `F`, `CF`, `CC` exceed thresholds;
>    M tracks S's *difference-making, intervention-supporting* structure, not merely its
>    observational statistics.
> 2. **(Mechanism-structured compression — object.)** M is short in a vocabulary of
>    interventionally-meaningful, composable parts organized into S's actual (possibly hierarchical)
>    structure: `K`, `MO`, `HC` exceed thresholds; where S admits closed low-dimensional levels, M
>    recovers them, and where it does not, M reports the integration.
> 3. **(Exercisable competence — manifestation.)** A can *use* M to answer a broad,
>    systematically-generated, anti-gameable battery — OOD/novel-kind prediction, counterfactuals,
>    optimal intervention, failure prediction, cross-system transfer — and to produce a step-by-step
>    generative account: `P(OOD), IV, T, R, B, X, Δ` exceed thresholds.
>
> The **degree** d is the (gated, weighted) aggregate `UO` of these dimensions at level L; the
> understanding is **mechanistic** (achievement 6) when additionally `HC` spans multiple levels with
> commuting maps and `Δ` includes the computational *why*. **Knowledge about** S is the achievement
> of (a subset of) the predictive/descriptive dimensions {P, K, description} **without** clause 1
> (no `F`/`CF`) — the large-gap regime.

The definition is: **relativized** (L, battery), **graded** (d ∈ [0,1]), **anti-gameable**
(interventional/OOD battery, mechanism-parts vocabulary), **multi-realizable-aware** (faithfulness
is to S's *intervention behavior at L*, allowing legitimate abstraction), and **operational**
(every clause maps to a measurable dimension and to a Part-VII benchmark).

---

## 6. How the framework recovers and sharpens the literature

- **Hempel/prediction** = achievement 1 (rung 1); the framework explains *why* it fails the
  asymmetry/relevance cases (no `F`/`CF`).
- **Salmon/Woodward/Pearl** = the `CF`/`IV`/`CC` core (clause 1); depth = `Δ` (range of invariance).
- **Kitcher/MDL/AIT** = `K` and `B` (compression + breadth), *constrained* to mechanism-parts so
  unification can't be opaque.
- **Craver/MDC mechanists** = achievement 5 + `F`/`CC`/`MO` (sketch→how-actually = `CC` gradient;
  mutual manipulability = the `F` estimator; 3M = the encode/decode map).
- **Simon/RG/causal abstraction/causal emergence** = `HC` (decomposability profile; closed levels;
  commuting maps; max-EI level).
- **Rosen** = the commuting modeling relation itself (the definition's clause 1, generalized).
- **de Regt/cognitive science** = `X` (intelligibility/grasp) — keeping the agent in the picture so
  a correct-but-ungraspable artifact isn't counted as understanding.
- **Causal representation learning / interpretability** = the *methods* that try to raise `F`/`CF`
  inside learned systems; the framework's `(KA, UO)` placement diagnoses which actually do (Part VIII).

The pay-off: a single construct in which "understanding ⊋ prediction ⊋ data," "compression is
necessary-not-sufficient," "hierarchy is the tractability-enabler," and "the test must be
interventional/OOD" are all *consequences*, and in which any method or study can be located by its
measured `(KA, UO)` profile.
