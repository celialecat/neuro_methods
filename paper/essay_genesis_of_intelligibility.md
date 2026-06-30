# The Genesis of Intelligibility

### Why we can fix a radio but not a brain — and why interpretability is biology, not engineering

*An essay distilling the original thesis of this project. Companion to the position paper; technical
development in Part IX.*

---

Yuri Lazebnik asked whether a biologist could fix a radio, and Eric Jonas and Konrad Kording asked
whether a neuroscientist could understand a microprocessor. Both answered, in effect, *no* — the
standard analytic toolkit, applied to a system whose mechanism is fully known, recovers
descriptions, correlations, and tuning curves that look like insight but are not the mechanism. The
usual moral is methodological self-flagellation: *our techniques are too weak.* I want to argue for a
different, and I think deeper, moral. The reason these thought experiments bite is not only that our
methods are weak. It is that **intelligibility is not a property a system simply has; it is a fossil
of how the system was built** — and the systems we most want to understand were built by processes
that imprint no such fossil.

## Prediction is the ε-machine; understanding is the ι-machine

Start with what "knowledge about" versus "understanding of" means formally. Computational mechanics
gives us the *ε-machine*: the smallest model that predicts a process optimally, built entirely from
the statistics of observation. It is the mathematical ideal of prediction — and two systems with the
same input–output statistics have the *same* ε-machine even if their guts differ completely, because
the difference between their guts only shows up when you *intervene*.

So define the object the ε-machine is missing: the **ι-machine**, the smallest model that is *closed
under intervention* — that answers not just "what comes next?" but "what comes next if I cut *this*
wire?" for every cut you can make. The ι-machine is never smaller than the ε-machine, and the gap
between their sizes, `C_ι − C_μ`, is a number: **the amount of mechanism that no quantity of passive
data can ever reveal.** For a designed pocket calculator the gap is near zero — predicting it and
understanding it nearly coincide. For a brain or a large language model the gap is enormous. That gap
is the formal residue of Jonas and Kording's finding: the missing bits are not in the data, and so
no method confined to the data — no encoding model, no decoder, no representational-similarity
analysis, no probe — can supply them. You have to poke the system, and you can only ever understand
it as finely as you can poke it. (That last clause is a theorem, not a slogan: understanding is
determined only up to the equivalence the intervention repertoire can resolve. Your interventions
are your aperture; you cannot see below their grain.)

## The Genesis Principle

Now the central claim. Why is the microprocessor, in principle, *understandable* at all — why does it
have a clean hierarchy of gates, registers, and instructions for us to recover? Herbert Simon told us
that persistent complex systems are nearly decomposable; but he left open *why*. Here is the answer I
propose:

> **A system's intelligibility is bounded by the structure imprinted on it by the process that built
> it. A builder that proceeds by understanding — a designer — necessarily stamps her own modular,
> hierarchical, intervention-closed plan onto the artifact. A builder that proceeds without
> understanding — natural selection, gradient descent — is under no such obligation, and will
> happily produce entangled, distributed, holistic solutions whenever they are cheaper or fitter.**

The decomposability of a radio is not luck. It is the *trace of the engineer's bounded mind*: she
could not have built the radio without breaking it into stages she could each hold in her head and
connect across interfaces she specified. The very finitude that forces a designer to modularize is
what later lets us reverse-engineer her product. **Intelligibility and buildability-by-an-understander
are the same constraint, seen twice.** A designed artifact wears its designer's ι-machine on the
outside.

Evolution and stochastic gradient descent wear nothing on the outside. They search the space of
*behaviors*, not the space of *comprehensible mechanisms*. Nothing stops them — and much encourages
them — from discovering dense, polysemantic, superposed solutions that pack more function into fewer
parts precisely by *violating* the clean modularity a human designer would have imposed. Superposition
in neural networks is not a curious anomaly; it is exactly what you should expect from a
compression process that was never asked to be understood.

## The uncomfortable consequence

This reframes the two founding thought experiments and points past them.

The microprocessor was the *easy* case, and Jonas and Kording's result is therefore worse than it
looks: our methods failed on the *most intelligible kind of system there is* — one literally
structured by an understanding mind. We should not comfort ourselves that the brain is just a bigger
chip. The brain was assembled by evolution, development, and learning — three processes that
understand nothing. The Genesis Principle predicts that the brain need not carry a designer's clean
decomposition at all, and that methods calibrated on engineered intelligibility will be
systematically *over-optimistic* about it. The correct null hypothesis for a brain is not "hidden
modularity waiting to be found" but "partial, grudging, incidental modularity in a substrate that is
holistic wherever holism paid off."

And mechanistic interpretability of neural networks inherits this fate exactly, because a trained
network is built by an understanding-free optimizer. The prediction is concrete: interpretability
will succeed on the sub-problems where *incidental* pressures happened to imprint structure — the
narrow induction heads, the modular-arithmetic circuits, the tasks squeezed through architectural
bottlenecks — and it will stall on the densely-optimized capabilities that matter most. Which is, so
far, what we see. **Interpretability is not reverse-engineering a CPU. It is reverse-engineering
biology** — and it should adopt biology's expectations: degeneracy, distributed codes,
context-dependence, and the real possibility that there is no tidy circuit to find.

There is a hopeful corollary, though, and it is actionable. If intelligibility is imprinted by the
generator, then **we can choose to imprint it**: bias the optimizer toward leaving a fossil —
modularity priors, bottlenecks, sparsity, curricula that build capabilities compositionally.
Interpretability, on this view, is not only a post-hoc analysis we perform on a finished model; it is
partly a *training-time decision* about how much structure we force the generator to lay down. If we
want understandable AI, we should build it the way an engineer builds a radio: by composing parts we
understand — or at least by paying the optimizer to pretend it is one.

## The horizon

A last, sobering thought. The understander is itself a finite system, and by Ashby's law it can only
model what its own variety can hold. To carry a system's ι-machine you need at least as many effective
bits as the ι-machine has; when you do not, you are forced to coarse-grain — which is why we build
hierarchies in the first place, and why a child, a student, and an expert "understand" the same engine
at different grains. But coarse-graining only rescues you if a *closed* coarser level exists. Some
systems may have none: their ι-machine admits no faithful simplification, and the only model as
accurate as the system is as large and as tangled as the system itself. Such systems would be
*understandable in principle and by no bounded agent in practice* — beyond the **understanding
horizon**. I suspect whole brains and frontier networks lie partly past it at the mechanistic level.
That is not mysticism; it is the 1:1 map. It means the honest goal for those systems may not be a
complete mechanism but a stack of the best *closed levels* we can find, an explicit accounting of
where no such level exists, and instruments — optogenetics, single-weight edits, causal scrubbing —
that widen our aperture rather than merely pile up more observation. Because in the end the history
of understanding is not the history of collecting more data. It is the history of building better
ways to intervene.
