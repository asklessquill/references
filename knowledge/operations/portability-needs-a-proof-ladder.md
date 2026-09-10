---
observed_at: 2026-09-10
source_type: chat-derived
source: account and environment portability discussions
status: candidate
confidence: high
topic: portability proof ladder
applicability: AI systems, disaster recovery, developer environments
---

# Portability should be proven in progressively harder environments

## Observation

Restoring repository history offline is useful but does not prove that a complete system can recover on a new device, identity, AI account, or live data environment.

## Interpretation

Portability is not binary. It has layers of proof.

## Decision relevance

A practical ladder is:

1. repository/history reconstruction
2. offline deterministic tests
3. fresh process
4. fresh AI context
5. fresh account or identity
6. different device
7. real data and external capabilities

Record the highest proven layer and the next unproven one.

## Limits

The exact ladder should match the system's dependencies and threat model.
