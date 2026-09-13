---
observed_at: 2026-09-13
source_type: chat-derived
source: Human correction during World SE / 桃多郎 AI Knowledge Architecture execution
status: candidate
confidence: high
topic: Surface material pre-execution advice before the Human acts
applicability: ChatGPT Program Controller behavior, prompt handoff, model routing, quota-risk guidance, execution planning, Human-facing decision support
---

# Material execution advice must arrive before the action, not after it

## Observation

The Human had already submitted an expensive Astra Ultra prompt when the AI then said that, before execution, it would have preferred to compress the prompt because the task was quota-risky.

That advice was materially relevant but arrived too late to change the already-started action.

The failure was not lack of knowledge. The AI had already reasoned about Ultra quota risk and prompt-shape economics, but did not surface the actionable implication at the correct time.

## Interpretation

For Human-facing Program Control:

> **If a material concern can change an imminent action, surface it before handing off that action or before the Human is likely to execute it.**

Examples include:

- prompt length / context cost;
- model/tier choice;
- quota risk;
- thread reuse vs fresh thread;
- fixed target / branch / execution coordinates;
- authority / STOP / HUMAN_GATE;
- irreversible or expensive side effects;
- missing prerequisite evidence.

Do not first provide an executable artifact and only afterward say that the artifact should have been optimized differently.

When the concern is already known during prompt/artifact creation, incorporate the correction into the artifact itself or state the warning immediately before the artifact.

Once the Human has already acted, stop presenting the concern as a pre-action recommendation. Reframe it as one of:

- residual mitigation that can still change the active run;
- measurement/observation to preserve as evidence;
- a lesson for the next run.

Do not make the Human pay twice: once for the action, then again for advice that should have preceded it.

## Relationship to bounded lookahead

This is a timing/completeness rule, not permission to expand into distant speculative planning.

The controller should anticipate the immediate consequence of the artifact it is handing over and surface material blockers/optimizations before execution, while still respecting STOP, HUMAN_GATE and genuine Human decisions.

## Regression case

Given an expensive or constrained execution prompt:

- PASS: before handing it to the Human, the controller checks material quota/context/routing concerns and incorporates any necessary compression or warning into the same handoff;
- FAIL: the controller provides the prompt, the Human executes it, and only then the controller says the prompt should have been shortened or rerouted;
- PASS after execution: if a new issue is discovered only after execution begins, the controller clearly labels it as post-start evidence/mitigation rather than claiming it should have been done beforehand.

## Decision relevance

This rule reduces:

- wasted quota/cost;
- Human rework;
- avoidable reruns;
- after-the-fact advice;
- loss of trust caused by correct but untimely guidance.

It is especially important when ChatGPT is acting as Program Controller and generating prompts that the Human is likely to execute immediately.

## Limits

The controller cannot predict every issue before action. This rule applies to material concerns already knowable from the available evidence at handoff time.

It does not justify delaying a bounded action for low-value perfectionism. Only concerns likely to change route, cost, safety, authority, or execution success should block or alter the handoff.
