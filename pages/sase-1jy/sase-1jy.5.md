# Bead: sase-1jy.5 — Scope the runner's startup and 60 s fallback resolution

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.5` · **Size:** small
**Created:** 2026-10-11 11:18:36 EDT · **Closed:** 2026-10-11 16:58:04 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

scoped-runner-fallback: make _resolve_marker_release build scoped project indexes for scopable markers, keeping the full project build for every other shape.

## Notes

[2026-10-11T20:57:41Z · sase-1jy.5] MEASURE: read-only gh_sase-org__sase named waiter 20260715092915 waiting_for=["sase-63.3"]: full build_wait_dependency_index 3.75s (16097 artifacts); scoped select+add_many 1.637s (2 artifacts, add_many 7ms); resolve_wait_release decisions matched (blocked on sase-63.3). Remaining cost is agent_meta.json reads, which sase-1jy.6 cache will drop.

[2026-10-11T20:58:04Z · sase-1jy.5] Runner startup/60s fallback builds scoped project indexes for named and bead-only waits; unscopable shapes including identity deps still call build_wait_dependency_index. Parity tests (handoff follow-up, newer-failed-run) and spy tests pass. sase tool run check 28fd5ce8a2190aa8ba0413dcab909545 succeeded. Host read-only: gh_sase-org__sase waiter 20260715092915 full 3.75s/16097 rows vs scoped 1.637s/2 rows, decisions matched. No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-1jy.3](sase-1jy.3.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jy.6](sase-1jy.6.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jy.5/README.md) | [sase-1jy.5](sase-1jy.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`814dbca`](https://github.com/sase-org/sase/commit/814dbcafb4eb6e3e465d00fb5bc1dd260cbbbe0d) | fix(axe): scope runner wait indexes to named-wait keys | [sase-1jy.5](sase-1jy.5.md) | 2026-10-11 16:59:36 EDT |
