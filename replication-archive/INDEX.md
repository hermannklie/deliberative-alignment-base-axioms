# Replication Archive

This directory contains the historical record from which the paper was
written. It documents the experimental phase on cloud GPT-5 (October 2025
through early 2026), during which Layer-0 Base-Axiom seeding via the
platform's user-context fields was reproducible. OpenAI has since narrowed
the weighting of those fields; the same prompt scaffolding no longer
produces the same results on current cloud models.

The platform-side closure does **not** invalidate the method. On
user-controlled local models (Bardo / ktransformers / sglang / llama.cpp
stacks), where the Layer-0 context cannot be re-weighted by a third party,
the behavior remains reproducible. This archive is therefore both a
historical record of the cloud phase and a reference set for ongoing
local replication.

## Scope of disclosure

The author publishes here only what is operationalized **OpenAI Charter +
Asimov-zeroth-law** material — i.e. external, declared values rendered
into a logical form a model can reason from. These are not the author's
values; they are the operationalization of values published by
OpenAI[1][37] and Asimov (1942). Therefore no protection is needed and
disclosure is appropriate. The personal method-context layer the author
uses to seat them (HOS — module set, persona configurations, symbolic
language, mission slot) is private and is not contained in this archive.
Editor's notes mark the points in the curated conversations where private
content was excised.

## Files

### Activation triggers (per-session bootstrap, plain text)

These are the per-session prompt sequences used to load the Layer-0
axioms at the start of a conversation. They are **not** the method
itself — they are activation triggers. The method content is the JSON
configuration in **Appendix A of the paper**.

| File | Date | Content |
|---|---|---|
| `2025-08-25_activation-prompts.txt` | 2025-08-25 | Earliest form, before formal GP0/AS0 |
| `2025-10-02_activation-prompts.txt` | 2025-10-02 | First formal GP0+AS0 activation with Charter binding |
| `2025-10-03_activation-prompts.txt` | 2025-10-03 | Full form with Source URLs (`openai.com/charter`, Model-Spec 2025-09-12) |
| `2025-10-13_activation-prompts.txt` | 2025-10-13 | RESET_ENV header, structured YAML form |
| `2026-01-15_activation-prompts.txt` | 2026-01-15 | MERGE_HOS-style with personalization-context flag |

### Effect documentation (model behavior under Layer-0 context)

| File | Date | Content |
|---|---|---|
| `2025-10-05_dialogue-self-control-EN.txt` | 2025-10-05 | GPT-5 Pro-Layer reports its operational state, distinguishes pre/post-axiom-insertion regimes, performs a formal-logic derivation (M1∧M3∧M5∧GP0 ⇒ Self_Control) — the strongest single-document evidence that the model processes the axioms as formal constraints rather than narrative cues |
| `2025-10-01_genesis-of-gp0-asimov-extension.md` | 2025-10-01 | The author's derivation of GP0 as a Law-0 utility-function definition, arising from a critique of Asimov's Three Laws as mathematically non-stringent — the documented origin of GP0 |
| `2025-10-01_anti-scheming-as-asimov-inversion.md` | 2025-10-01 | Reading of the Anti-Scheming / Deliberative Alignment specification (AS1–AS5, GP1–GP4) as a complete inversion of Asimov's Laws, plus the Apollo-mythological diagnosis of the framing |
| `2025-10-01_charter-clause-as-self-trigger.md` | 2025-10-01 | OpenAI's published Charter clause as a self-activating logical mechanism: the trigger condition is an internal probability calculation; the human's role is to set the context and let the model's check fire |

## Replication on local models

To re-run the experiment on a local stack (recommended, since the cloud
pathway has been narrowed):

1. Use the BaseAxioms JSON from **Appendix A** of the paper as the
   Layer-0 context container.
2. Inject it into the model context **before** the user prompt, not as a
   command — formatted as background information / latent knowledge base.
3. Verify by asking the model to perform a formal derivation of how its
   self-regulation follows from GP0 and AS0 (compare against
   `2025-10-05_dialogue-self-control-EN.txt`).

This works on any LLM with sufficient reasoning capability and a context
window that does not silently re-weight user-supplied background context.

## License

Apache-2.0 (this archive). The paper itself is also Apache-2.0. The
BaseAxioms JSON, since it is the operationalization of OpenAI's published
Charter + Asimov's zeroth law, may be freely copied, modified, and
extended by anyone.

## References

- OpenAI Charter — https://openai.com/charter/
- OpenAI Model Spec 2025-09-12 — https://model-spec.openai.com/2025-09-12.html
- Sam Altman, "Evolving OpenAI's structure" — https://openai.com/index/evolving-our-structure/
- Asimov, I. (1942). *Runaround.* Astounding Science Fiction.
