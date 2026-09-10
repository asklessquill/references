---
observed_at: 2026-09-10
source_type: chat-derived
source: fresh-account and incomplete-canon discussions
status: candidate
confidence: high
topic: semantic fork risk
applicability: multi-agent systems, migrations, handoffs, canonical-state design
---

# Incomplete canon creates semantic forks before code forks

## Observation

Two capable actors can read the same repository and still continue in different directions when key decisions remain only in chat history, local state, memory, or unstated Human intent.

## Interpretation

The dangerous fork often happens before any Git branch diverges. It begins when actors reconstruct different meanings of:

- what is authoritative
- what is complete
- what is still provisional
- which actions are permitted
- what the next phase actually means

This is a **semantic fork**. Code divergence is only a later symptom.

## Decision relevance

Before handing work to a fresh actor or account, prefer a checkpoint containing:

- accepted/frozen candidate identifier
- current state
- acceptance or review evidence
- explicit unresolved items
- authority boundaries
- forbidden next steps
- a clear STOP or continuation condition

If this information is absent, the receiving actor should recover and classify state before designing or implementing.

## Limits

A complete checkpoint reduces but does not eliminate interpretation differences. Independent review is still useful for high-impact transitions.
