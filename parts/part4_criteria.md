# Part IV — Criteria for Declaring a System Understood

This is the operational core. We take each candidate criterion proposed in the brief, give it a
crisp statement, then evaluate it on three axes:

- **Necessary?** Must any understood system satisfy it?
- **Sufficient?** Does satisfying it guarantee understanding?
- **Gameable?** Can it be passed *without* understanding (the crucial question, given the thesis)?

We then assemble the surviving criteria into a **joint test** (no single criterion is both
necessary and sufficient; understanding is a *profile*, not a checkbox — formalized in Part VI).

Two preliminaries fix the evaluation:

1. **Relativization.** "Understood" is always *relative to a level/contrast class and a question
   set* (van Fraassen; Marr). "Is the microprocessor understood?" is ill-posed; "Is its
   instruction-decoding mechanism understood at the logic-gate level?" is well-posed. Every
   criterion below is implicitly relativized to a *target level* and a *space of questions/
   interventions/transfers*.
2. **Anti-gaming principle.** Because the thesis is that prediction can masquerade as
   understanding, *every* criterion must be stress-tested against a "**clever predictor**"
   adversary — a system (e.g., a giant lookup table, an overfit network, a memorizer) that aces the
   nominal metric without any mechanism. A criterion survives only if the clever predictor fails it
   *or* can pass it only by *acquiring the mechanism*.

---

## C1. Can predict unseen behavior

- **Statement.** Correctly predicts behavior on inputs/conditions not used to build the model.
- **Necessary?** **Weakly yes** — an understood system's behavior should be predictable *in the
  regimes the understanding covers*. (Caveat: one can understand *why* a system is unpredictable —
  e.g., chaos — so the prediction is of the *right kind*: statistics, attractor, Lyapunov bounds.)
- **Sufficient?** **No.** The flagpole/barometer and the lookup table predict without understanding.
- **Gameable?** **Highly**, *if "unseen" means same-distribution*. Much less so if "unseen" means
  **out-of-distribution / novel regimes / novel kinds** (notion 22). Recommendation: only **OOD /
  extrapolative / novel-kind** prediction counts as evidence; in-distribution prediction is near-zero
  evidence.
- **Verdict.** Necessary (in OOD form), not sufficient. Keep, but require OOD.

## C2. Can answer counterfactuals

- **Statement.** Correctly answers a broad, systematically generated set of "what if X had been
  different" questions.
- **Necessary?** **Yes.** Understanding *is* (in large part) grasp of dependence relations
  (Woodward, Pearl rung 3); failure to get counterfactuals right is failure to understand.
- **Sufficient?** **Nearly, given breadth.** If a model answers *all* relevant counterfactuals
  correctly, it has the system's causal structure at that level. The residual gaps: it may lack the
  *why* (computational rationale) and the *organized decomposition* (it could be a correct but
  monolithic counterfactual oracle).
- **Gameable?** **Hard to game by memorization** (the space of counterfactuals is combinatorially
  large), *provided* the question set is generated to require composition/extrapolation, not lookup.
- **Verdict.** Necessary and the strongest single criterion; "sufficient-leaning" when broad. The
  centerpiece of the operational battery.

## C3. Can repair the system

