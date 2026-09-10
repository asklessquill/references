---
observed_at: 2026-09-10
source_type: chat-derived
source: model handoff and review discussions
status: validated
confidence: high
topic: evidence-based handoff
applicability: multi-agent workflows, reviews, recovery, model replacement
---

# Handoffs should point to fixed evidence, not mutable local state

## Observation

A fresh reviewer or replacement actor can reach a different conclusion if it inspects a branch, folder, or local workspace that changed after the intended review target was prepared.

## Interpretation

The handoff contract should identify immutable or auditable evidence: commit SHA, branch lineage, acceptance receipt, test evidence, and explicit scope.

## Decision relevance

For independent review or recovery, prefer:

- fixed candidate SHA
- explicit authority and prohibitions
- named evidence files
- clear stop condition
- no dependence on conversational memory

## Limits

A fixed SHA proves immutability of the reviewed content, not correctness of the content itself.
