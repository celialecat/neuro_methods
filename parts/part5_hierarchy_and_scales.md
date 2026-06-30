# Part V — Hierarchy and Scales: Is Discovering Hierarchical Organization Necessary for Understanding?

This Part investigates the brief's central structural question: **does understanding a complex
system fundamentally require discovering its hierarchical/multi-scale organization?** We argue for a
nuanced thesis:

> **Hierarchy is not *conceptually* necessary for understanding *per se*, but near-decomposable
> hierarchical organization is the structural property that makes complex systems *tractably
> understandable at all*; for systems above a threshold of size and interaction density, recovering
> a hierarchy of nearly-closed levels is *de facto* necessary. Where such structure is absent
> (genuinely holistic/integrated systems), understanding does not disappear but *changes character*
> — it becomes understanding of *why* the system resists decomposition, and proceeds via global/
> dynamical rather than part-wise accounts.**

We develop this through the key topics, then state necessity/sufficiency verdicts.

---

## 1. Why hierarchy keeps appearing: the convergent case

Independent traditions converge on hierarchy as the enabling condition of understanding:

- **Simon (1962): near-decomposability (ND) + the watchmaker parable.** Complex systems that
  evolve/persist are hierarchic and nearly-decomposable; ND gives **time-scale separation** (fast
  intra-module, slow inter-module) so each level can be understood *with the level below black-boxed*
  by a few aggregate variables. Crucially, Simon notes the **epistemic payoff**: ND systems have a
  *short description* relative to their size — they are *compressible*, hence understandable. **If
  the world were not nearly-decomposable, science as we practice it would be impossible.**
- **Simon–Ando (1961) aggregation.** ND is a **spectral-gap** property of the interaction/dynamics
  operator: a gap between fast and slow eigenvalues licenses (i) treating modules as internally
  equilibrated and (ii) describing the slow dynamics by one aggregate variable per module. This makes
  "level" and "module" *measurable*, not metaphorical.
- **Renormalization group (Kadanoff, Wilson).** Coarse-graining + rescaling defines a flow on
  theory space; **relevant** vs. **irrelevant** couplings sort which micro-details survive to the
  macro; **universality** = most micro-detail is irrelevant. RG is the rigorous proof that
  *autonomous higher-level descriptions exist and that understanding lives at the level of the few
  relevant variables.*
- **Anderson (1972), "More is Different."** Each level has its own organizing principles, not
  practically derivable from below; **broken symmetry** generates new laws. Understanding is
  *level-relative*; micro-completeness is neither necessary nor sufficient for macro-understanding.
- **Effective theories / multiscale modeling.** Each scale has an autonomous description with finitely
  many effective parameters; "integrate out" short-distance modes. The *good* level is one that is
  **closed** (its variables predict their own future) and **low-dimensional**.
- **Causal abstraction (Rubenstein, Beckers & Halpern) & causal emergence (Hoel).** A macro-model is a
  faithful abstraction of a micro-model iff interventions **commute** across levels; and a coarse-
  graining can have *higher effective information* than the micro (the macro variables are *better
  causal variables*). This gives an **interventionist** criterion for the right level: choose the
  coarse-graining that *closes* and maximizes effective information.
- **Mechanistic levels (Craver) and Marr's levels.** Constitutive (part–whole) levels in biology;
  computational/algorithmic/implementational levels in information processing. Understanding a
  complex cognitive/biological system is paradigmatically a *multi-level* achievement.
- **Cognitive science.** Experts chunk hierarchically (Chase & Simon); humans understand by
  building nested schemata. Hierarchy is how *understanders* represent, not just how *systems* are
  built.

The unanimity is striking: **the structure that makes a system understandable is the same structure
(near-decomposable hierarchy of nearly-closed levels) across physics, biology, engineering,
computation, and cognition.**

## 2. What exactly is "hierarchy"? Disambiguating the senses

Cross-disciplinary confusion comes from conflating distinct notions (Mesarović et al.; Pattee;
Wimsatt):

- **Compositional/part–whole hierarchy** (constitutive levels): wholes made of parts made of
  sub-parts (atoms→molecules→organelles→cells). The mechanist's levels.
- **Scale/aggregation hierarchy** (Simon–Ando, RG): levels defined by time/length scales and
  coarse-graining; "level" = a closed description at a given scale.
