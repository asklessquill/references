---
observed_at: 2026-09-10
source_type: chat-derived
source: staged implementation and acceptance discussions
status: candidate
confidence: high
topic: lab versus production authority
applicability: experiments, agentic development, promotion workflows
---

# Passing a lab review is not production authority

## Observation
A technically correct candidate can be safe to study without being authorized for production use.

## Interpretation
Semantic correctness, test success, and independent review are distinct from promotion authority.

## Decision relevance
Record separately:
- implementation candidate status
- verification status
- independent review verdict
- production promotion authority
- deployment or activation status

## Limits
Some small systems intentionally collapse these gates. If so, the risk acceptance should be explicit.
