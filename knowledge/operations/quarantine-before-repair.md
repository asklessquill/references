---
observed_at: 2026-09-10
source_type: chat-derived
source: contaminated-context recovery discussions
status: candidate
confidence: high
topic: quarantine before repair
applicability: repository recovery, AI memory recovery, compromised assumptions, incident response
---

# Quarantine uncertain state before trying to repair it

## Observation

When contamination is suspected, immediately continuing normal development can spread uncertainty into new commits, documents, memories, or generated explanations.

## Interpretation

The first recovery move should often be containment rather than correction.

A useful sequence is:

```text
preserve suspect state
→ remove or narrow write authority
→ identify trusted evidence
→ reconstruct independently
→ compare
→ accept only verified state
→ resume mutation
```

This keeps the original evidence available while preventing it from silently becoming new authority.

## Decision relevance

Apply quarantine when there is uncertainty about:

- canonical versus local state
- AI memory or conversational assumptions
- provenance of generated documents
- whether a branch contains accepted or speculative work
- whether a previous actor exceeded scope

A quarantined source can remain readable without remaining authoritative.

## Limits

Quarantine is not proof of corruption and should not become permanent paralysis. The goal is to create a bounded path back to trusted operation.
