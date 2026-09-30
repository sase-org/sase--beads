# Bead: sase-1d7.10 — Cached wait-status maps and change-only runtime patching

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.10` · **Size:** medium
**Created:** 2026-09-30 07:18:20 EDT · **Closed:** 2026-09-30 11:05:48 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

runtime-tick-caches: cache collect_agent_wait_status_maps per roster generation, patch runtime rows only when their rendered runtime text changes, and cache clan runtime aggregation so the 1 Hz tick stops freezing the loop.

## Notes

[2026-09-30T15:05:05Z · sase-1d7.10] PROPOSED FOLLOW-UP: full sase tool run check exceeds single-turn 10-min limit on this host (killed during sase-core crate compile); targeted gates pass (ruff/mypy/symvision/fmt/toobig, runtime/wait/roster/unread suites, idle tick bench) — rerun full check via monitor or CI

[2026-09-30T15:05:48Z · sase-1d7.10] runtime-tick-caches done: app-wide wait-maps cache per (roster,tribe,id,len) with tribe/wait bumps; per-clan aggregate wires cached (Rust only per tick); change-only suffix-only tick reusing left without cache invalidate (wait/tool via full patch). Verified: 6 new cache tests, 59 runtime + 61 roster/wait + 58 unread/core suites pass; idle tick p50 5.2ms/p95 6.2ms (was 73ms) under 16ms with 134 ticking rows; ruff/mypy/symvision/fmt/toobig clean; full check exceeds 10-min Rust build, recorded as follow-up

## Dependencies

- **Depends on:** [sase-1d7.3](sase-1d7.3.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.10/README.md) | [sase-1d7.10](sase-1d7.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`11ba54b`](https://github.com/sase-org/sase/commit/11ba54b3816412c082c2ca9ba93ad672247782a0) | feat(agents): cache wait-status maps and change-only runtime patching | [sase-1d7.10](sase-1d7.10.md) | 2026-09-30 11:08:32 EDT |
