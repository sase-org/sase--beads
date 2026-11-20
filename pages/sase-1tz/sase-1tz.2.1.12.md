# Bead: sase-1tz.2.1.12 — Cache compiled query profiles and cut per-second clan runtime work

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.12` · **Size:** small
**Created:** 2026-11-19 11:13:29 EST · **Closed:** 2026-11-19 12:45:12 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

ui_cpu_caches: memoize compiled built-in pane query profiles and stop re-serializing every clan member on each one-second runtime tick. Confirm the removed agent_share_fingerprint has no live caller.

## Notes

[2026-11-19T17:44:53Z · sase-1tz.2.1.12] ui_cpu_caches landed: memoized compiled_profile_for_builtin_pane keyed by pane id (src/sase/ace/query_profile/pane_registry.py + package export) and added per-member asdict cache in aggregate_clan_runtime facade keyed by wire identity (src/sase/core/agent_runtime_facade.py). Bench: profile compile 177us/call -> 0.1-0.2us memoized; facade 12-member steady tick 115us -> ~67-73us (Rust aggregation itself still runs per tick for the now-dependent suffix). agent_share_fingerprint: zero live callers in src/tests/docs; audit stall samples (Nov 16-17, _agent_graph.py:288,306 + compiler.py:120 json.dumps line) predate removal commit d152f200b2 (Nov 18). Tests: new tests/test_query_profile_pane_registry.py (6) + tests/test_core_agent_runtime_cache.py (3); existing runtime_tick_caches + query-profile suites pass. just check: all lint gates pass incl symvision; scoped lane 62125 passed with 3 unrelated load flakes (bare_git_init lock-retry, artifact volume-budget, pager trail) that import none of the touched modules and all pass in isolation.

[2026-11-19T17:45:12Z · sase-1tz.2.1.12] Verified: pane-profile memoization + facade wire cache landed with focused tests green; just check all lint gates pass, scoped lane 62125 passed (3 unrelated load flakes pass in isolation); agent_share_fingerprint has no live callers and audit samples predate its removal.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.12/README.md) | [sase-1tz.2.1.12](sase-1tz.2.1.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ffb7d33`](https://github.com/sase-org/sase/commit/ffb7d33edb8ae72b9bc2f2ee2af9d2f426174fe6) | perf(ace): memoize built-in query profiles and clan runtime wire payloads | [sase-1tz.2.1.12](sase-1tz.2.1.12.md) | 2026-11-19 12:47:49 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.12][1] | check notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.12/README.md

<!-- sase:referenced-by:end -->