- **Statement.** Given a malfunction, localize the fault and restore function (Lazebnik's test).
- **Necessary?** **No** (understanding can outrun feasible repair: we understand stellar fusion but
  cannot repair a star; some faults are irreversible).
- **Sufficient?** **No, but strong** — repair requires the normal mechanism (counterfactual: what it
  *should* do), fault localization (decomposition), and correct intervention. The gap:
  **module-swap repair** can succeed by exploiting modularity without full mechanistic insight
  ("replace the board that tests bad").
- **Gameable?** **Partially** via trial-and-error part-swapping; mitigated by requiring **targeted,
  first-try, minimal** repairs and **explanation of the fault**.
- **Verdict.** Powerful *practical* indicator (especially for engineered/biological systems); neither
  strictly necessary nor sufficient. Keep as a high-value benchmark (Part VII).

## C4. Can redesign the system

- **Statement.** Produce a modified system with predictably altered behavior, or rebuild the function
  from components (Feynman's "what I cannot create…").
- **Necessary?** **No** (understanding a *natural* system doesn't require ability to rebuild it).
- **Sufficient?** **No** — one can build/evolve a working system without understanding it (evolved
  FPGAs, trained nets: *we built it and don't understand it* is the entire premise of
  interpretability). Design shows sufficiency of *a* mechanism, not identification of *the* mechanism.
- **Gameable?** **Yes**, via blind search/optimization that yields function without insight.
- **Verdict.** Strong indicator for "understanding a *function*"; weak for "understanding a *given*
  system." Keep as benchmark with the build-without-understanding caveat.

## C5. Can compress the mechanism

- **Statement.** Provide a description of the mechanism much shorter than an enumeration of its
  behavior, in a vocabulary of meaningful parts.
- **Necessary?** **Yes**, in the *mechanism-structured* sense: an understood system has a short
  description *in terms of parts/operations* (Simon's redundancy; MDL model-part). A model the size
  of the data has found no structure.
- **Sufficient?** **No** — opaque/predictive compression doesn't understand (Part II.2; IB;
  ε-machine caveats).
- **Gameable?** **Yes** by opaque compressors (huge polynomials, distillation into a smaller black
  box). Mitigation: require the short description be **in interventionally meaningful, composable
  parts** and **causally validated** — i.e., couple C5 with C2/C7.
- **Verdict.** Necessary (as *mechanistic* compression); not sufficient. Becomes our **MDL-of-mechanism**
  dimension (Part VI), explicitly *not* MDL-of-behavior.

## C6. Can derive macroscopic behavior from microscopic rules

- **Statement.** From the micro-level model, derive (analytically or via principled coarse-graining)
  the macro-level phenomena.
- **Necessary?** **No, in general** (multi-level autonomy/emergence means macro understanding need
  not route through micro — we understand thermodynamics without deriving it from QM; Anderson). It
  *is* necessary for the specific goal of **inter-level understanding**.
- **Sufficient?** **No** — micro→macro derivation can be a brute simulation (weak emergence) that
  reproduces without illuminating; and getting macro right doesn't establish the *macro-level*
  mechanism is itself understood.
- **Gameable?** Via brute-force simulation (derives without insight).
- **Verdict.** Necessary *for cross-scale understanding specifically*; otherwise neither. Pairs with
  C7-down and the hierarchy criteria (Part V).

## C7. Can infer microscopic rules from macroscopic behavior (the inverse)

- **Statement.** From macro-observations, recover the micro-mechanism (an inverse problem).
- **Necessary?** **No** (and often impossible — many micro-realizations yield the same macro;
  multiple realizability; ill-posed inverse).
- **Sufficient?** **No**, but a *successful, validated* inference is strong evidence (it has solved
  the hard identifiability problem). 
- **Gameable?** The inverse problem's **non-identifiability** is the issue, not gaming: many wrong
  micro-models fit the macro. Mitigation: validate by **intervention/transfer** (does the inferred
  micro-model predict novel macro under perturbation?).
- **Verdict.** Neither necessary nor sufficient; a *bonus* capability marking deep understanding when
  achieved and validated. The asymmetry between C6 and C7 is itself an important lesson (forward
  derivation ≠ inverse recovery).

## C8. Can identify causal variables

- **Statement.** Pick out the variables that are genuine difference-makers (vs. epiphenomena/
  proxies) — solve the variable-choice problem at the target level.
- **Necessary?** **Yes.** You cannot have the causal/mechanistic structure without its relata; wrong
  variables ⇒ wrong (or no) mechanism. This is logically prior to most other criteria.
- **Sufficient?** **No** — knowing the variables isn't knowing the organized dynamics among them.
- **Gameable?** Correlational variable selection (e.g., feature importance) finds *predictive* not
  *causal* variables; mitigated by **invariance across environments** (ICP) and **intervention**.
- **Verdict.** Necessary and foundational; not sufficient. The "right variables / right level"
  precondition (links to Part V and to the representation problem in interpretability).

## C9. Can intervene optimally

- **Statement.** Choose the intervention that best achieves a goal (max effect, min side-effect),
  and predict its outcome.
- **Necessary?** **No** (understanding doesn't require *optimization* capability per se).
- **Sufficient?** **No**, but **near-criterial in conjunction with C2**: optimal intervention
  requires an accurate, broad causal model (you must predict outcomes of *many candidate*
  interventions to pick the best) — by the Good Regulator theorem, optimal+simple control implies a
  model. 
- **Gameable?** Model-free optimization (RL) can find good interventions without an inspectable model.
- **Verdict.** Strong indicator (via its dependence on broad counterfactual competence); not strictly
  necessary or sufficient alone.

## C10. Can localize functions

- **Statement.** Map functions/operations to parts (decomposition + localization).
- **Necessary?** **Only if the system is decomposable.** For non-decomposable/distributed/superposed
  systems, *insisting* on localization is a *failure mode*, not a criterion (Lazebnik; superposition).
  What is necessary is to **correctly characterize the (possibly distributed) organization** —
  including establishing that it is *not* cleanly localizable.
- **Sufficient?** **No** — localization gives a parts-map, not the activities/dynamics (connectome
  lesson).
- **Gameable?** **Yes and dangerously** — spurious localization (a region/neuron "lights up") is the
  classic over-claim; mitigated by **mutual manipulability** (both bottom-up and top-down
  interventions) and by checking against distributed-coding nulls (PID synergy, superposition).
- **Verdict.** Conditionally necessary (when decomposable); a *failure mode* when forced. Reframe as:
  "**correctly recover the actual organization, decomposable or not.**"

## C11. Can compose explanations

- **Statement.** Combine explanations of parts/sub-mechanisms into an explanation of the whole, and
  of simple cases into complex ones.
- **Necessary?** **For *scalable* understanding of complex systems, effectively yes** — without
  compositionality you cannot build whole-system understanding from tractable pieces (Simon;
  it's how all engineering understanding works).
- **Sufficient?** **No** (composition presupposes correct part-explanations and correct interfaces).
- **Gameable?** Hard to game — composition either correctly predicts the whole's behavior from parts
  or it doesn't (a stringent test of interface correctness).
- **Verdict.** Necessary for scalable/complex-system understanding; a key dimension (compositionality/
  modularity). Its *failure* (parts understood, whole not) precisely marks **emergence/synergy**.

## C12. Can transfer explanation across systems

- **Statement.** Apply the explanatory account to a *different* system with shared structure and
  correctly predict/intervene there.
- **Necessary?** **No** (one can understand a unique system). 
- **Sufficient?** **No**, but a strong indicator of **depth/breadth** — transfer works only if the
  account captured *invariant, abstract structure* rather than surface correlations (ICP; Kitcher
  unification).
- **Gameable?** Hard — spurious accounts don't transfer (that's why transfer is a good test of
  having recovered real structure).
- **Verdict.** Excellent indicator of depth/breadth; neither necessary nor sufficient. Becomes the
  **transferability** dimension.

## C13. Can discover latent modularity

- **Statement.** Recover the system's near-decomposable module structure and interfaces when present.
- **Necessary?** **No** (some systems aren't modular). But discovering *whatever* modularity exists
  is necessary for tractable understanding of *modular* systems.
- **Sufficient?** **No** (modules + nothing about their dynamics ≠ understanding).
- **Gameable?** Community-detection/clustering can impose modules that aren't functional; mitigated by
  validating modules **interventionally** (do module boundaries predict intervention locality?).
- **Verdict.** Conditionally necessary; a structural enabler (Part V). Closely tied to C10/C11.

## C14. Can recover hierarchy

- **Statement.** Recover the multi-level organization (levels, scales, interfaces) and the maps
  between them.
- **Necessary?** **For complex systems, near-necessary in practice** (Part V argues this); not
  conceptually necessary for simple systems.
- **Sufficient?** **No.**
- **Gameable?** Imposed hierarchies (arbitrary coarse-graining) that don't *close* mislead; mitigated
  by requiring **closure/commuting** under the coarse-graining (causal abstraction; RG; max-EI level).
- **Verdict.** Near-necessary for complex systems; constitutive of *deep* understanding. The
  **hierarchical consistency** dimension.

## C15. Can explain failures

- **Statement.** Predict and explain *how and why* the system fails, degrades, or produces errors.
- **Necessary?** **Strongly indicative, arguably necessary for *complete* understanding** — knowing
  the failure modes requires knowing the mechanism's boundary conditions and weak points (a model
  that explains only successes has likely fit the success regime).
- **Sufficient?** **No.**
- **Gameable?** Hard — failure prediction requires the mechanism's limits, not just its typical
  behavior; a correlational model rarely predicts *novel* failure modes.
- **Verdict.** Excellent, under-used indicator (especially for engineered/AI systems: predicting
  adversarial/OOD failures is a strong understanding test). Keep as a benchmark and as part of
  robustness/depth.

## C16. Can explain emergence

- **Statement.** Account for why/how macro-properties arise that are not properties of parts —
  including *why the macro-level is autonomous* (which micro-details are irrelevant).
- **Necessary?** **For systems exhibiting emergence, yes** (an account silent on the emergent
  macro-behavior is incomplete).
- **Sufficient?** **No.**
- **Gameable?** Brute simulation "shows" emergence without explaining it; genuine explanation
  identifies the *relevant variables* and *why* micro-detail washes out (RG/causal emergence).
- **Verdict.** Necessary for emergent systems; tied to C6/C14 and to the "right level" problem.

## C17. Can generate faithful simulations

- **Statement.** Produce simulations that match the system across conditions, *including under
  intervention*.
- **Necessary?** **No** (understanding need not be packaged as a runnable sim; and unsimulable-in-
  practice systems can be understood at an abstract level).
- **Sufficient?** **No** (faithful black-box sim = weak emergence, predicts-without-illuminating).
- **Gameable?** **Yes** by overfit simulators — *unless* faithfulness is required **under
  intervention/counterfactual** (then the sim must be causally correct ≈ a mechanism).
- **Verdict.** Indicator; its evidential value is exactly proportional to whether faithfulness is
  tested **off-distribution and under intervention** (collapses into C1-OOD + C2).

## C18. Can explain *why* rather than merely *how*

- **Statement.** Provide the **computational-level / teleological / design rationale** — what problem
  the mechanism solves and why it is organized as it is (Marr's *why*; normative theories).
- **Necessary?** **For the *deepest* understanding, yes;** for *mechanistic* (how-actually)
  understanding at a level, not strictly — one can know *how* without knowing *why*. But the *why*
  often *is* what makes a mechanism intelligible and transferable.
- **Sufficient?** **No** (a why/normative story without the how is a how-possibly account).
- **Gameable?** Just-so teleological stories are cheap; mitigated by requiring the *why* to **predict
  structural/mechanistic features** (optimality predicting the mechanism, as efficient-coding
  predicts receptive fields).
- **Verdict.** Constitutive of *deep* understanding (the "depth toward the computational level"
  dimension); complements rather than replaces the how-actually mechanism.

---

## Synthesis: no silver bullet; understanding is a profile

| Criterion | Necessary? | Sufficient? | Main gaming risk | Mitigation |
|---|---|---|---|---|
| C1 Predict unseen | Yes (OOD only) | No | in-distribution lookup | require OOD/novel-kind |
| C2 Counterfactuals | **Yes** | Near (if broad) | memorize | combinatorial, compositional question set |
| C3 Repair | No | No (strong) | part-swap trial&error | first-try, minimal, +explain fault |
| C4 Redesign | No | No | blind search builds it | require predicted-behavior spec |
| C5 Compress mechanism | Yes (mech-structured) | No | opaque compression | parts-vocabulary + causal validation |
| C6 Macro from micro | only cross-level | No | brute simulation | principled coarse-graining + closure |
| C7 Micro from macro | No | No (bonus) | non-identifiability | intervention/transfer validation |
| C8 Identify causal variables | **Yes** | No | predictive≠causal selection | invariance(ICP)+intervention |
| C9 Intervene optimally | No | No (strong) | model-free RL | require outcome prediction across candidates |
| C10 Localize functions | conditional | No | spurious localization | mutual manipulability; distributed nulls |
| C11 Compose explanations | Yes (scalable) | No | — (hard to game) | predict whole from parts |
| C12 Transfer explanation | No | No (strong) | — (hard to game) | cross-system prediction+intervention |
| C13 Discover modularity | conditional | No | imposed modules | interventional module validation |
| C14 Recover hierarchy | near (complex sys) | No | imposed hierarchy | closure/commuting requirement |
| C15 Explain failures | near | No | — (hard to game) | predict novel failure modes |
| C16 Explain emergence | for emergent sys | No | brute sim | identify relevant variables + why |
| C17 Faithful simulation | No | No | overfit sim | faithfulness under intervention |
| C18 Explain *why* | for deepest | No | just-so stories | why predicts mechanism |

**Three conclusions:**

1. **No single criterion is both necessary and sufficient.** The closest to *necessary*:
   counterfactual competence (C2), causal-variable identification (C8), mechanistic compression
   (C5), and (for complex systems) hierarchy/compositionality (C11/C14). The closest to *sufficient*
   in conjunction: a *broad* C2 + C8 essentially delivers the causal structure at a level.

2. **The necessary core is the causal/mechanistic/hierarchical cluster; the sufficient evidence is
   the competence battery exercised off-distribution and under intervention.** Understanding is
   established when a model (a) recovers organized, intervention-validated, hierarchically-consistent
   structure (the *object*), **and** (b) supports the competences C1-OOD, C2, C3/C4, C11, C12, C15
   (the *manifestation*). This dual object+competence structure is exactly Part VI's framework.

3. **Every criterion is gameable by a "clever predictor" *unless* it is evaluated off-distribution
   and/or under intervention.** This is the single most important methodological lesson and the
   formal expression of the Jonas–Kording/Lazebnik thesis: **the test of understanding must probe
   regimes the system-builder/predictor did not fit.** We therefore adopt as the **master criterion**:

   > **A system is understood (at level L, to degree d) to the extent that an agent possesses a
   > model that correctly answers a broad, systematically-generated battery of counterfactual and
   > interventional questions at level L — including novel-kind, off-distribution, failure-mode, and
   > cross-system-transfer questions — using a description that is short and expressed in
   > interventionally-meaningful, composable parts organized into the system's actual
   > (possibly hierarchical) structure.**

   This master criterion is *gradable* (degree d), *relativized* (level L, question battery),
   *anti-gameable* (off-distribution + intervention), and *decomposes* into the measurable dimensions
   of Part VI.
