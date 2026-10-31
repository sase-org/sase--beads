# Bead: sase-1qh.1 — Planner prompt-archive rows use linked (page-only) scope

[Bead Pages](../README.md) / [sase-1qh](README.md) / sase-1qh.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5l.linker.w0.md) · **Assignee:** `sase-1qh.1` · **Size:** medium
**Created:** 2026-10-31 12:01:49 EDT
**Plan:** [202610/agent\_publication\_notifications.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_publication_notifications.md)

## Description

planner-scope: planner approvals enqueue their prompt-archive row with linked scope, and enqueue merges keep revision scope when either side has it, so the revision gate stops refusing rows for commits the planner never made.

## Notes

[2026-10-31T16:20:25Z · sase-1qh.1] PROPOSED FOLLOW-UP: add an explicit prompt fulfillment scope in sase-core — needs a scope in complete.rs and stale.rs::normalize_scope, an outbox schema bump with migration, the binding, and a sase-core-revision.txt pin; one row with an unknown scope makes the whole outbox unreadable to older readers

## Dependencies

- **Blocks:** [sase-1qh.2](sase-1qh.2.md) ◐ · ⧖ 2026-10-31
- **Blocks:** [sase-1qh.4](sase-1qh.4.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qh.1/README.md) | [sase-1qh.1](sase-1qh.1.md) | 0 |
