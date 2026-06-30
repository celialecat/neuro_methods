# Part I — Literature Review: Major Theories of Scientific Understanding

> **Reading note.** This Part is organized by discipline, but a single thread runs through it:
> each tradition supplies a different answer to *what an explanation must recover* before we
> grant that a system is understood. We flag, for each tradition, the **epistemic object** it
> treats as the currency of understanding (regularity, cause, mechanism, unifying pattern,
> invariant, hierarchy, generative principle) and whether that object is taken to be sufficient
> for understanding or merely necessary.

---

## 1. Philosophy of science: the theory of explanation

The philosophy of scientific explanation is the most direct ancestor of our question, because
"to understand X" has classically been analyzed as "to possess an explanation of X." The major
positions can be read as a sequence of answers to the question *what kind of object is an
explanation?*

### 1.1 Hempel: explanation as nomic expectability (the covering-law model)

Carl Hempel and Paul Oppenheim (1948) and Hempel (1965) proposed the **Deductive-Nomological
(D-N) model**: to explain an event is to exhibit it as the conclusion of a deductively valid
argument, at least one of whose premises is a law of nature. The companion
**Inductive-Statistical (I-S) model** extends this to probabilistic laws, where the explanandum
is conferred high probability rather than entailed. Explanation, on this view, is *nomic
expectability*: we understand E when we see that, given the laws and initial conditions, E was
to be expected.

- **Epistemic object recovered:** lawful regularity + logical subsumption.
- **Strengths:** precise, formal, captures the role of laws in physics; ties explanation to
  prediction (the "structural identity" of explanation and prediction).
- **Decisive limitations** (the classic counterexamples that drive the entire subsequent
  literature):
  - *The flagpole and the shadow* (Bromberger): from the length of a shadow and the laws of
    optics one can deductively derive the height of the flagpole, but the shadow does not
    *explain* the height. Explanation is **asymmetric**; deductive subsumption is symmetric.
  - *The barometer*: a falling barometer lets us predict a storm and is covered by a regularity,
    but does not explain it — both are effects of a common cause. **Correlation/derivability is
    not explanation.**
  - *The hexed salt* / irrelevance (Salmon): "this salt dissolved because it was hexed and all
    hexed salt dissolves" is a valid D-N argument but explanatorily empty. **Explanatory
    relevance** is not captured by subsumption.
  - The I-S model founders on low-probability events (we can explain a rare paresis from
    untreated syphilis even though most syphilitics never develop paresis).

The flagpole and barometer cases are, in miniature, exactly the Jonas–Kording/Lazebnik worry:
a method can deliver correct nomic expectations (prediction, derivability, correlation under a
regularity) while failing to deliver understanding, because it does not track the *asymmetric,
relevant, productive* structure of the world.

### 1.2 Salmon: explanation as causal/mechanical relevance

Wesley Salmon (1971, 1984, 1998) diagnosed the failures above as a failure to track **causation**.
His **Statistical-Relevance (S-R) model** replaced "high probability" with "statistical
relevance": a factor explains insofar as it makes a difference to the probability of the
explanandum (partitioning a reference class into cells with different probabilities). He then
moved to the **Causal-Mechanical (C-M) model**: to explain an event is to situate it in the
causal nexus — to trace the **causal processes** (which transmit conserved quantities / can
transmit a "mark") and **causal interactions** that produce it. Salmon distinguished *causal
processes* from *pseudo-processes* (a moving shadow is a pseudo-process: it cannot transmit a
mark).

