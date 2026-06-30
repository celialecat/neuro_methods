# Open Problems

Ordered roughly from foundational to applied. Each is stated as a question with why it matters and
what a solution would look like in the framework's terms (Part VI).

## Foundational

1. **The variable/level-choice problem.** Every causal/mechanistic account presupposes the right
   variables and level, but *finding* them is unsolved in general (the representation problem under
   the SCM; the relevant-variables problem under RG; superposition under interpretability). *What
   principled, general procedure selects the explanatory variables/level?* Candidates: max effective
   information (causal emergence), closure-under-coarse-graining, ε-machine causal states — but each
   is predictive- or measure-dependent. **Until solved, `F`/`HC` are only well-defined relative to a
   hand-chosen level.**

2. **Identifiability of mechanism from finite interventions.** T1 says observational data can't
   cross the understanding line; but *how many and which* interventions suffice to identify a
   mechanism (raise `F`/`CF` to threshold) for a given system class? A sample-complexity theory of
   *understanding* (analogous to PAC learning for prediction) is missing.

3. **Multiple realizability vs. faithfulness.** Faithfulness (`F`) is to the system's intervention
   behavior *at a level*, deliberately allowing abstraction — but *how abstract is too abstract?*
   When do two systems with the same `(KA, UO)` profile count as "the same mechanism understood"
   vs. "different mechanisms, same abstraction"? Needs a principled equivalence relation on
   mechanisms (causal-abstraction isomorphism is a start).

4. **Quantifying the predictive/mechanistic gap.** T2 asserts predictive score is not a consistent
   estimator of `UO`. Can we *bound* `UO` given `KA` and structural facts about the system (e.g.,
   its integration index)? A formal "understanding gap" inequality `G = KA − UO ≥ f(integration)`
   would turn the thesis into a theorem with constants.

5. **Holism without decomposition.** For genuinely integrated systems (high Φ / synergy / no closed
   level), what does *understanding* concretely consist of, beyond "demonstrating irreducibility"?
   Is there a positive theory of understanding for non-decomposable systems (global dynamical/
   order-parameter accounts), or is irreducibility a hard ceiling on mechanistic understanding?

6. **Compression vs. faithfulness trade-off.** `K` (mechanism-MDL) and `F`/`CC` can conflict — the
   shortest mechanism-parts description may omit difference-makers; the complete one may be
   incompressible. Is there an optimal point (an "understanding frontier" analogous to the IB
   curve), and is it unique?

7. **The status of *why* (computational level).** Can the normative/teleological *why* (`Δ`) be made
   as rigorous and falsifiable as the *how* (`F`/`CF`), beyond "optimality predicts structure"? When
   is a *why* explanation testable vs. a just-so story?

## Methodological

8. **Faithfulness metrics that don't collapse to plausibility.** Causal-abstraction/DAS can overstate
   faithfulness if the alignment search is too flexible (an identifiability worry inside the metric).
   Robust, regularized, OOD-validated `F` estimators are needed — and agreed-upon for the field.

9. **Scalable mechanism recovery.** Activation patching and circuit analysis are labor-intensive and
   may not scale to frontier models; SAEs scale but have uncertain faithfulness. *Can `F`-bearing
   methods scale to systems with 10^9–10^12 parameters/neurons?* This is the dimension-19
   (scalability) problem made concrete and may be the binding constraint for both brains and LLMs.

10. **Fat-handed / off-distribution interventions.** Interventions (lesions, ablations, patches) push
    systems off their normal operating manifold, creating artifacts that masquerade as mechanism.
    Principled "on-manifold" or distribution-preserving intervention design is open in both
    neuroscience and interpretability.

11. **Benchmarks with ground-truth understanding.** Part VII's suite needs to be *built and
    standardized* (with predictor controls and decomposability sweeps) so methods can be compared on
    `(KA, UO)` rather than on prediction alone. Existing pieces (microprocessor, Tracr, IOI,
    causal-abstraction benchmarks) are not yet unified under common `F`/`HC`/`CC` scoring.

