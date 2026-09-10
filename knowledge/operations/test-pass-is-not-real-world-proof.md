---
observed_at: 2026-09-10
source_type: chat-derived
source: lab, recovery, and activation discussions
status: validated
confidence: high
topic: levels of proof
applicability: software verification, agent systems, deployment readiness
---

# Passing tests is not the same as proving real-world operation

## Observation

A system can pass deterministic tests, independent review, offline recovery checks, and fresh-process validation while still lacking evidence that it works on a different machine, account, live dataset, or external service.

## Interpretation

Verification evidence belongs to different layers. Conflating them overstates readiness.

## Decision relevance

Label evidence separately as implementation test, semantic acceptance, recovery simulation, environment validation, and real-world activation. State explicitly which layer remains unproven.

## Limits

Not every project needs every proof layer. The required level depends on deployment consequences.
