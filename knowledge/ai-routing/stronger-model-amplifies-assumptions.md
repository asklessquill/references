---
observed_at: 2026-09-10
source_type: chat-derived
source: repeated model-routing and recovery discussions
status: candidate
confidence: high
topic: stronger models and premise quality
applicability: model routing, architecture review, contaminated-context recovery
---

# A stronger model can amplify a wrong premise

## Observation

Increasing model capability does not automatically reduce system risk. If the model is given an incorrect authority model, stale context, contaminated memory, or a false canonical assumption, stronger reasoning and higher execution capacity can make the resulting work more coherent, faster, and harder to detect.

## Interpretation

Model quality and premise quality are multiplicative rather than interchangeable.

A useful mental model is:

```text
outcome quality ≈ reasoning quality × premise quality × evidence quality × execution discipline
```

When premise quality is uncertain, the first routing decision should often be to reduce authority, inspect provenance, or reconstruct context before increasing model power.

## Decision relevance

Before routing a task to a stronger or more expensive model, ask:

- Is the target state trustworthy?
- Is the source of truth explicit?
- Are assumptions distinguishable from evidence?
- Could a stronger model merely accelerate the wrong interpretation?
- Should the task be review/recovery instead of implementation?

## Limits

This does not imply that weaker models are safer. Weak models can also make incorrect changes. The point is that greater capability does not compensate for bad authority or provenance.
