# Bead: sase-14l.2 — Read acknowledgment dismisses the settlement row

[Bead Pages](../README.md) / [sase-14l](README.md) / sase-14l.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.17](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.17.md) · **Assignee:** `sase-14l.2` · **Size:** medium
**Created:** 2026-09-20 16:56:56 EDT · **Closed:** 2026-09-20 18:40:49 EDT
**Plan:** [202609/epic\_launch\_read\_dismiss.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_launch_read_dismiss.md)

## Description

host-ack: ratchet the core revision pin, widen the TUI's cached-snapshot predicate so acknowledged settlement rows leave the cache and the indicator with the completion row, and document the widened contract.

## Notes

[2026-09-20T22:40:49Z · sase-14l.2] host-ack done: pin ratcheted to 1655a12 (core-match); combined row predicate dismisses exact-key epic-launch/monitor-settlement rows from cache with the completion row; row identity confirmed vs live agent list; 46 focused tests pass; ruff/mypy clean; symvision clear for touched symbols (26 pre-existing violations in untouched sdd/service/completion/models files remain, identical to pristine-tree baseline); Justfile epic-symbol keyed to open sase-14l.3 for the settlement predicate

## Dependencies

- **Depends on:** [sase-14l.1](sase-14l.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14l.3](sase-14l.3.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-14l.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-14l.2/README.md) | [sase-14l.2](sase-14l.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`64b2463`](https://github.com/sase-org/sase/commit/64b246312a0fd6ee669577e5be8d45f7564c6ea9) | feat(notify): dismiss row-owned settlement rows on agent read ack | [sase-14l.2](sase-14l.2.md) | 2026-09-20 18:43:05 EDT |
