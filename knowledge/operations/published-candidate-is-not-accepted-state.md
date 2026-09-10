---
observed_at: 2026-09-10
source_type: chat-derived
source: candidate branch and acceptance review discussions
status: validated
confidence: high
topic: candidate versus accepted state
applicability: Git workflows, autonomous development, release governance
---

# A published candidate is not automatically accepted state

## Observation

A branch can be pushed, tests can pass, and its remote SHA can be verified while the work still remains only a candidate awaiting closeout or independent acceptance.

## Interpretation

Publication, verification, acceptance, and promotion are distinct transitions.

## Decision relevance

Represent states explicitly: local work -> published candidate -> verified candidate -> independently accepted -> promoted canonical state. Do not infer later states from earlier evidence.

## Limits

Small projects may combine transitions operationally, but the semantics remain useful when independent review or rollback matters.