12. **Measuring `X` (intelligibility) objectively.** Grasp is agent-relative; the illusion of
    explanatory depth shows self-report is unreliable. Operational, inter-subjective intelligibility
    measures (step-by-step reconstruction tests; agent-counterfactual-from-model tests) need
    development and validation.

## Domain-specific

13. **The decomposability profile of the brain.** Empirically, *where* and *at what scale* is the
    brain near-decomposable vs. integrated? The framework predicts mechanistic methods will succeed
    in the former and stall in the latter; mapping this profile is a concrete research program.

14. **Do SAE features cross the understanding line?** Resolve whether sparse-dictionary features are
    the model's *causal* units (high `F` after intervention) or reconstruction artifacts — including
    feature splitting/absorption and whether feature inventories *compose* into clean circuits
    (`MO`/`HC`).

15. **Understanding emergent capabilities of LLMs.** Are in-context learning, chain-of-thought, and
    "emergent" abilities understandable as composed circuits (achievement 5–6), or are they
    genuinely integrated/synergistic (Part V holism)? This is the highest-stakes instance of the
    whole question.

16. **Closed-loop / inside-out systems.** Most methods assume an open-loop stimulus→response framing;
    brains (Buzsáki) and embodied agents are closed-loop. Extending `F`/`CF` to closed-loop,
    self-generated-dynamics settings is open.

17. **Transfer of *understanding* (not just models) across systems.** When does an explanation of
    system S license understanding of S′ (the `T` dimension)? A theory of explanatory transfer/
    analogy with guarantees would unify Kitcher-unification with mechanistic accounts.

## Meta

18. **Is "understanding" one concept or many?** The framework treats it as a profile; but perhaps
    "understanding" fractures into distinct, non-comparable goods (predictive vs. mechanistic vs.
    normative) with no single aggregate `UO`. Whether the dimensions admit a meaningful scalar
    aggregate — or only a Pareto frontier — is itself open.

19. **Normativity: how much understanding is *enough*?** Thresholds in the definition are
    context/stakes-dependent (a bridge vs. a curiosity). A decision-theoretic account tying required
    `UO` to the cost of being wrong (especially for AI safety) is needed.

20. **Understanding by machines.** If an AI system recovers a faithful, hierarchical, interventionally-
    validated mechanism that no human can grasp (high `F`/`HC`, low human-`X`), is the system
    *understood*? This forces the question of whether understanding is essentially *human*-agent-
    relative or can be *agent-neutral* — directly relevant to automating interpretability and
    science itself.

## Raised by Part IX (deep theory)

21. **Computing the ι-machine.** The ι-machine (Part IX §1) is well-defined but, like the ε-machine,
    generally hard to infer — and harder, since it needs interventional sampling. Is there a tractable
    estimator of `C_ι` (or of the gap `C_ι − C_μ`) for realistic systems, and a state-merging
    algorithm under interventions analogous to CSSR for ε-machines?

22. **Testing the Genesis Principle.** The Provenance–Decomposability prediction (Part IX §4.3) —
    that achievable mechanistic faithfulness orders as design > regularized optimization >
    unconstrained optimization for behavior-matched systems — is runnable on the Part-VII suite but
    has not been run. Does it hold, and where exactly does the ordering break?

23. **Interpretability-by-construction.** If intelligibility is imprinted by the generator, *which*
    training-time pressures (modularity priors, bottlenecks, sparsity, curricula) most raise post-hoc
    `F` per unit of capability lost? Is there a quantifiable intelligibility/performance trade-off
    (an analogue of the rate–distortion curve)?

24. **Locating the understanding horizon.** Are there complex systems (brains, frontier models) for
    which *no* closed coarse-graining brings `C_ι` within a bounded agent's variety `V(A)`? A
    constructive criterion for "beyond the horizon at level L" — versus "we just lack the right
    level" — would turn a conjecture into a decidable property.

25. **Computing human-graspable quotients.** If an automated system holds a faithful ι-machine, can we
    *algorithmically* compute the maximal quotient that remains 𝓘-closed *and* fits human variety/
    intelligibility constraints? This is the formal statement of "automated interpretability as
    translation" (Part IX §5.4).