- **Epistemic object:** causal processes and interactions; *ontic* conception of explanation
  (explanation is a feature of the world's causal structure, not of our arguments or expectations).
- **Strengths:** dissolves the asymmetry and irrelevance problems; grounds explanation in
  physical production.
- **Limitations:** the conserved-quantity account is hard to apply outside fundamental physics;
  it says little about *higher-level* explanation (why does the economy do X?); tracing every
  causal line is neither feasible nor obviously explanatory (the "too much detail" problem).

### 1.3 The ontic vs. epistemic divide

Salmon also crystallized a meta-distinction that recurs throughout this review:

- **Epistemic conception:** explanation is something we *do* — it changes our epistemic state
  (expectation, inference, cognitive grasp). Hempel, van Fraassen, and unificationists sit here.
- **Ontic conception:** explanation is something in the *world* — the objective causal/mechanical
  structure that produces phenomena, which we merely describe. Salmon and (in part) Craver sit here.
- **Modal conception** (later, Lange): explanation by appeal to what *must* be so (mathematical,
  constraint-based explanation).

This trichotomy matters for our project because "understanding" can be located on the epistemic
side (a cognitive achievement) while "the mechanism" lives on the ontic side; a complete theory
must connect the two.

### 1.4 van Fraassen: explanation as answers to contrastive why-questions (pragmatic/erotetic)

Bas van Fraassen (1980, *The Scientific Image*) advanced **constructive empiricism** and a
**pragmatic theory of explanation**. An explanation is an *answer to a why-question*, and a
why-question is individuated by (i) a **topic** (the fact P_k), (ii) a **contrast class**
({P_1, …, P_n}), and (iii) a **relevance relation** that determines what counts as an answer.
"Why P_k *rather than* P_j?" Explanation is therefore context- and interest-relative; there is
no context-free fact about *the* explanation of an event.

- **Epistemic object:** contextually relevant difference-makers relative to a contrast class.
- **Strengths:** captures the manifest context-sensitivity of explanatory requests ("why did
  *Adam* eat the apple?" vs. "why did Adam eat *the apple*?"); explains why "too much detail"
  fails to satisfy.
- **Limitations / for our purposes:** as an *anti-realist* (we need only empirical adequacy,
  not truth about unobservables), van Fraassen is skeptical that explanation tracks anything
  beyond prediction + pragmatics. This is precisely the position our thesis resists: if
  understanding reduces to empirically adequate answers to context-relative questions, the
  Jonas–Kording microprocessor would be "understood" by any predictively adequate model, which
  is the conclusion we wish to avoid.

### 1.5 Kitcher: explanation as unification

Philip Kitcher (1981, 1989, "Explanatory Unification and the Causal Structure of the World")
revived (with Friedman 1974) the idea that we understand the world by **unifying** it: by
deriving many phenomena from the smallest possible stock of repeatedly-used **argument patterns**.
The "explanatory store" E(K) over our beliefs K is the set of argument patterns that maximizes
the number of conclusions while minimizing the number and stringency of patterns. Understanding
increases as the ratio (phenomena explained)/(independent patterns used) increases.

- **Epistemic object:** a minimal generating set of argument schemata (a *compression* of our
  total knowledge into few reusable derivation templates).
- **Strengths:** captures the felt power of unifying theories (Newton, Maxwell, Darwin,
  thermodynamics); connects explanation to **compression and parsimony**, which links directly
  to MDL/Kolmogorov ideas (Section 4). Provides an account of why deep theories feel
  illuminating beyond local causal stories.
- **Limitations:** unification can conflict with causation — sometimes the most unifying
  derivation is the asymmetric-wrong one (deriving flagpole from shadow could be part of a
  unified optics); Kitcher must add asymmetry conditions, partly re-importing causal notions.
  Unification is also a *global* virtue, hard to assess locally.
- **Why it matters here:** the unification tradition is the philosophical home of the
  "**understanding = compression**" intuition. Part II and Part VI must confront whether
  compression is sufficient (we argue: necessary-ish, not sufficient — see the "lossy vs.
  mechanism-preserving compression" distinction).

### 1.6 Woodward: interventionism (the manipulationist theory)

James Woodward (2003, *Making Things Happen*; Woodward & Hitchcock 2003) gives what is now the
dominant account in philosophy of science and the lingua franca for causal ML. Its core:

- **Causal/explanatory relevance is defined via interventions.** X causes Y (relative to a
  background) iff there is a possible **intervention** on X that changes Y (or its distribution).
- An explanation is good to the extent that it answers a range of **what-if-things-had-been-
  different questions (w-questions)**: it tells us how the explanandum *would have changed* under
  interventions on the explanans. Explanatory relations are **invariant under intervention**
  within a domain.
- **Explanatory depth** is measured by the *range of invariance*: a relationship that holds
  across a wider range of interventions and background conditions is deeper (Hitchcock &
  Woodward 2003, "Explanatory Generalizations Part II: Plumbing Explanatory Depth").

- **Epistemic object:** invariant, intervention-supporting relationships (counterfactual
  dependence under manipulation).
- **Strengths:** operationalizable (interventions, do-operator); naturally graded (depth = range
  of invariance); applies at any level (no need to bottom out in physics); directly connects to
  Pearl's causal graphs and to **activation patching** in interpretability.
- **Limitations:** requires a notion of "possible intervention" that can be obscure for
  variables that cannot be wiggled independently (e.g., interventions on a network's
  superposed features); silent on *which* variables to use (the **variable-choice problem**),
  which is where the mechanistic and abstraction literatures re-enter.
- **Centrality to this project:** counterfactual/interventional competence is one of our core
  measurable dimensions (Part VI), and interventionism gives the cleanest formal scaffold for it.

### 1.7 Bogen & Woodward: data vs. phenomena

Bogen & Woodward (1988, "Saving the Phenomena") drew a distinction that is essential for
evaluating empirical methods: **data** are the idiosyncratic, error-laden records of particular
measurements; **phenomena** are the stable, repeatable features of the world that data are
evidence *for*. Theories explain *phenomena*, not data. A method can model data superbly
(high predictive fit) without isolating any phenomenon, let alone explaining it.

- **For our taxonomy:** this gives a principled way to separate *description/curve-fitting of
  data* from *explanation of phenomena*, and warns that high in-sample fit (a regression to fMRI
  voxels, a transformer's loss) is evidence about data, not yet about phenomena or mechanism.

### 1.8 Cartwright: capacities, nomological machines, and the disunity of science

Nancy Cartwright (1983, *How the Laws of Physics Lie*; 1989, *Nature's Capacities and Their
Measurement*; 1999, *The Dappled World*) argues that fundamental laws are literally false as
descriptions (they hold only *ceteris paribus*); what is real are **capacities/powers** and the
**nomological machines** — stable arrangements of components with stable capacities — that
generate regularities. Laws are local, not universal; the world is "dappled."

- **Epistemic object:** stable capacities and the (often engineered) arrangements that harness
  them.
- **Strengths:** explains why regularities are *parochial* and why understanding often means
  understanding a *machine/arrangement* — strikingly congruent with Lazebnik's radio and with
  mechanistic neuroscience. Warns that exporting a fitted regularity outside its nomological
  machine fails (a direct critique of "prediction = understanding").
- **Limitations:** "capacity" is a primitive that critics find obscure; offers less in the way
  of formal machinery than interventionism.

### 1.9 The mechanists: Machamer, Darden, Craver; Bechtel & Richardson; Glennan

The **New Mechanist** program is the single most important philosophical input to this project,
because it is explicitly about *understanding complex, multi-level biological and engineered
systems* — exactly our target.

- **Machamer, Darden & Craver (2000), "Thinking About Mechanisms" (MDC):** a mechanism is
  *entities and activities organized such that they are productive of regular changes from
  start/setup to finish/termination conditions.* Crucially, mechanisms include both *entities*
  (things) and *activities* (the doings) — not just static parts. To explain a phenomenon is to
  describe the mechanism that produces it.
- **Bechtel & Richardson (1993), *Discovering Complexity*:** scientific discovery proceeds by
  **decomposition** (breaking a system into component operations) and **localization** (assigning
  operations to component parts). They analyze when these heuristics *succeed* and when they
  *mislead* (e.g., when the system is *integrated/non-decomposable*, localization fails) — a
  direct, constructive treatment of Lazebnik's worry.
- **Craver (2007), *Explaining the Brain*:** develops **constitutive mechanistic explanation**
  and the criterion of **mutual manipulability** for *constitutive relevance*: a component's
  activity φ is constitutively relevant to a phenomenon ψ iff (i) intervening on φ changes ψ
  (bottom-up) and (ii) intervening on ψ changes φ (top-down). Craver also distinguishes
  **how-possibly**, **how-plausibly**, and **how-actually** models, and **mechanism sketches**
  (with black boxes/filler terms) from **complete mechanistic descriptions**. He defends a
  **3M (model-mechanism-mapping)** norm: a good explanatory model's variables and dependencies
  must map onto the entities, activities, and organizational features of the actual mechanism.
- **Glennan (1996, 2017, *The New Mechanical Philosophy*):** causation between events is grounded
  in underlying mechanisms; "minimal mechanism."
- **Levels of mechanism:** mechanistic levels are *part–whole* (constitutive) levels, not the
  global "levels of nature" of the reductionist picture; this is important for Part V.

- **Epistemic object:** entities + activities + organization producing a phenomenon; with
  explicit *relevance* (mutual manipulability) and *completeness* (sketch → schema → how-actually)
  gradients.
- **Strengths:** purpose-built for biology/neuroscience/engineered systems; provides
  *gradable* notions (sketch vs. complete; how-possibly vs. how-actually) that we operationalize
  as **mechanistic faithfulness** in Part VI; integrates interventionism (mutual manipulability
  is an interventionist criterion) with decomposition/hierarchy (Simon).
- **Limitations:** "mechanism" can be too permissive (almost anything is a mechanism); the
  completeness gradient is informal; says less about *dynamical/field* systems where part
  decomposition is unnatural.

### 1.10 Strevens: the kairetic account (explanation as difference-making detail)

Michael Strevens (2008, *Depth*) offers the **kairetic account**: a causal explanation is built
from a *causal model* of the production of the event, from which one then **abstracts away**
every detail that does not make a difference to the outcome (an "optimizing" procedure that
removes non-difference-makers while preserving entailment of the explanandum). What remains —
the **difference-makers** — is the explanation. Depth and generality come from finding the
*most abstract* difference-making description that still entails the target.

- **Epistemic object:** the minimal set of difference-making causal factors (causal structure
  *plus* an explicit abstraction/idealization step).
- **Strengths:** unifies causation with abstraction; explains why *idealized* models (frictionless
  planes, ideal gases) can explain better than fully detailed ones — they isolate
  difference-makers. This is the cleanest philosophical bridge to **the "right level of
  description" problem** and to information-theoretic compression of mechanism (Part VI's
  *mechanistic faithfulness at minimal description length*).
- **Limitations:** the optimizing procedure is hard to make precise; the role of idealizations
  that are *not* mere abstractions (distortions) is contested.

### 1.11 Lipton: inference to the best explanation; understanding as a cognitive good

Peter Lipton (1991/2004, *Inference to the Best Explanation*) defends **IBE**: we infer the
hypothesis that, if true, would best explain the evidence, where "best" tracks **explanatory
loveliness** (the degree of understanding it would provide) as a guide to **likeliness** (truth).
Lipton also wrote influentially on **understanding without explanation** and the contrastive
structure of explanation (why P rather than Q is answered by a *difference* in the causal
histories of P and Q).

- **For our project:** Lipton foregrounds *understanding* itself as the cognitive good that
  explanation delivers, and links it to contrastive, difference-making structure — converging
  with Woodward and Strevens.

### 1.12 De Regt: understanding as an aim in its own right (intelligibility)

Henk de Regt (2017, *Understanding Scientific Understanding*; de Regt & Dieks 2005) argues that
**understanding** is a legitimate, irreducible aim of science, not a mere by-product of
explanation. His **Criterion for Understanding Phenomena (CUP):** a phenomenon is understood iff
there is an *intelligible* theory of it that meets empirical standards; and **Criterion for the
Intelligibility of Theories (CIT):** a theory is intelligible (to scientists in a context) iff
they can recognize *qualitative consequences* of it without exact calculation. Intelligibility
is partly *pragmatic and skill-relative* (it depends on scientists' abilities and tools), but
not merely subjective.

- **Epistemic object:** an intelligible theory + the *skills* to draw consequences from it.
- **Strengths:** captures the *agent-relative, ability-based* face of understanding (you
  understand if you can *do* things with the theory — predict qualitatively, see what would
  happen if…). This anticipates our emphasis on **competences** (Part IV/VI) and links to
  cognitive science (Section 6).
- **Limitations:** risks subjectivity; needs supplementing with objective constraints (which the
  mechanistic and interventionist accounts supply).

### 1.13 Explanatory depth, scientific realism vs. instrumentalism

- **Explanatory depth** (Hitchcock & Woodward 2003; Strevens 2008): depth = *range of invariance*
  / *abstraction over difference-makers* / *resilience under intervention*. Depth is the
  philosophical seed of our quantitative "depth" and "breadth" dimensions (Part VI).
- **Realism vs. instrumentalism:** *Scientific realism* (Boyd, Psillos; the "no-miracles"
  argument; explanationist defenses) holds that mature theories are approximately true and their
  unobservable posits real — so understanding requires getting the *hidden structure* right.
  *Instrumentalism / constructive empiricism* (van Fraassen) holds theories are tools for
  prediction; "understanding" beyond empirical adequacy is optional or pragmatic. The **pessimistic
  meta-induction** (Laudan) and **underdetermination** are the standard anti-realist levers.
  *Structural realism* (Worrall 1989; Ladyman & Ross 2007, *Every Thing Must Go*) is the
  intermediate view that what is preserved across theory change is *structure* (relations,
  equations), not the intrinsic nature of entities — directly relevant to whether interpretability
  recovers "real features" or only useful structure.
- **For our thesis:** the prediction-vs-understanding distinction *is* a realism-vs-instrumentalism
  distinction in operational clothing. A purely instrumentalist stance collapses the distinction
  (and would declare the predictive microprocessor model "as good as understood"); a realist
  stance demands recovery of hidden structure. Our framework takes a *modest realist* line:
  understanding requires recovering structure that is **invariant, manipulable, and
  hierarchically composable**, which is testable without metaphysical commitment to the ultimate
  furniture of the world.

---

## 2. Complex systems and systems science

If philosophy of science tells us *what an explanation must recover*, complexity/systems science
tells us *what about complex systems makes recovery hard or easy* — and supplies the central
structural concept of this project: **near-decomposability / hierarchy**.

### 2.1 Herbert Simon: The Architecture of Complexity; near-decomposability

Simon (1962, "The Architecture of Complexity"; 1969/1996, *The Sciences of the Artificial*) is
the keystone reference for Part V. Core claims:

- **Hierarchy is ubiquitous:** complex systems that survive/evolve tend to be **hierarchic** —
  composed of subsystems, which are composed of sub-subsystems. (Parable of the watchmakers
  Hora and Tempus: the one who builds via stable sub-assemblies finishes; modular construction is
  vastly more robust to interruption — an evolutionary argument for hierarchy.)
- **Near-decomposability (ND):** in many hierarchic systems, *intra*-subsystem interactions are
  much stronger/faster than *inter*-subsystem interactions. Consequences:
  1. **Short-run** behavior of each subsystem is approximately independent of the others.
  2. **Long-run** behavior depends on the others only in an aggregate way.
  This yields **scale/time separation**: fast within-module equilibration, slow between-module
  dynamics.
- **Empty world / sparsity:** interactions are sparse; most pairs of components barely interact.
- **Description and the observer:** Simon stresses that the *redundancy* exploited by hierarchy
  is what makes complex systems *describable* at all — a hierarchic system has a **short
  description** relative to its size (linking hierarchy to compression / MDL, Section 4).

- **Epistemic object / payoff:** ND licenses *aggregation* and *modular* explanation — you can
  understand the system level-by-level, treating each module's internal detail as a black box
  characterized by a few aggregate variables. This is the structural precondition that makes
  decomposition-and-localization (Bechtel & Richardson) *work*, and its *absence* is precisely
  Lazebnik's nightmare (a non-decomposable radio/cell where localization misleads).

### 2.2 Simon–Ando–Fisher: aggregation and the dynamics of near-decomposable systems

Simon & Ando (1961, "Aggregation of Variables in Dynamic Systems") and Ando & Fisher made ND
*mathematically precise* for linear dynamical systems: if the state-transition (or interaction)
matrix is **block-diagonal-dominant** (strong within-block, weak between-block coupling), then
the dynamics exhibit two phases — (i) **fast** within-block equilibration during which blocks
behave nearly independently, then (ii) **slow** between-block dynamics during which the
*aggregate* variables (one per block) evolve while within-block ratios stay nearly fixed. The
spectral picture: a *gap* in the eigenvalue spectrum separates fast and slow modes; the system is
ND to the degree this **spectral gap** is large.

- **For our framework:** this gives an *operational, measurable* signature of decomposability
  (spectral gaps, block structure in interaction/coupling matrices) that Parts V–VII use to
  define **hierarchical consistency** and to design benchmarks where the ground-truth modularity
  is known.

### 2.3 Ashby and cybernetics: requisite variety, regulation, the law of every good regulator

W. Ross Ashby (1956, *An Introduction to Cybernetics*; 1958) supplies the control-theoretic lens.

- **Variety** = the number of distinguishable states. **The Law of Requisite Variety:** "only
  variety can absorb variety" — a regulator can hold an essential variable within bounds only if
  it has at least as much variety as the disturbances it must counter. Control/understanding of a
  system requires *matching its variety*.
- **The Good Regulator Theorem** (Conant & Ashby 1970, "Every Good Regulator of a System Must Be
  a Model of That System"): any regulator that is *optimal and simple* must be (isomorphic to) a
  **model** of the system it regulates. This is a striking formal bridge: *successful control
  entails an internal model* — i.e., a particular link from the "control" goal to the "modeling"
  goal in our taxonomy (Part III), and a partial argument that intervention competence presupposes
  representational/mechanistic structure.
- **Homeostasis, feedback, the ultrastable system** (Ashby's homeostat): understanding regulation
  requires understanding feedback loops, not just feedforward chains — a caution for any method
  (e.g., linear encoding models) that ignores closed-loop structure.

### 2.4 Wiener, von Foerster, Pask: first- and second-order cybernetics

- **Wiener (1948, *Cybernetics*):** control and communication in the animal and the machine;
  feedback, information, and purpose as unifying concepts across engineered and living systems.
- **Second-order cybernetics** (von Foerster, Pask, Maturana & Varela): the observer is part of
  the system observed; *autopoiesis* (self-production) as the mark of the living. Relevant as a
  caution: the **modeling relation always includes a modeler**, foreshadowing Rosen.

### 2.5 Rosen: the modeling relation; (M,R)-systems; complexity as non-computability

Robert Rosen (1985, *Anticipatory Systems*; 1991, *Life Itself*) provides the deepest
formalization of *what it is to model* a system, and a provocative claim about the limits of
mechanistic understanding.

- **The modeling relation:** a *commuting diagram* between a **natural system** (with its causal
  entailment structure) and a **formal system** (with its inferential entailment structure),
  linked by **encoding** and **decoding** maps. We "understand" a natural system to the extent
  that inference in the formal system *commutes* with causality in the natural system: decode(infer(encode(x))) = observe(cause(x)). This is, in our terms, **the requirement that a
  model be mechanistically faithful — that its internal transitions mirror the system's causal
  transitions**, not merely match input–output behavior.
- **(M,R)-systems and closure to efficient causation:** Rosen argues organisms are **complex** in
  a strong sense — they are *closed to efficient causation* (every function's "maker" is itself
  made within the system), which (he argues) makes them **non-simulable by any single syntactic/
  Turing model** ("largest model" arguments). Whether or not one accepts the strong
  non-computability claim (it is contested), the modeling relation itself is a clean,
  discipline-neutral statement of the faithfulness condition we adopt.
- **Anticipatory systems:** systems containing a *predictive model of themselves/environment* and
  acting on its predictions — connecting to Conant–Ashby and to "world models" in ML.

- **Epistemic object:** a *commuting* encode/infer/decode relation (structure-preserving model),
  not mere predictive fit. Rosen is the strongest statement of "**simulation/prediction ≠
  understanding unless the model's entailment mirrors the system's causation**."

### 2.6 Mesarović, Pattee, Klir: general systems and hierarchy theory

- **Mesarović, Macko & Takahara (1970), *Theory of Hierarchical, Multi-Level Systems*:** formal
  taxonomy of hierarchies — **strata** (levels of description/abstraction), **layers** (levels of
  decision complexity), **echelons** (organizational levels) — useful for disentangling the many
  senses of "level" that confuse cross-disciplinary debate (Part V).
- **Pattee:** the **epistemic cut** between dynamics (laws) and controls (symbols/constraints);
  hierarchies arise where symbolic constraints harness rate-dependent dynamics — relevant to
  genotype/phenotype and to memory in neural systems.
- **Klir (1991, *Facets of Systems Science*):** systematic catalog of systems concepts and the
  **epistemological hierarchy of systems** (source → data → generative → structure → metasystems),
  a useful scaffold for "what kind of model does a method deliver."

### 2.7 Emergence, levels of organization, downward causation

- **Anderson (1972), "More is Different":** *more is different* — at each level of complexity new
  properties and laws appear that are not (practically) derivable from the level below; **broken
  symmetry** and scale generate genuinely new science at each level. A foundational argument that
  understanding is **level-relative** and that micro-reduction is neither necessary nor sufficient
  for macro-understanding.
- **Kinds of emergence:** *epistemological/weak emergence* (Bedau: macro-states reachable only by
  simulation, derivable in principle but not in practice — e.g., Game of Life patterns) vs.
  *strong/ontological emergence* (irreducible new causal powers, downward causation — contested).
- **Downward causation** (Campbell; critiqued by Kim's *causal exclusion* argument): whether
  higher levels can be causally efficacious over lower ones; bears on whether macro-variables are
  *real difference-makers* (interventionist takes — e.g., causal emergence below — try to
  vindicate this).
- **For our framework:** emergence is the reason "derive macro from micro" and "infer micro from
  macro" are *separate* criteria (Part IV), and why **multi-scale faithfulness** is a distinct
  dimension.

### 2.8 Network science

- **Structure:** small-world (Watts & Strogatz 1998), scale-free/preferential attachment
  (Barabási & Albert 1999), community/modularity detection (Newman & Girvan 2004; modularity Q),
  motifs (Milo et al. 2002), **rich clubs**, core–periphery. Networks give a *measurable* handle
  on **modularity** and **hierarchy** (hierarchical modularity: Ravasz & Barabási 2003).
- **Function:** controllability of complex networks (Liu, Slotine & Barabási 2011), spreading
  dynamics, robustness/percolation.
- **For our taxonomy:** network analysis typically recovers **structural/topological description
  and correlation** (who connects to whom, which nodes are central). This is *knowledge about*
  the system; it becomes *understanding* only when topology is tied to **mechanism and
  intervention** (does removing this hub change function as predicted?). A key Part VIII caution
  for "network neuroscience."

### 2.9 Dynamical systems, attractors, bifurcations

Strogatz (1994), Guckenheimer & Holmes: phase space, **attractors** (fixed points, limit cycles,
strange attractors), **bifurcations**, **normal forms**, center-manifold reduction, separation of
**fast/slow** variables (singular perturbation), and **universality** of bifurcation types.
Dynamical-systems understanding is often *geometric and topological* (the shape of the flow), a
distinct epistemic object from both "mechanism" (parts) and "law" (equations). Highly relevant to
**neural manifolds/dynamics** (Part VIII) and to whether recovering an *attractor geometry*
counts as understanding (we argue: it is understanding *at the dynamical level* — a legitimate
level — but may leave the *implementing mechanism* unexplained).

### 2.10 Renormalization, coarse-graining, and the renormalization group (RG)

The RG (Kadanoff; Wilson 1975, Nobel 1982) is arguably the deepest scientific account of
**why and how higher-level descriptions are possible and autonomous**:

- **Coarse-graining + rescaling** defines a flow on the space of theories (Hamiltonians/couplings).
- **Fixed points** of this flow correspond to scale-invariant (critical) behavior; the flow
  sorts couplings into **relevant**, **irrelevant**, and **marginal**.
- **Universality:** systems with utterly different microphysics flow to the same fixed point and
  share macroscopic critical exponents — *most microscopic detail is irrelevant to macroscopic
  behavior.* This is the rigorous vindication of the intuition that **understanding lives at the
  level of the relevant variables**, and a template for **principled, mechanism-respecting
  coarse-graining** (vs. arbitrary aggregation).
- **For our framework:** RG is the gold standard for "deriving macro from micro" *with* an account
  of *which* micro-details survive — the inspiration for defining **hierarchical consistency** as
  the existence of a coarse-graining map under which the coarse dynamics close (commute), and for
  treating "relevant variables" as the targets of explanation.

### 2.11 Multiscale modeling and effective theories

The **effective field theory** stance (each scale has its own autonomous description with a finite
number of parameters; integrate out short-distance modes): generalized in physics, materials, and
increasingly in biology (multiscale models). The methodological upshot, central to Part V: a
*good* level of description is one that is **closed/autonomous** (its variables suffice to predict
their own future) and **low-dimensional** (few effective parameters). This is the criterion we
generalize as **closure under coarse-graining**.

---

## 3. (Reserved — cybernetics merged into §2.3–2.5.)

---

## 4. Information theory: compression, complexity, and information-theoretic notions of structure

This tradition supplies the *quantitative* vocabulary for "compression," "structure," and the
sharpest version of the question *is compression understanding?*

### 4.1 Shannon: information, entropy, channel capacity

Shannon (1948). **Entropy** H(X) quantifies uncertainty/description length; **mutual information**
I(X;Y) quantifies statistical dependence; **channel capacity** bounds reliable transmission.
Crucial caveats for our project:
- Shannon information is **purely statistical/correlational and semantics-free**; I(X;Y) > 0 is
  *correlation*, not causation and not mechanism. (Recovering high mutual information between a
  neural population and a stimulus is *knowledge about* coding, not yet *understanding* of the
  mechanism — a recurring Part VIII point.)
- The source-coding theorem ties *probabilistic* structure to *compressibility*, the bridge to MDL.

### 4.2 Kolmogorov complexity and Algorithmic Information Theory (AIT)

Solomonoff (1964), Kolmogorov (1965), Chaitin (1969). **K(x)** = length of the shortest program
that outputs x on a universal machine. **Algorithmic probability** and **Solomonoff induction**
formalize "the simplest explanation that fits the data is most probable," a rigorous Occam's razor.

- **Key conceptual link:** the shortest program *is* a candidate "mechanism" — it is a generative
  recipe, not a mere summary. But two warnings: (i) K(x) is **uncomputable**; (ii) a *shortest
  program* need not be **decomposable, modular, or human-intelligible**, and need not align with
  the system's *actual* causal parts. Thus "maximally compressed" ≠ "mechanistically faithful" ≠
  "understood." This gap is one of the load-bearing distinctions in Part VI.
- **Sophistication / logical depth (Bennett 1988):** *logical depth* = the computation time the
  shortest program needs — distinguishes *trivially* simple (a constant string) and *random*
  (incompressible) objects, both shallow, from *deep* objects whose structure took long
  computation to produce. **Effective/structural complexity** (Gell-Mann & Lloyd's "effective
  complexity"; Koppel's sophistication) tries to separate the *regular* part of an object (its
  structure/model) from the *random* part (noise) — formalizing "the part worth understanding."

### 4.3 Minimum Description Length (MDL) and the two-part code

Rissanen (1978, 1989); Grünwald (2007). MDL operationalizes Occam: choose the model that
minimizes **L(model) + L(data | model)** — the description length of the hypothesis plus the data
encoded with it. The "two-part code" makes explicit the trade-off between model complexity and
fit; it is a computable, statistical surrogate for Kolmogorov-style "best explanation," and the
formal core of the **unification = compression** idea (Kitcher) and of **structural complexity**
(the model part L(model) is the "structure"; the residual L(data|model) is the "noise").

- **For our framework:** MDL gives a principled way to define **mechanistic compression** — but
  we must add the constraint that L(model) be expressed in a vocabulary of *interventionally
  meaningful, composable* parts, otherwise MDL rewards opaque compressions (lookup tables, giant
  polynomials) that predict without explaining.

### 4.4 The Information Bottleneck (IB)

Tishby, Pereira & Bialek (1999). Given input X and target Y, seek a representation T that
**minimizes I(X;T)** (compression) while **maximizing I(T;Y)** (relevance/prediction): the
optimal trade-off curve. IB is the cleanest formal statement of *task-relevant lossy
compression*. It (and its "deep learning" interpretation, Shwartz-Ziv & Tishby 2017, contested)
captures *prediction-oriented* representation.

- **Crucial for our thesis:** IB optimizes for **predictive sufficiency**, not **mechanistic
  faithfulness** or **causal/counterfactual competence**. An IB-optimal code can throw away
  exactly the variables a *mechanism* needs (e.g., it discards a variable that is causally
  upstream but redundant for the specific Y), so IB representations exemplify "**knowledge about**
  (optimal predictive coding) **without understanding** (no guarantee of recovering generative/
  causal structure)." This is a canonical example for Part III.

### 4.5 Predictive information, excess entropy, statistical complexity, ε-machines

- **Predictive information / excess entropy** (Bialek, Nemenman & Tishby 2001; Crutchfield &
  Feldman): the mutual information between past and future, I(past; future) — the amount of the
  past that is *relevant to predicting* the future; sub-extensive growth signals learnable
  structure.
- **Computational mechanics: ε-machines and statistical complexity** (Crutchfield & Young 1989;
  Shalizi & Crutchfield 2001). The **causal states** are equivalence classes of pasts that yield
  identical conditional futures (the coarsest sufficient statistic for prediction); the **ε-machine**
  is the minimal, unifilar hidden-Markov machine over causal states; **C_μ (statistical
  complexity)** = entropy of the causal-state distribution = the amount of *historical
  information the process must store to predict its future optimally.* This is one of the very
  best formalizations available of "**the intrinsic structure that must be represented to
  understand a process**," and it explicitly *separates* structure (C_μ) from intrinsic randomness
  (entropy rate h_μ). We lean on ε-machines heavily in Part VI/VII as a principled target: a
  process is "understood at the predictive level" when one has recovered its ε-machine.
  *Caveat:* causal states are defined by *predictive* equivalence, so the ε-machine is the
  minimal *predictively* sufficient model — still potentially distinct from the *physically
  implementing* mechanism (two systems can share an ε-machine), which is exactly why we keep
  "predictive structure" and "mechanistic structure" as separate dimensions.

### 4.6 Integrated Information Theory (IIT) and Φ

Tononi (2004, 2016) et al. **Φ (integrated information)** quantifies how much a system's
**cause–effect structure is irreducible** to the sum of its parts (information generated by the
whole above its minimum-information partition). Whatever one thinks of IIT's consciousness claims,
Φ is notable here as an attempt to formalize **non-decomposability / irreducible integration** —
the *anti*-modularity that defeats Simon-style hierarchy and Lazebnik-style localization. High Φ
≈ "this system resists decomposition," which is directly relevant to *when* mechanistic
decomposition will fail. (Caveats: Φ is computationally intractable at scale, definition-sensitive,
and its interpretation is contested.)

### 4.7 Partial Information Decomposition (PID)

Williams & Beer (2010); Bertschinger et al.; Griffith & Koch. Decomposes the information that
multiple sources {X1,X2} carry about a target Y into **unique**, **redundant**, and **synergistic**
components. This is the precise tool for asking *how information is distributed across parts* — and
for detecting **synergy** (information present only in the joint, not in any part), the
information-theoretic face of *holism/non-decomposability*. Highly relevant to interpretability
(is a feature represented redundantly across neurons? is a computation synergistic across heads?)
and to whether a "localization" is legitimate.

### 4.8 Effective information and causal emergence

Hoel, Albantakis & Tononi (2013); Hoel (2017), "When the map is better than the territory."
**Effective Information (EI)** measures the causal influence of a system on itself under a maximum-
entropy intervention on inputs (an *interventionist* information measure, related to Pearl's
do-operator). Striking result: **coarse-grained (macro) descriptions can have higher EI than the
micro description** ("causal emergence") — i.e., the macro variables can be *better causal
variables* (less noisy, more deterministic/less degenerate) than the micro ones. This gives a
*quantitative, interventionist* vindication of Anderson's "more is different" and a criterion for
**choosing the explanatory level**: pick the scale that maximizes effective/causal information.
We use this in Parts V–VI as one formalization of "the right level of description."

### 4.9 Compression versus understanding — the crux

Synthesizing §4: the information-theoretic tradition makes vivid that **compression is necessary
but not sufficient** for understanding.
- *Necessary-ish:* a model that does not compress (a lookup table the size of the data) has
  captured no regularity; genuine structure shows up as compressibility (Simon's redundancy,
  Kitcher's unification, MDL).
- *Not sufficient:* (i) the shortest code can be **opaque/non-modular** (no recoverable parts);
  (ii) it can be **predictively** rather than **causally/mechanistically** sufficient (IB, ε-machine
  caveats); (iii) two systems with the same compressed description can have **different
  mechanisms** (multiple realizability). Hence our framework demands *mechanism-structured*
  compression: a short description **in a vocabulary of interventionally meaningful, composable,
  hierarchically organized parts** whose transitions *commute* with the system's (Rosen). This is
  the precise sense in which "understanding ⊋ compression."

---

## 5. Machine learning and mechanistic interpretability

ML is both an *object* of the understanding question (we want to understand trained networks) and
a *source* of methods that other sciences now borrow. We tag each method with its epistemic object.

### 5.1 Representation learning, disentanglement, world models

- **Representation learning** (Bengio, Courville & Vincent 2013): learn features that make
  downstream tasks easy. Epistemic object: *predictively useful representations* — knowledge
  about, not yet understanding (the features need not be causal or interpretable).
- **Disentanglement** (Higgins et al. β-VAE 2017; *definition* Higgins et al. 2018 via group
  theory): seek latent factors that vary independently and align with *generative factors of
  variation*. Aspires to recover **generative structure** — closer to understanding — but
  **Locatello et al. (2019)** proved disentanglement is **unidentifiable without inductive
  biases/supervision** (a purely unsupervised guarantee is impossible), a deep limitation that
  re-appears as the identifiability problem in causal representation learning.
- **World models** (Ha & Schmidhuber 2018; model-based RL; JEPA): learn a *predictive simulator*
  of an environment. Epistemic object: a **generative/predictive model** that supports rollout and
  planning. Whether a world model *understands* its environment depends on whether its latent
  transitions are **causally/mechanistically faithful** (do they support correct counterfactuals
  and transfer?) or merely good at next-state prediction on-distribution.

### 5.2 Mechanistic interpretability: the program

Mechanistic interpretability (MI) aims to *reverse-engineer* trained neural networks into
human-understandable algorithms — explicitly the ML analogue of Jonas–Kording. Foundational
strands:

- **Circuits / features** (Olah et al. 2020, "Zoom In: An Introduction to Circuits"; the
  Distill *Circuits* thread): the claims that (i) **features** are the fundamental units (directions
  in activation space corresponding to meaningful properties), (ii) features are connected by
  **weights into circuits** that implement algorithms, and (iii) features/circuits are partly
  **universal** across models. Epistemic object: *entities (features) + activities (weighted
  connections) + organization* — strikingly the **MDC mechanism** ontology applied to networks.
- **Induction heads and in-context learning** (Elhage et al. 2021 "A Mathematical Framework for
  Transformer Circuits"; Olsson et al. 2022): identification of specific attention-head circuits
  ("previous-token" + "induction" heads) that implement copying/pattern-completion and drive
  in-context learning — a worked *how-actually* mechanism with causal evidence.
- **Indirect Object Identification (IOI)** (Wang et al. 2022): a full circuit in GPT-2 small,
  localized via path patching — a benchmark of "mechanism recovered."
- **Grokking / modular arithmetic** (Nanda et al. 2023, "Progress Measures…"): a network found to
  implement a *Fourier/trig algorithm* for modular addition — a case where the recovered mechanism
  is **provably faithful** (you can read off the algorithm and verify it), the cleanest existing
  example of genuine mechanistic understanding of a network.

### 5.3 Superposition and the feature-identification problem

- **Toy Models of Superposition** (Elhage et al. 2022): networks represent **more features than
  neurons** by encoding features as *non-orthogonal directions* (superposition), so individual
  neurons are **polysemantic**. This is the network analogue of *non-localizability* — features
  are not cleanly mapped to parts, exactly the situation that defeats naïve localization (Bechtel
  & Richardson's warning, in silico).
- **Implication:** the *unit of mechanism* in a network is generally **not the neuron** but a
  **direction/feature**; recovering mechanism requires first solving a *representation* problem
  (find the right basis), echoing the **variable-choice problem** in causal inference.

### 5.4 Sparse autoencoders (SAEs) and dictionary learning

Bricken et al. 2023 ("Towards Monosemanticity"); Cunningham et al. 2023; Templeton et al. 2024
("Scaling Monosemanticity," Claude 3 Sonnet); Gao et al. 2024 (scaling SAEs). SAEs learn an
**overcomplete, sparse dictionary** of features from activations, aiming to *un-mix superposition*
into **monosemantic** features. Epistemic object: a candidate **feature inventory** (the
"entities" of the mechanism).
- *Strengths:* recovers human-interpretable features at scale; supports steering (intervention).
- *Limitations / open:* features are found by an **unsupervised reconstruction objective**, so
  identifiability is not guaranteed (cf. disentanglement); recent work questions **faithfulness**
  (do SAE features correspond to the features the model *actually uses* causally, or are they
  reconstruction artifacts?), **feature splitting/absorption**, and whether SAEs improve
  **downstream task understanding**. In our terms: SAEs deliver a *representation* (knowledge
  about the activation geometry); whether they deliver *mechanism* requires separate causal
  validation (patching the SAE features and confirming the predicted behavioral change).

### 5.5 Causal/interventionist interpretability methods

- **Activation patching / causal tracing** (Vig et al. 2020; Meng et al. ROME 2022; Geiger et al.):
  intervene on internal activations (replace with those from a counterfactual input) and measure
  the effect on output — a **do-operation on internal variables**, i.e., Woodward/Pearl applied
  inside the network. This is the method that most directly targets **mechanistic/causal**
  epistemic objects rather than correlational ones.
- **Causal abstraction / interchange interventions / DAS** (Geiger et al. 2021, 2023, "Causal
  Abstraction": Distributed Alignment Search): test whether a network *implements* a hypothesized
  high-level causal algorithm by checking that **interchange interventions** on the network align
  with interventions on the abstract model — a direct operationalization of **mechanistic
  faithfulness as causal-model isomorphism** (our central technical proposal in Part VI, and
  essentially Rosen's commuting diagram, instantiated).
- **Model editing** (ROME, MEMIT): locate-and-edit factual associations; *editing success +
  specificity + generalization* is itself a **repair/redesign** test of understanding (Part IV).

### 5.6 Correlational / attributional interpretability methods (and their epistemic ceiling)

- **Feature attribution / saliency** (Saliency maps, Integrated Gradients [Sundararajan et al.
  2017], LIME [Ribeiro et al. 2016], SHAP [Lundberg & Lee 2017], DeepLIFT, Grad-CAM): attribute a
  prediction to input features. Epistemic object: *local input–output sensitivity / correlation*.
  *Known failures:* many saliency methods fail **sanity checks** (Adebayo et al. 2018 — outputs
  barely change under randomization of weights/labels), are not **faithful** to the model's
  computation, and explain *the output* not *the mechanism*. Strong example of "**knowledge about
  (which inputs matter locally) ≠ understanding (how the computation works).**"
- **Linear probes** (Alain & Bengio 2016): train a linear classifier on activations to decode a
  property. Epistemic object: *decodability / linear availability of information.* Decodability is
  **correlational** — a probe can read out information the model **does not use** (Hewitt &
  Liang 2019 on probe selectivity/control tasks; Belinkov 2022). Decoding ≠ the model *using* that
  information; only **intervention** (does ablating the probed direction change behavior?)
  upgrades a probe from knowledge-about to evidence-of-mechanism.
- **Concept Activation Vectors (TCAV)** (Kim et al. 2018): directional derivatives along
  human-concept directions; sensitivity of predictions to a concept. Between probing and
  attribution; correlational unless causally validated.
- **Feature visualization** (activation maximization; Olah et al. 2017): synthesize inputs that
  maximally activate a unit/feature. Epistemic object: *a characterization of a unit's tuning* —
  descriptive; informative about *what* a feature responds to, silent about its *causal role* in
  the circuit.

### 5.7 The interpretability-evaluation literature (faithfulness vs. plausibility)

A growing methodological literature warns that interpretability "explanations" are often evaluated
by **plausibility** (do humans find them convincing?) rather than **faithfulness** (do they
correctly describe the model's actual computation?) — Jacovi & Goldberg (2020); Rudin (2019,
"Stop Explaining Black Box Models…", arguing for *inherently interpretable* models over post-hoc
explanation); critiques of saliency (Adebayo); the rise of **causal**, **ablation-validated**, and
**necessity/sufficiency**-based metrics. This literature is, in effect, the ML community
*independently rediscovering the prediction-vs-understanding distinction* — and it directly
motivates our insistence on causal/interventional and faithfulness criteria in Parts IV–VI.

### 5.8 Causal representation learning (CRL)

Schölkopf et al. (2021, "Toward Causal Representation Learning"); identifiability results (e.g.,
ICA/nonlinear ICA, Hyvärinen et al.; Khemakhem et al. iVAE 2020; CRL identifiability under
interventions, Brehmer et al. 2022, Ahuja et al.). CRL aims to learn **latent causal variables and
their causal graph** from high-dimensional observations — explicitly targeting the **causal/
mechanistic** epistemic object that representation learning alone misses. Central message and
caution: causal variables are **not identifiable from observational data alone**; identifiability
requires **interventions, temporal structure, multiple environments, or strong inductive biases**.
This is the ML re-statement of the philosophical point that *passive prediction underdetermines
mechanism* — the formal heart of our thesis.

---

## 6. Cognitive science: understanding as a psychological/agentive achievement

The philosophy and formal sciences tell us what *objects* understanding tracks; cognitive science
tells us what understanding *is for an agent* — which grounds our **competence-based** criteria.

- **Marr's three levels** (Marr 1982; see also §7.1): computational / algorithmic / implementational.
  A foundational claim that *understanding an information-processing system requires answers at
  multiple levels*, and that the *computational* level (what problem is solved and why) is often
  primary. We treat Marr's levels as a *paradigm of multi-level understanding* and use it
  throughout Part VIII.
- **Mental models** (Craik 1943, *The Nature of Explanation* — organisms carry small-scale models
  of reality to anticipate events [a cognitive Conant–Ashby]; Johnson-Laird 1983): understanding =
  possessing a **runnable mental model** that supports simulation and inference. This grounds
  "understanding as simulation/mental modeling."
- **Causal cognition and explanation** (Keil 2006 on the structure of explanatory understanding;
  Lombrozo 2006, 2012 on the function of explanation; Sloman 2005 *Causal Models*): humans treat
  explanation as *causal*, prize **simplicity** and **breadth**, and explanation guides learning
  and generalization. The **Illusion of Explanatory Depth** (Rozenblit & Keil 2002): people
  vastly overestimate their mechanistic understanding until asked to produce a step-by-step
  account (and *can't*) — an empirical operationalization of the difference between *feeling* one
  understands and *being able to produce the mechanism*. This is a direct empirical template for a
  **test of understanding**: demand the step-by-step generative account, not the gist.
- **Expertise and chunking** (Chase & Simon 1973; de Groot): experts understand via **hierarchical
  chunks/schemata** — again hierarchy/modularity as the structure of understanding (ties to Simon).
- **Understanding vs. knowledge in epistemology** (Pritchard, Kvanvig, Grimm, Zagzebski): a
  parallel philosophical literature argues **understanding is a distinct epistemic good** from
  knowledge — it is *holistic* (grasping how things hang together), comes in *degrees*, is tied to
  *abilities* (to answer w-questions, to model, to draw inferences), and is *factive about
  dependence relations*. This is the epistemological backbone of our title distinction
  ("knowledge about" vs. "understanding of").

---

## 7. Neuroscience: levels, methods, and the recurring failure modes

Neuroscience is the *primary application target* (Part VIII) and the source of the Jonas–Kording
provocation; here we lay out its conceptual landscape and methods, tagging epistemic objects.

### 7.1 Marr's levels of analysis (the organizing frame)

Marr & Poggio (1976), Marr (1982): **computational** (what is computed and *why* — the goal and
its logic), **algorithmic/representational** (what representations and procedures), and
**implementational** (how realized in hardware/wetware). Marr's lesson, echoing Anderson and
Simon: you can understand at one level while being ignorant of others, and *full* understanding
requires linking levels (and the *why*/computational level is often the most illuminating).
Jonas–Kording is in part a demonstration that *implementational-level data abundance* (record
every transistor/neuron) does not yield computational-/algorithmic-level understanding.

### 7.2 Buzsáki: "inside-out," the neural syntax, reading vs. correlating

György Buzsáki (2006, *Rhythms of the Brain*; 2019, *The Brain from Inside Out*) argues against the
dominant **outside-in/encoding** framing (stimulus → neural response → "representation") in favor
of an **inside-out** view: the brain's self-organized dynamics and **action** come first; meaning
is *grounded by the organism's own actions and predictions*. Methodologically he stresses the gap
between **correlating** neural activity with stimuli (knowledge about) and identifying the brain's
own **neural syntax** and read-out mechanisms (understanding). A neuroscience-internal articulation
of our thesis.

### 7.3 The Churchlands and computational/eliminative neurophilosophy

Patricia Churchland (1986, *Neurophilosophy*) and Paul Churchland: **co-evolution** of neuroscience
and theory; state-space/vector-coding accounts of representation; eliminativist pressure on
folk-psychological categories. Relevant for the claim that *understanding the brain may require
new theoretical vocabulary* (new "relevant variables"), not just more data in old categories.

### 7.4 Computational neuroscience: from Hodgkin–Huxley to normative theories

- **Biophysical/mechanistic models:** Hodgkin–Huxley (1952) — a *how-actually* mechanistic model
  of the action potential, often cited as neuroscience's paradigm of genuine mechanistic
  understanding (and notably *not* obtained by black-box fitting but by hypothesizing
  ion-channel mechanisms and testing interventionally). Compartmental models, cable theory.
- **Normative/computational theories:** efficient coding (Barlow, Atick), predictive coding (Rao &
  Ballard 1999; Friston's free-energy/active inference), Bayesian brain, sparse coding (Olshausen
  & Field 1996), reinforcement-learning/dopamine (Schultz, Dayan, Montague). These deliver
  *computational-level (why)* understanding — often the deepest kind — but must be tied to
  mechanism/implementation to be complete.

### 7.5 Connectomics

Reconstruction of complete wiring diagrams: *C. elegans* (White et al. 1986 — the first
connectome, 302 neurons) and the modern EM connectomes (*Drosophila* hemibrain/FlyWire; mouse
cortex MICrONS). Epistemic object: **complete structural connectivity** (the static "parts list +
wiring"). The deep lesson — anticipated by *C. elegans* and emphasized by Jonas–Kording — is that
**a connectome is necessary but radically insufficient** for functional understanding: even with
the full wiring of 302 neurons, behavior is not "read off" because function depends on dynamics,
neuromodulation, and physiology not visible in the wiring. The connectome is the strongest
real-world case of "complete low-level description ≠ understanding."

### 7.6 Encoding models, decoding models, and the encoding/decoding asymmetry

- **Encoding models** (e.g., receptive-field/Gabor models in V1; voxel-wise fMRI encoding,
  Naselaris et al. 2011; Gallant lab): predict neural responses from stimulus features. Epistemic
  object: a **predictive stimulus→response mapping**; can be *correlational* (a good fit shows the
  feature space is *sufficient to predict*, not that the brain *computes via* those features).
- **Decoding models / "mind-reading"** (Haxby, Kamitani & Tong 2005, Kay et al. 2008): predict
  stimulus/state from neural activity. Epistemic object: **decodability** = *information present*
  in the signal. The **decoding/encoding asymmetry** (Naselaris; deCharms & Zador): decoding shows
  information is *available* to the experimenter, not that it is *used* by the brain, nor *how*.
  Both are powerful for "knowledge about representation," limited for mechanism — the neuroscience
  twin of probing vs. patching (§5.6).

### 7.7 Representational Similarity Analysis (RSA)

Kriegeskorte, Mur & Bandettini (2008). Compares **representational geometries** (dissimilarity
matrices) across brains, models, and behavior — a powerful, model-agnostic way to test *whether
two systems represent stimuli similarly*. Epistemic object: **second-order representational
structure (geometry of similarities)**. Strength: enables model comparison (e.g., DNN-to-brain
matches, Yamins & DiCarlo 2014). Limitation for understanding: a *match in representational
geometry is a correlation/identity at the representational level* — it constrains but does not by
itself reveal the *mechanism/algorithm*, and similar geometries can arise from different
mechanisms.

### 7.8 Neural manifolds and population dynamics

Churchland, Shenoy, Cunningham; Gallego et al. (2017); the "computation-through-dynamics" view:
neural population activity occupies **low-dimensional manifolds**, and computation is understood as
**dynamical-systems structure** (fixed points, rotations, line attractors — Sussillo & Barak 2013
reverse-engineering RNNs). Epistemic object: **dynamical/geometric structure of population
activity** — a genuine *algorithmic-level* understanding (especially when one reverse-engineers a
trained RNN's fixed-point structure), explicitly a multi-scale move from single neurons (parts) to
collective variables (the "right" relevant variables — cf. RG/effective theory). One of the most
promising routes to *understanding* (not just *describing*) neural computation, and a key
exhibit in Part VIII.

### 7.9 Network neuroscience

Sporns, Bassett; graph-theoretic analysis of functional/structural connectivity (modules, hubs,
rich clubs, small-worldness, controllability). Epistemic object: **topological/statistical
description** of connectivity. As in §2.8: rich for *knowledge about* organization; becomes
*understanding* only when topological claims are tied to **mechanism and validated by
intervention** (e.g., does targeted perturbation of a hub produce the predicted functional
change?), and when care is taken that graph metrics are not artifacts of thresholding/processing.

---

## 8. Causal inference: the formal theory of difference-making

Causal inference supplies the formal machinery that turns "mechanism/intervention" talk into
mathematics, and the sharpest statements of *what passive data cannot give you*.

### 8.1 Pearl: SCMs, the do-calculus, and the Ladder of Causation

Pearl (2000/2009, *Causality*; Pearl & Mackenzie 2018, *The Book of Why*). Core apparatus:
- **Structural Causal Models (SCMs):** a set of variables, structural equations, and a DAG; encode
  how each variable is *generated* from its direct causes + noise — i.e., a **mechanism** in
  Pearl's sense (each equation is an autonomous mechanism, *modular* and *invariant*).
- **The do-operator and do-calculus:** P(Y | do(X=x)) formalizes intervention; the three rules of
  do-calculus give a *complete* method for deciding when interventional quantities are
  identifiable from observational data + graph.
- **The Ladder of Causation (three rungs):** (1) **Association** P(y|x) — seeing/correlation (the
  rung of most statistics and standard ML); (2) **Intervention** P(y|do(x)) — doing; (3)
  **Counterfactuals** P(y_x | x', y') — imagining/retrospection. Each rung answers questions the
  one below cannot, and **you cannot climb the ladder from data alone** — you need a causal model
  (assumptions). This is, in our framework, *exactly* the prediction(rung 1)-vs-understanding
  (rungs 2–3) distinction, with a proof that the gap is real and that crossing it requires
  structural assumptions/interventions, not more data.
- **Counterfactuals & mediation:** structural counterfactuals (abduction–action–prediction);
  natural direct/indirect effects (mechanism along paths).

### 8.2 Woodward (again) and the interventionist bridge

Woodward's manipulationism (§1.6) is the *philosophical* counterpart of Pearl's *formal* SCMs;
together they make "explanation/understanding = grasp of intervention-supporting, invariant
dependences" both rigorous and graded (depth = range of invariance). Their convergence is why we
adopt the interventionist–mechanistic synthesis as our backbone.

### 8.3 Rubin/Neyman potential outcomes; the credibility revolution

Potential-outcomes framework (Neyman, Rubin 1974); the fundamental problem of causal inference
(we never observe both potential outcomes); identification strategies (RCTs, IVs, RDD,
diff-in-diff, matching). Epistemic object: **average/heterogeneous treatment effects** — a
specific, valuable causal quantity (the *effect of* a manipulation), which is *intervention-level*
knowledge but typically **not a full mechanism** (it answers "does X make a difference to Y?" not
"by what organized process?").

### 8.4 Invariant Causal Prediction and causal discovery

- **Invariant Causal Prediction (ICP)** (Peters, Bühlmann & Meinshausen 2016): the *causal* set of
  predictors is the one whose predictive relationship to the target is **invariant across
  environments/interventions**; exploit heterogeneity to find causes. Operationalizes Woodward's
  "invariance under intervention" as a *discovery* algorithm, and underwrites **Invariant Risk
  Minimization** (Arjovsky et al. 2019) in ML. Directly relevant: *invariance across environments*
  is one of our core measurable signatures of having recovered mechanism rather than correlation.
- **Causal discovery / structure learning:** constraint-based (PC, FCI — Spirtes, Glymour &
  Scheines 2000, *Causation, Prediction, and Search*), score-based (GES), and functional/asymmetry
  methods (LiNGAM — Shimizu et al.; additive-noise models — Hoyer et al.; post-nonlinear). These
  recover **causal-graph structure** from data under assumptions (faithfulness, sufficiency,
  acyclicity); their reliability/identifiability limits are themselves an object lesson in how much
  structure data alone can yield.

### 8.5 Mechanism discovery and abstraction in causal inference

- **Causal abstraction** (Rubenstein et al. 2017; Beckers & Halpern 2019; Geiger et al.): formal
  conditions under which a **macro** SCM is a faithful *abstraction* of a **micro** SCM (a
  commuting relation between interventions at the two levels) — the causal-inference statement of
  Simon's hierarchy / RG coarse-graining / Rosen's modeling relation, and the formal target for
  **hierarchical consistency** in Part VI. Constructive/exact transformations, τ-abstraction.
- **Actual causation & explanation in CS** (Halpern & Pearl 2005; Halpern 2016, *Actual Causality*):
  formal definitions of token causation and of **explanation** (a minimal set of facts that, given
  the causal model, suffices for the explanandum across the relevant contexts) — a bridge from
  Woodward-style explanation to algorithmic definitions usable in interpretability.
- **Causal emergence** (Hoel, §4.8) recurs here: an *interventionist* criterion for choosing the
  causal level, unifying information theory and causal inference.

---

## 9. Synthesis of Part I: five convergent claims

Across these disciplines, a remarkable convergence emerges that frames the rest of the document:

1. **There is a real gap between association and mechanism, and it cannot be closed by more data.**
   Pearl's ladder (you can't get rung 2/3 from rung 1), CRL/disentanglement unidentifiability
   (Locatello; Schölkopf), Bogen–Woodward (data vs. phenomena), and the connectome lesson all say
   the same thing: *prediction/description underdetermines mechanism.* **This is the formal core of
   the Jonas–Kording/Lazebnik worry and the thesis of this document.**

2. **Mechanism = entities + activities + organization, made precise by interventions.** The New
   Mechanists (MDC, Craver's mutual manipulability), Woodward's interventionism, and Pearl's SCMs
   converge on the same object: organized, invariant, intervention-supporting dependence relations.
   *This is our primary epistemic object for "understanding."*

3. **Understanding is graded and competence-linked.** Craver's sketch→how-actually, Woodward/
   Strevens' depth (range of invariance / abstraction over difference-makers), de Regt's
   intelligibility-as-skill, and cognitive science's runnable mental models all make understanding
   a matter of *degree* and of *what an agent can do* (predict, answer counterfactuals, intervene,
   repair, transfer). *This motivates measurable, competence-based dimensions (Part IV/VI).*

4. **Hierarchy/near-decomposability is the structural precondition that makes complex systems
   understandable — and the right level is the level of the "relevant variables."** Simon
   (ND/hierarchy), Simon–Ando (spectral gap/aggregation), Anderson (more is different), the RG
   (universality/relevant variables), causal abstraction, and causal emergence (EI-maximizing
   scale) all say: understanding lives at a *level* defined by variables under which the dynamics
   **close/commute**, and complex systems are tractable to the extent they are
   nearly-decomposable. *This is the spine of Part V and of "hierarchical consistency" in Part VI.*

5. **Compression is necessary but not sufficient; faithful, mechanism-structured compression is
   the target.** AIT/MDL/Kitcher tie structure to compressibility; but IB/ε-machine caveats,
   superposition, and multiple realizability show a short code can be predictive-but-not-causal,
   opaque, or mechanism-ambiguous. *Understanding requires a short description in a vocabulary of
   interventionally meaningful, composable, hierarchically organized parts whose transitions
   commute with the system's (Rosen) — the synthesis we build in Part VI.*

These five claims are the load-bearing inputs to Parts II–VIII.
