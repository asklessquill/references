# Reference Entry Schema

Use this lightweight header for durable knowledge entries.

```yaml
observed_at: YYYY-MM-DD
source_type: chat-derived | official | empirical | external-report | experiment
source: free-text provenance
status: raw | candidate | validated | superseded | rejected
confidence: low | medium | high
topic: short topic name
applicability: where this knowledge is useful
```

## Body guidance

Prefer four sections:

### Observation
What was observed or established.

### Interpretation
What the observation may mean. Keep inference separate from fact.

### Decision relevance
What kinds of decisions this could change.

### Limits
What this entry does **not** prove, where it may be stale, and what should be rechecked.

## Update rule

Do not silently rewrite history when knowledge changes. Prefer adding a newer entry and marking the older one `superseded`, with a pointer to the replacement.
