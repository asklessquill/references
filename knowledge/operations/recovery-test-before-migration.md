---
observed_at: 2026-09-10
source_type: chat-derived
source: account and platform portability discussions
status: candidate
confidence: high
topic: recovery testing before migration
applicability: account changes, platform changes, model replacement, workspace migration
---

# Treat migration as a recovery test before treating it as a move

## Observation

A full migration mixes many variables at once: data transfer, new account behavior, missing memory, changed permissions, different model behavior, and new integrations. If the destination cannot reconstruct the current state, a full move can turn a recoverable gap into operational confusion.

## Interpretation

The safer pattern is to keep the old environment intact and use the new environment as a **recovery candidate** first.

```text
old environment = preserved reference
new environment = fresh recovery actor
        ↓
reconstruct from durable sources
        ↓
compare with accepted state
        ↓
close gaps
        ↓
only then migrate authority
```

## Decision relevance

This approach makes migration produce useful evidence:

- which knowledge was truly durable
- which assumptions existed only in chat or memory
- which integrations are account-bound
- whether the new actor understands current authority
- what bootstrap material is actually necessary

## Limits

Parallel environments can create their own divergence if both retain write authority. During recovery testing, mutation rights and authoritative outputs should be explicit.
