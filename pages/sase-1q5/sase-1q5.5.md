# Bead: sase-1q5.5 — Trim Agents-tab tick and capacity patch work

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.5` · **Size:** medium
**Created:** 2026-10-30 18:38:11 EDT · **Closed:** 2026-10-30 21:52:38 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

agents-tick-trims: stop capacity patches from rebuilding panel titles, skip unchanged capacity applies, and check a cheap revision key before fingerprinting clan members for runtime aggregation.

## Notes

[2026-10-31T01:38:06Z · sase-1q5.5--2] Benchmark evidence: Agents default next p50/p95 improved from 21.35/26.93 to 16.00/26.81 ms and prev from 24.01/34.25 to 19.97/26.09 ms. Named next moved from 23.90/30.48 to 20.53/37.30 ms and prev from 22.43/28.57 to 21.02/44.45 ms; p50 improved in all four cases, while named p95 increased. After benchmark: 8 failed, 11 passed in 614.51s. The clean-tree baseline had 8 failed, 11 passed in 592.78s. The same failing test categories recurred: archive warm-open budget; clan fold p95 (baseline level 3, after level 2); selected tribe fold level 1; Fleet hung_host, reconnect_churn, and event_burst; link-rail stall row; and Axe-tab assertion. PROPOSED FOLLOW-UP: Stabilize the remaining host-sensitive TUI performance benchmark failures — the same eight benchmark test categories fail on the clean tree and after this phase, with the clan fold crossing at different levels.

[2026-10-31T01:52:20Z · sase-1q5.5--2] Verification update: Fixed the capacity test double to include the new input key and fixed runtime fast-cache scope, stale-object validation, and seen-set parity. The 42-test focused rerun passes, including the five code-related failures from check ToolRun 4d1830b282ed5cfca9ba6c4a13d8fcad; the parallel prompt-bar failure also passed on serial rerun. just _lint-symvision passes. Final check ToolRun 094325f9eb25ee94a8c532799f4d8d38 exits 1 at lint (feature flags) before scoped tests because generated macro input schemas are stale; the failure requests tools/sync_macro_input_schemas --write. No macro input source or schema paths are changed by this phase, so this is a clean-base failure. PROPOSED FOLLOW-UP: Regenerate and review macro input schema artifacts so the clean-base feature-flags lint passes; the mismatch is outside the TUI phase.

[2026-10-31T01:52:38Z · sase-1q5.5--2] Implemented the Agents capacity/title and runtime aggregation trims with parity tests. The 42-test focused suite and Symvision pass. Recorded before/after benchmark results and the clean-base benchmark and feature-flag lint failures as proposed follow-ups; no epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1q5.2](sase-1q5.2.md) ✓ · ⧖ 2026-10-30
- **Depends on:** [sase-1q5.3](sase-1q5.3.md) ✓ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.5.md) | [sase-1q5.5](sase-1q5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b09d069`](https://github.com/sase-org/sase/commit/b09d06945d17ad00e49e8b513a983d6951a85c0d) | perf(ace): trim Agents tab tick work | [sase-1q5.5](sase-1q5.5.md) | 2026-10-30 21:57:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q5.5--2][1] | Need the phase scope, decisions, and prior work notes before completing verification | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.5.md

<!-- sase:referenced-by:end -->
