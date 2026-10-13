# Bead: sase-1kj.2 — Coalesce deferred ToolRun glance refreshes

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.2` · **Size:** small
**Created:** 2026-10-13 11:47:18 EDT · **Closed:** 2026-10-13 12:45:15 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

toolrun-glance-coalesce: keep the ToolRun refresh marked scheduled while it waits behind an Agents load, so only one deferred chain and one glance load can exist.

## Notes

[2026-10-13T16:44:34Z · sase-1kj.2] PROPOSED FOLLOW-UP: TUI import budget 3518 vs <3513 on clean base (this phase +0 production imports) — tracked by sase-1ic; KNOWN witness 0409af70242a4314f4aa519ba6c48ebb

[2026-10-13T16:44:46Z · sase-1kj.2] PROPOSED FOLLOW-UP: tests/tool/test_executor.py::test_nested_run_has_parent_and_no_duplicate_logs StopIteration in scoped check, passed isolation on dirty tree and clean base — tracked by flake sase-1jl

[2026-10-13T16:44:51Z · sase-1kj.2] PROPOSED FOLLOW-UP: tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued elapsed 31.15s vs <5.0 in scoped check at load1=16.7; passed isolation (~0.5s) on dirty tree and clean base — no existing bead

[2026-10-13T16:45:15Z · sase-1kj.2] Coalesced ToolRun glance deferral: scheduled stays true while _agents_loading, spawn/timer failures reset it, running entry sets pending. Isolation: 4 extra schedules during load -> 1 spawn, 1 50ms timer, scheduled true; after load ends, 1 load_glance_blocking. Before: each 2s drift probe armed a new chain (scheduled cleared). Host loadavg at check 16.73/14.11/14.24 (64 CPUs). just check 344ff26041c317293b9934407e16a7e8: 2 NEW flakes (sase-1jl nested-run StopIteration; bounded-drain 31s vs <5s) plus KNOWN import budget 3518<3513 (sase-1ic); all reproduced as pre-existing/isolation-green. Kept ToolRunGlance join_kind/join_id intact.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.2/README.md) | [sase-1kj.2](sase-1kj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`82aa8a7`](https://github.com/sase-org/sase/commit/82aa8a7a88b10c0d3aba515a834e0503cc99771c) | fix(tui): coalesce deferred ToolRun glance refreshes behind Agents load | [sase-1kj.2](sase-1kj.2.md) | 2026-10-13 12:47:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kj.2/README.md

<!-- sase:referenced-by:end -->
