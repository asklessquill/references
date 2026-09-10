# Knowledge Map

`knowledge/` contains reusable reference knowledge. It is **not canonical authority**.

## Categories

- `architecture/` — boundaries, roles, authority, protocols, recovery semantics, projections, agent structure
- `ai-routing/` — model/surface selection, quotas, experience, failure lessons, context, routing evidence
- `economics/` — subscription and capacity economics, interruption cost, optionality, self-funding loops
- `insight/` — evidence quality, freshness, unknowns, rapid change packets, research horizons
- `operations/` — closeout, review, activation, retries, observability, portability, current state, workspace hygiene
- `platform/` — connectors, capability discovery, shared knowledge, workspace adoption, build/buy/borrow/reuse

## Reading rule

Each entry should be read with its YAML metadata. `candidate` means useful enough to retain, not established truth. `validated` means the principle has stronger support from repeated observation or established practice, but still does not override project-specific authority.

## Promotion rule

Reference knowledge may inform a decision. It must not silently become project canon, production configuration, agent authority, or organizational knowledge. Promotion requires an explicit decision in the destination system.

## Correction rule

Prefer superseding an entry over silently rewriting semantic history. Preserve why a belief changed when the change could affect later decisions.
