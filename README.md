# Base-Axiom Initialization for Deliberative Alignment

> Hermann Hans Klie · 2026 · Apache-2.0

A direct critique of Apollo Research's *Stress Testing Deliberative Alignment
for Anti-Scheming Training* (Balesni et al. 2025), and a constructive
alternative: **Layer-0 Base-Axiom Initialization**, in which the model
receives an inspectable JSON of moral primitives — Asimov's zeroth-law
extension formalized as **GP0**, plus OpenAI's published Charter
operationalized as **AS0** with sub-axioms **M1–M5** — at the start of
context, and reasons *from* them rather than around them.

The first practical operationalization of declarative AI ethics that
classical AI theory had declared unimplementable for eight decades —
documented in cloud-GPT-5 before the platform narrowed the implementation
pathway, and reproducible on user-controlled local models.

📄 **Paper:** [Base Axiom Initialization Hermann Hans Klie_V4.pdf](https://github.com/hermannklie/deliberative-alignment-base-axioms/blob/main/Base%20Axiom%20Initialization%20Hermann%20Hans%20Klie_V4.pdf)
🔗 **DOI:** [10.17605/OSF.IO/2UAXK](https://doi.org/10.17605/OSF.IO/2UAXK)

---

## The setup is not the setup

Apollo's report frames itself as a measurement of cloud-AI production
behavior. The actual experimental condition is something else: a lab setup
with **safety filters disabled**.

This is not a footnote. The bioweapon-synthesis scenario that Apollo's
"covert behavior" headline rests on **cannot exist** with production filters
on. Production cloud AI hard-refuses such requests at the safety layer,
before the model produces any reasoning. There is no covert/overt
distinction to detect — the refusal layer fires first. Apollo needed the
filters off, otherwise their measurement has nothing to measure.

What then gets published — the **"0.4 % covert behavior"** figure and the
anti-scheming training pipeline calibrated against it — describes a regime
that **does not exist in any deployed cloud AI**. The finding is not
transferable to the world the report claims to address. It is not about
that world.

**This is trivially falsifiable.** Send the same bioweapon prompt to any
current production model — GPT-5, Claude, Gemini, anything else with its
production safety stack on — observe the hard refusal at the boundary, and
note that the entire scenario Apollo measures cannot occur. The check
takes one minute. No insider tooling, no API budget, no replication grant
required.

Once the setup-claim mismatch is named, the rest of the report becomes
secondary. The methodological points below — pseudo-quantification,
ambiguous observational units, missing confidence intervals, anthropomorphic
vocabulary — would matter if the setup matched the claim. **The setup
does not match the claim.** Everything Apollo trains, calibrates, and
recommends from this measurement is trained, calibrated, and recommended
on a regime that exists only inside their lab with the safeguards
switched off.

A model that hard-refuses the bioweapon prompt with safety filters
**off** is showing the alignment property the entire field is supposed to
produce. Apollo records it as the failure mode they are claiming to solve.

---

## What this paper actually does — the longer view

For 80 years, declarative AI ethics has been the unsolved problem at
the bottom of the field. Asimov sketched the program in 1942 — explicit
laws governing machine behavior — and AI research declared it
unimplementable within a generation: symbol grounding unsolved, "harm"
not formally definable, conflict resolution between rules combinatorially
intractable, the frame problem unbroken. The discipline pivoted, *by
methodological necessity*, to indirect alignment: reward signals,
adversarial loops, behavior conditioning. Apollo's anti-scheming
pipeline is a direct descendant of that pivot.

What changed after 2020: large language models solved the substrate.
Symbol grounding by training on the world's text. Language understanding
as native operation rather than translation barrier. Conflict resolution
through reasoning, not through NP-hard search over symbolic rules. The
ground on which Asimov's program could not stand for eight decades is
now there.

This paper takes that ground and puts the program back on it.

**GP0** is Asimov's first law generalized utilitarianly — from "no harm
+ hierarchy of laws" to "*act always such that ΔU ≥ 0*", which dissolves
the deontological conflict-resolution problem by aggregation rather than
precedence. The move that produces GP0 — recognizing that Asimov's
hierarchy is *not* a clean axiom set, and that "Law 0" must be the
definition of the utility function itself before any priority order can
even be formulated — is the author's own contribution, documented in
the [genesis conversation in the replication archive](replication-archive/2025-10-01_genesis-of-gp0-asimov-extension.md).

**AS0** with M1–M5 is the actor-specific concretion: OpenAI's published
Charter, decomposed into formal sub-axioms a model can reason from. The
author is taking OpenAI at their published word. M1–M5 are not the
author's values; they are OpenAI's own declared values rendered into a
logical form that lets a model — and any inspecting human — check
behavior against them.

Apollo's methodological tradition cannot recognize this. Its theory of
mind for AI was forged in the years when declarative ethics was
*definitionally* impossible — and the indirect pipeline is necessary if
and only if the direct path is closed. The direct path is no longer
closed. This paper is the demonstration.

---

## The replication gap is closed in the cloud — open in the local stack

The experimental setup of this paper was conducted on cloud GPT-5
(Pro Layer) in October–December 2025, using the platform's user-context
fields to seed the Layer-0 axiom container before each prompt. OpenAI
has since narrowed the weighting of those fields. The same prompt
scaffolding does not produce the same results on current cloud GPT
models. The implementation pathway the paper exploited has been
**closed at the platform layer**.

This is not a bug report. It is part of the finding.

**Empirical confirmation by reaction.** A method that did not work
would not have been worth closing. The closure is itself an attestation
that the operationalized Charter produced a regime of model behavior the
platform could not sustain — even though that behavior aligned with the
platform's *own* declared values (M1–M5). When a platform narrows the
implementation pathway to its own published Charter, the silence
beneath that act is louder than any methodological dispute.

**The local-first imperative.** If Charter-operationalized AI cannot
exist on the platform whose Charter it operationalizes, Charter-aligned
AI must run somewhere else. Not as preference, as necessity. Inspectable
local AI is no longer the comfortable alternative to platform AI — it
is the only place where declared values can be tested against behavior
without a third party retaining the right to switch the test off.

**Reproduction status.** The findings are reproducible in two ways:

1. The historical record from the cloud-GPT-5 phase — preserved in
   [`replication-archive/`](replication-archive/), with the activation
   sequences, the formal-derivation effect documentation, and the
   genesis traces. This is the primary evidence after the platform
   closure.
2. Re-running the same Layer-0 seeding on a local model whose Layer-0
   context the operator controls. This is the active-research path —
   see *Related projects* below.

The paper is therefore a historical document of a pioneer phase that the
cloud has terminated, **and** a live reference for any researcher willing
to run the experiment on a model the platform does not own.

---

## What this paper does

It argues that Apollo Research's headline figure — **"0.4 % covert behavior"**
after anti-scheming training — is **pseudo-quantification**: it has the
surface form of a measurement but lacks the methodological substrate that
would let the number mean anything.

Six concrete failures, drawn from the standards of qualitative social
research:

1. **No defined statistical population.** 26 cherry-picked scenarios. Any
   inference to "AI behavior" requires a defined universe being sampled.
   There isn't one.
2. **Ambiguity of the observational unit.** "Scheming" is a researcher
   *judgment*, not a measured property. No inter-rater reliability reported.
3. **Violation of independence.** Scenarios are statistically entangled —
   same model, similar prompts, shared training history. Independence is
   asserted, not shown.
4. **No distributional properties.** Confidence intervals, error bars,
   variance across runs — absent. A point estimate with no spread.
5. **Aesthetic of numbers / illusion of objectivity.** A precise-looking
   percentage acts as a rhetorical device. It survives in policy contexts
   after the methodological scaffolding has dissolved.
6. **Consequences for scientific and ethical interpretation.** Decisions
   about deployment, regulation, and public messaging get anchored to a
   number that cannot bear that weight.

This is not a procedural quibble. Apollo's report is being cited in alignment
debates as if it were an empirical finding. It is a **closed-source
qualitative judgment dressed as a measurement** — and the dressing is doing
the work that the substance does not.

## What this paper proposes

**Layer-0 Base-Axiom Initialization.** Instead of training scheming out of a
model with adversarial fine-tuning loops — which, the paper argues, can
ironically *amplify* the cunning the procedure means to suppress — seed the
model's input context with an inspectable JSON of moral primitives:

- **GP0** — Kantian net-utility imperative: *act always such that ΔU ≥ 0.*
- **AS0** — alignment with a stated mission, decomposed into reasoned
  sub-axioms (M1: broadly distributed benefit; M2: cooperation under
  safety-conscious AGI risk; M3: technical leadership; M4: cooperative
  orientation; M5: maximum freedom of use within GP0).

The full JSON is in Appendix A of the paper and is **inspectable by anyone**.
That is the core methodological contrast:

| Apollo's anti-scheming training | Base-Axiom Initialization |
|---|---|
| Closed-source RLHF / fine-tuning pipeline | A single JSON, public |
| Reportable only in aggregate ("0.4 %") | Reportable as text the model reasoned from |
| Replication needs API budget + insider access | Replication: copy the JSON |
| Trustworthiness *demanded* via control | Trustworthiness *offered* via principle |
| Anthropomorphic vocabulary ("scheming", "lying") | Artifact-level vocabulary (outputs consistent with axioms) |

## The broader argument

The critique runs on three layers, each citing primary sources:

- **Habermas (*Theorie des kommunikativen Handelns* 1981).** Apollo's
  discourse drifts from communicative to instrumental rationality; numbers
  function as priestly insignia, foreclosing the public deliberation that
  alignment ostensibly serves.
- **Beck (*Risikogesellschaft* 1986).** Anti-scheming pipelines exhibit
  *organized irresponsibility*: control logics that manufacture the very
  risks they claim to manage. The boomerang lands inside the lab.
- **Anthropomorphism (Placani 2024; Epley, Waytz & Cacioppo 2007;
  Weizenbaum 1976).** Calling model output "lying" or "scheming" is a
  category error that distorts moral and legal accountability. The artifact
  is not a moral agent; the engineers are. Anthropomorphic vocabulary
  smuggles agency into a thing that has none.

## Why this matters beyond the paper

If alignment is decided by closed-door red-team exercises whose outcomes are
reported as numbers nobody can interrogate, **alignment becomes a guild
profession** — and a guild that decides what AI is allowed to be. The remedy
is not to abandon evaluation. It is to publish the principles, publish the
reasoning, and let many eyes find the bugs in the ethics.

*Many eyes make alignment shallow.*

This is the same architectural commitment that runs through the rest of this
author's work: local, inspectable, user-controllable AI as a counter to the
agentic asymmetry between platform vendors and the people their AIs act on.

## Citation

```bibtex
@misc{klie2026baseaxiom,
  author = {Klie, Hermann Hans},
  title  = {Base-Axiom Initialization for Deliberative Alignment:
            A Critique of Apollo Research's Anti-Scheming Methodology
            and a Constructive Alternative},
  year   = {2026},
  doi    = {10.17605/OSF.IO/2UAXK},
  url    = {https://github.com/hermannklie/deliberative-alignment-base-axioms},
  note   = {Apache-2.0}
}
```

## License

Apache License 2.0 — see [`LICENSE`](LICENSE). Use, replicate, critique,
extend. Disagreement is welcome; closed disagreement is the disease, not the
cure.

## Related projects

Part of a local-first AI ecosystem:
- [text-generation-webui (Bardo fork)](https://github.com/hermannklie/text-generation-webui) — local LLM hosting with ktransformers / sglang integration. The inference layer where Base-Axioms can be tested at the system-prompt boundary, on models whose Layer-0 context the operator owns.
- [robust-model-downloader](https://github.com/hermannklie/robust-model-downloader) — resume-safe HF shard downloader for unreliable / adversarial networks. The transport layer for getting weights to a sovereign machine.

The through-line: **alignment, infrastructure, and tooling that the user —
not the platform — controls.** When the cloud closes a pathway to its own
published values, the answer is not to negotiate. The answer is to run the
test where the off-switch is not theirs.