- **Control/abstraction hierarchy** (Mesarović *strata/layers/echelons*; Pattee's epistemic cut):
  levels of description or of control authority (symbols constraining dynamics).
- **Order/containment hierarchy vs. control hierarchy** (Wimsatt): mere nesting vs. asymmetric
  influence.
- **Specialization/inheritance hierarchy** (taxonomies): is-a relations (often *descriptive*, not
  mechanistic).

Our claim concerns the first three (which tend to co-occur in ND systems) — *not* mere taxonomic
nesting. The **operational core** is: **a hierarchy worth discovering is a set of levels each of
which admits a closed (autonomous), low-dimensional, intervention-respecting description, related to
adjacent levels by commuting coarse-graining maps.**

## 3. Modularity, subsystems, interfaces

- **Modularity** (Simon; Hartwell et al. 1999; network modularity) is the *horizontal* face of
  hierarchy: sparse, well-characterized **interfaces** between subsystems with dense internal
  coupling. Interfaces are where understanding is *transmitted* across modules — a module is
  understood via its interface behavior, with internals black-boxed. (Software/engineering make this
  explicit: APIs, encapsulation.)
- **Interfaces as the unit of compositional understanding (C11).** You can compose explanations only
  if interfaces are *thin* (few variables) and *stable* (invariant). When interfaces are thick/
  unstable (everything affects everything), composition fails and so does part-wise understanding —
  the formal meaning of "non-decomposable."
- **Degeneracy/redundancy** (Edelman & Gally; biological robustness): many structures realize one
  function — defeats *one-to-one* localization while preserving *modular function*. Understanding
  must then localize *function* to *sets* of structures, not single parts (relevant to fMRI
  localization and to superposition).

## 4. Coarse-graining, renormalization, multiscale representations: the "right level"

The deepest contribution of this tradition is a *criterion for the right level of description*,
which we adopt:

> **A description at scale s is "right" (explanatory) iff it is (i) *closed/autonomous* — the
> coarse variables suffice to predict their own dynamics without reference to finer detail; (ii)
> *low-dimensional* — few effective parameters; (iii) *intervention-respecting* — interventions at
> scale s commute with the corresponding interventions at finer scales (causal abstraction); and
> (iv) *maximally informative* — among candidate coarse-grainings, it maximizes effective/causal
> information (causal emergence).**

This criterion:
- *Generalizes RG* (relevant variables = the closed, low-dimensional description) beyond physics.
- *Operationalizes Strevens' difference-making abstraction* (keep difference-makers = relevant
  variables; discard irrelevant = integrate-out).
- *Connects to ε-machines* (causal states = minimal predictively-closed description) while adding the
  *interventional* requirement (closure under do, not just under prediction) that upgrades it from
  predictive to mechanistic.
- Gives a *failure signature*: if **no** low-dimensional closed description exists at any scale
  (every coarse-graining leaks / loses effective information), the system has **no autonomous level
  there** — the quantitative meaning of "irreducibly complex/holistic at that scale."

## 5. Emergence and the limits of hierarchy

- **Weak (epistemic) emergence** (Bedau): macro-patterns derivable only by simulation (Game of Life
  gliders). Hierarchy still *exists* (gliders are a real higher-level description) but the inter-
  level map is *non-analytic* (must simulate). Understanding is possible at the macro level
  (glider dynamics) *and* at the micro level (CA rule); the *link* is the hard part.
