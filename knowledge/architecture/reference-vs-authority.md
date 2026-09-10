---
observed_at: 2026-09-10
source_type: chat-derived
source: architecture and recovery discussions
status: candidate
confidence: high
topic: reference knowledge versus authority
applicability: multi-agent systems, AI-assisted development, repository governance
---

# Reference knowledge is not authority

## Observation

AI-assisted projects become fragile when conversational context, remembered assumptions, repository state, and human decisions are allowed to silently substitute for one another.

A useful separation is:

- **authority** decides what is allowed or canonical;
- **evidence** supports or challenges a decision;
- **reference knowledge** preserves reusable interpretation;
- **runtime state** says what currently exists or happened.

## Interpretation

A knowledge repository is most useful when it helps a future Actor reason without granting that repository permission to redefine the system.

This also reduces the risk of a semantic fork: two Actors may read the same historical material but infer different current authority unless canonical state and reference material are explicitly separated.

## Decision relevance

Use this distinction when designing:

- AI handoffs
- fresh-agent recovery
- multi-repository governance
- architecture reviews
- durable project memory

## Limits

This is an architectural principle, not proof that a particular authority model is correct. Concrete authority must still be defined by the system or its Human owner.
