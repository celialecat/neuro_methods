# Taxonomy Table of Notions of Understanding

Compact companion to Part II. Columns: **epistemic object**, **cluster**, **verdict**
(Constitutive / Necessary / Sufficient / Indicator / Neither), **gameable by a clever predictor?**,
**maps to UKG dimension(s)** (Part VI).

| # | Notion | Epistemic object | Cluster | Verdict | Gameable? | UKG dimension(s) |
|---|---|---|---|---|---|---|
| 1 | Prediction | predictive map / regularity | predictive | Necessary (OOD only); not sufficient | yes (in-dist) | P |
| 2 | Compression | short generative code | predictive | Necessary (mech-structured); not sufficient | yes (opaque) | K |
| 3 | Simulation | runnable generative model | competence/predictive | Necessary-ish; not sufficient | yes (overfit/1:1) | (model) → F,CF if commuting |
| 4 | Explanation | difference-making/mechanistic structure | causal/mechanistic | **Constitutive** | hard (if causal) | CF,CC,Δ |
| 5 | Intervention | intervention-supporting dependence | causal | **Necessary (core)** | no (rung-2) | IV,CF |
| 6 | Abstraction | minimal difference-making/relevant-variable description | abstraction/level | **Constitutive** of form; Necessary | partial | K,HC,Δ |
| 7 | Decomposition | entities+activities+organization | mechanistic | Constitutive (if decomposable); else the difficulty | no (if intervention-validated) | F,MO |
| 8 | Counterfactual competence | structural counterfactuals (rung 3) | causal/competence | **Necessary; near-criterial** | hard (combinatorial) | CF |
| 9 | Causal structure | SCM / causal graph + mechanisms | causal | **Constitutive/core**; Necessary | no | F,CF,CC |
| 10 | Generative modeling | data-generating process | predictive/generative | Necessary (synthesis sense); sufficient iff true mechanism | yes (likelihood-equiv.) | F (if causal), K |
| 11 | Transfer / generalization | invariant/portable structure | competence | Necessary/strong indicator | hard | T,B,Δ |
| 12 | Repair | mechanism + symptom→fault→fix mapping | competence | Sufficient-leaning indicator; not necessary | partial (part-swap) | CF,F,MO (C3) |
| 13 | (Re)design | constructive sufficient recipe | competence | Indicator (function); weak for given system | yes (blind search) | F,K (C4) |
| 14 | Modularity | module decomposition + interfaces | mechanistic/structural | Constitutive (tractability); conditional necessary | yes (imposed) | MO |
| 15 | Robustness explanation | stabilizing mechanisms (feedback/redundancy) | mechanistic | Constitutive for robust systems; a dimension | hard | R (C15) |
| 16 | Invariance | invariants/symmetries | causal/abstraction | **Constitutive/Necessary** | no | Δ (range of invariance), T |
| 17 | Compositionality | grammar/algebra of mechanism | mechanistic/structural | **Constitutive** of scalable understanding | hard | MO,B (C11) |
| 18 | Generalization across regimes/scales | multi-regime-valid theory | competence/abstraction | Necessary/indicator | partial | B,Δ,HC |
| 19 | Scalability (of method) | method-level tractability at scale | meta | Neither (concept); first-order method criterion | n/a | (meta) |
| 20 | Hierarchy / macro↔micro | inter-level map (coarse-graining+closure) | abstraction/structural | **Constitutive of deepest**; near-necessary (complex) | no (if commuting) | HC,CC |
| 21 | Grasp / intelligibility | internalized usable model + skills | competence/agentive | **Constitutive** (agent side) | yes (IOED illusion) | X |
| 22 | Novel-kind prediction / surprise reduction | theory entailing new *kinds* | competence | Strong indicator of depth | hard | P(novel),B,Δ |

## Cluster → epistemic-status summary

| Cluster | Notions | Recovers | Yields understanding alone? |
|---|---|---|---|
| **Predictive/descriptive** | 1,2,3(fit),10(fit),18(fit),19 | statistical/predictive structure | **No** ("knowledge about") |
| **Causal/interventionist** | 4,5,8,9,16 | difference-making structure | **Jointly near-necessary & core** |
| **Mechanistic/organizational** | 7,14,15,17,20 | organized productive structure | **Constitutive of mechanistic understanding** |
| **Abstraction/level** | 6,16,20 | right relevant variables / level | **Constitutive of understanding's form** |
| **Competence/agentive** | 3,8,11,12,13,21,22 | abilities that manifest/test understanding | **The manifestation/test, not the object** |

**The screening test (Part II §23):** *Can you correctly predict the effect of interventions you have
never observed, and explain why, in terms of organized parts?* — passed by the causal/mechanistic/
abstraction clusters, failed by the predictive/descriptive cluster. This single test sorts every
notion into "knowledge about" vs "understanding of."
