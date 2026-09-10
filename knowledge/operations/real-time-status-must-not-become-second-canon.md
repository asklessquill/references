---
observed_at: 2026-09-10
source_type: chat-derived
source: real-time project dashboard discussions
status: candidate
confidence: high
topic: real-time status projection
applicability: dashboards, observatories, project control
---

# Real-time status should be fast without becoming a second canon

## Observation

Teams want dashboards and current-state pages to update quickly, but manually maintained summaries can drift from accepted commits and evidence.

## Interpretation

Real-time visibility and canonical authority should be separated. The dashboard should project the latest trustworthy state and show uncertainty when synchronization lags.

## Decision relevance

Design status views with source links, update timestamps, confidence or acceptance state, and correction paths. Prefer generation from durable evidence where practical.

## Limits

Some operational state exists only at runtime and cannot be reconstructed from Git alone; its source should still be explicit.
