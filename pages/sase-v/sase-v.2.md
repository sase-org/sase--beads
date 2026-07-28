# Bead: sase-v.2 — Phase 2 — Evaluator + agent-side helpers

[Bead Pages](../README.md) / [sase-v](README.md) / sase-v.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-v.2`
**Created:** 2026-04-26 07:31:00 UTC · **Closed:** 2026-04-26 07:58:12 UTC
**Plan:** [202604/agents\_tab\_query\_filters.md](https://github.com/sase-org/sase--plans/blob/main/202604/agents_tab_query_filters.md)

## Description

Semantics layer. Create src/sase/ace/agent_query/evaluator.py with evaluate_agent_query(expr, agent, *, now, content_cache) -> bool. Add helpers: agent_source(agent) in models/agent.py (axe vs manual), _NEEDS_INPUT_STATUSES frozenset in agent_groups.py, is_pinned(agent) colocated with DEFAULT_PINNED_TAG. Pure function — no I/O, no global state. Tests: per-property-key coverage, age comparator with frozen now, boolean composition, bare-word + property combinations. Out of scope: TUI integration, modal changes, help modal.

## Notes

COMMIT: 27f18d23

## Dependencies

- **Depends on:** [sase-v.1](sase-v.1.md) ✓
- **Blocks:** [sase-v.3](sase-v.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8ca4684`](https://github.com/sase-org/sase/commit/8ca46840d49ef809c216eae66ae5151d8fa4e0e6) | feat: add agent\_query evaluator + agent helpers — phase 2 of agents-tab structured query filters (sase-v.2) | [sase-v.2](sase-v.2.md) | 2026-04-26 07:58:15 |
