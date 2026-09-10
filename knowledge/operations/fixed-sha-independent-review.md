---
observed_at: 2026-09-10
source_type: chat-derived
source: independent acceptance review workflows
status: candidate
confidence: high
topic: fixed-sha independent review
applicability: software review, agentic coding, acceptance gates
---

# Review a frozen candidate, not a moving workspace

## Observation
Independent review loses meaning when the reviewer evaluates mutable local state or continues changing the candidate while reviewing it.

## Interpretation
A review target should be frozen by immutable identifier such as a commit SHA, and the reviewer should be operationally separate from the builder role.

## Decision relevance
A strong acceptance review should specify:
- exact repository and candidate SHA
- allowed review scope
- prohibited mutations
- authority of the reviewer
- acceptance criteria
- explicit STOP after verdict

## Limits
A fixed SHA proves what was reviewed, not that later branches or deployments match it.
