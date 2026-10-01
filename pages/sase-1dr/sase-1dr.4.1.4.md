# Bead: sase-1dr.4.1.4 — Snapshot cache, upstream marker, and query bindings

[Bead Pages](../README.md) / [sase-1dr.4.1](sase-1dr.4.1.md) / sase-1dr.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) · **Assignee:** `sase-1dr.4.1.4` · **Size:** medium
**Created:** 2026-09-30 20:38:57 EDT · **Closed:** 2026-09-30 23:36:12 EDT
**Plan:** [202609/memory\_history\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history_core.md)

## Description

cache-queries: persist the per-scope snapshot, report how far origin is ahead, and expose sync, subjects, resolve, timeline, version, compare, and feed through GIL-releasing memory_history_ bindings.

## Notes

[2026-10-01T03:35:30Z · sase-1dr.4.1.4] PROPOSED FOLLOW-UP: `sase tool run check` in sase-core fails on 9 pre-existing clippy lints (nonminimal_bool, manual_range_contains, collasible_if, etc.) in agent_runtime.rs, agent_scan/index/maintenance.rs, finalizer/run_view/decode.rs, fleet_owner_facts.rs, provider_usage/mod.rs, tool_run/store/receipt.rs, tool_run/store/triage.rs — all files untouched by cache-queries; reproducible on clean base tree by construction

[2026-10-01T03:36:12Z · sase-1dr.4.1.4] cache-queries done in sase-core: cache.rs (snapshot persist/load, key, memo, sync fresh/folded/rebuilt), upstream.rs (ahead marker, never fetches), query.rs (sync/subjects/resolve/timeline/version/compare/feed), 8 GIL-releasing memory_history_ bindings registered; verified: 36 memory_history + 4294 sase_core lib + 259 sase_core_py tests pass, fmt-check/features/modules green; tool-run check blocked only by 9 pre-existing clippy lints in untouched files (recorded as PROPOSED FOLLOW-UP); epic-symbols clean

## Dependencies

- **Depends on:** [sase-1dr.4.1.3](sase-1dr.4.1.3.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.4.1.4/README.md) | [sase-1dr.4.1.4](sase-1dr.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@11f29c3`](https://github.com/sase-org/sase-core/commit/11f29c3385acfd4d2e2f165192b796b8b954d731) | feat(memory-history): add cache-backed query layer with python bindings | [sase-1dr.4.1.4](sase-1dr.4.1.4.md) | 2026-09-30 23:38:21 EDT |