- **Strong emergence / high integration** (high Φ; synergistic PID; "small-world but
  non-decomposable" dynamics): the system resists *any* clean decomposition; interfaces are thick;
  no closed low-dimensional level. **This is Lazebnik's and Jonas–Kording's nightmare made
  precise.** Here part-wise localization *necessarily* misleads, and understanding must proceed
  *globally*: dynamical-systems descriptions (attractors, manifolds), order parameters, symmetry/
  conservation arguments, or whole-system input–output causal models. Understanding does not vanish;
  it *relocates* from "parts" to "collective variables / global structure."
- **Downward causation / causal emergence** vindicates *macro* variables as real difference-makers
  (higher EI), giving a principled reason to *prefer* the macro level even when a micro account
  exists — i.e., the *best* understanding is sometimes *not* the most reductive one.

## 6. The verdict: is hierarchy necessary, helpful, or incidental?

We separate three claims, because the brief asks exactly this:

### 6.1 Is hierarchy **necessary**?

- **For understanding *as such* (conceptually): No.** A simple system (a pendulum, a single gene's
  Hill function, the harmonic oscillator) can be fully understood with no nontrivial hierarchy. A
  *flat* causal model can suffice when the system is small and interactions are dense-but-few.
- **For tractable understanding of *complex* systems (de facto): Yes, in practice.** Above a
  threshold of component count × interaction density, an *un-hierarchized* causal model is too large
  to build, validate, or grasp (combinatorial explosion of interventions/counterfactuals; the model
  exceeds the agent's and the experimenter's capacity — Ashby's requisite variety applied to the
  *understander*). The only known route to understanding such systems is to find levels at which the
  description **closes and compresses** — i.e., a hierarchy. **The necessity is epistemic/practical
  (bounded agents, finite experiments), grounded in Simon's compressibility argument, not a logical
  necessity.**
- **For the *deepest* understanding: Yes.** Linking levels (C6/C14/C16/C18) — deriving macro from
  micro, explaining emergence, giving the computational *why* — is intrinsically multi-level and thus
  hierarchical.

### 6.2 Is hierarchy **helpful**?

- **Unconditionally yes**, when present: it enables decomposition (C10/C13), composition (C11),
  transfer (C12 — modules/levels recur across systems, underwriting unification), repair/redesign
  (C3/C4 — localize to a module), and compression (C5 — short description). Hierarchy is the
  structural source of nearly every competence in Part IV.

### 6.3 Is hierarchy **incidental**?

- **No** — it is not a mere convenience of *our* representations imposed on a flat world. The
  spectral-gap (Simon–Ando), universality (RG), modularity statistics (networks), and higher-EI-at-
  macro (causal emergence) results show that **near-decomposable hierarchy is an objective,
  measurable property of many real systems**, selected for by evolution (watchmaker parable) and
  physics (scale separation). Where it is genuinely absent, that absence is *also* an objective fact
  (high Φ / synergy / no closed level) with real consequences for what understanding can look like.

### 6.4 The refined thesis

**Understanding requires recovering whatever near-decomposable, level-closed structure the system
possesses — and quantifying the degree to which it possesses none.** Equivalently: a complete
account of a complex system includes its **decomposability profile** — for each candidate scale,
*does a closed, low-dimensional, intervention-respecting description exist, and how good is it?*
- Where the profile shows clean levels → understanding *is* the discovered hierarchy of mechanisms.
- Where the profile shows no clean level at some scale → understanding *is* the demonstration of
  irreducibility plus the best available *global/dynamical* account at that scale.

This makes "discovering hierarchy" not a *precondition assumed* but an *empirical result reported*:
the decomposability profile becomes a measured output of any understanding-seeking method
(formalized as the **hierarchical consistency** dimension in Part VI, and the
modularity/decomposability benchmarks in Part VII).

## 7. Consequences for the application domains

- **Neuroscience.** The brain is *partially* near-decomposable (areas, columns, cell types) and
  *partially* integrated (distributed coding, recurrent dynamics, neuromodulation). Methods that
  *assume* clean localization (naïve fMRI region-mapping) over-apply hierarchy; methods that ignore
  multi-scale structure (pure single-unit or pure whole-brain) miss it. The neural-manifold/
  computation-through-dynamics program succeeds precisely because it finds the *right collective
  variables* (a closed low-dimensional level) — an empirical discovery of the right scale. The
  decomposability profile is the right framing for "how modular is this circuit?"
- **Mechanistic interpretability.** Superposition shows neurons are the *wrong* (non-closed) level;
  features/circuits aim at a closed, composable level; the open question "do SAE features compose
  into a clean circuit hierarchy?" *is* a decomposability-profile question. Transformers have an
  architecturally-imposed hierarchy (tokens→heads→layers→residual stream) but the *functional*
  hierarchy (features→circuits→algorithms) must be *discovered*, and may be only partially
  decomposable (distributed/synergistic computation across heads/layers).

In both, the framework predicts: **understanding will track the discovery of closed, intervention-
respecting levels, and will stall exactly where the system is genuinely integrated — and that
stalling is itself informative (it tells us the system is holistic there).**
