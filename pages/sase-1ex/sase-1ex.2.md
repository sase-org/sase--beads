# Bead: sase-1ex.2 — App-owned launchable-MRU snapshot for project cycling

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.2` · **Size:** medium
**Created:** 2026-10-02 14:53:45 EDT · **Closed:** 2026-10-02 19:37:20 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

mru-snapshot: add an immutable launchable-MRU snapshot owned by `AceApp`. A single-flight worker builds it, and peek-token ticks and launch/set-current triggers keep it fresh. `ctrl+n/p` read it only, pin it per prompt session, and show a hint instead of editing when it is cold.

## Notes

[2026-10-02T23:37:04Z · sase-1ex.2--1] PROPOSED FOLLOW-UP: joined check f5a02662134a9f53de0067538eb6ba90 flagged 3 load-flaky tests (test_demand_runs peak_tree_rss, deck spread pilot timeout, launch_context rebroadcast identity) that pass in isolation on both base and patched trees; consider KNOWN witnesses or load-hardening

[2026-10-02T23:37:20Z · sase-1ex.2--1] mru-snapshot done: LaunchableMruSnapshot model + AceApp mixin (startup warm, 2s tick), snapshot-serving ctrl+n/p with ring pinning + cold hint, launch/set-current triggers. Verified: 12 new test_launchable_mru pass; AST call_from_thread guard + all 4 prompt-key perf smoke pass after fixing 2 real regressions from this phase (direct publish after to_thread; smoke test seeds ready snapshot); 3 unrelated joined-check failures pass in isolation on base and patched trees (load flakes, filed as follow-up); ruff/fmt/mypy clean; epic-symbols empty.

## Dependencies

- **Depends on:** [sase-1ex.1](sase-1ex.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.3](sase-1ex.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.4](sase-1ex.4.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.7](sase-1ex.7.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.2.md) | [sase-1ex.2](sase-1ex.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8138678`](https://github.com/sase-org/sase/commit/813867849ce4ff10ae8d1ee9d146367f2e95d475) | feat(ace-tui): app-owned launchable-MRU snapshot for project cycling | [sase-1ex.2](sase-1ex.2.md) | 2026-10-02 19:38:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.2--1][1] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.2.md

<!-- sase:referenced-by:end -->
