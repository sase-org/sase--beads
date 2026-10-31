# Bead: sase-1q5.6 — Move small synchronous work off the UI pump

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.6` · **Size:** small
**Created:** 2026-10-30 18:38:11 EDT · **Closed:** 2026-10-30 20:12:10 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

pump-probe-trims: use one persistent malloc_trim worker, move the tool-runs token probe off the countdown tick, and debounce the prompt subtitle restyle while keeping typing and the caret immediate.

## Notes

[2026-10-31T00:11:52Z · sase-1q5.6] PROPOSED FOLLOW-UP: Triage the 2026-10-30 full-lane check failures (ToolRun ca21f9a45f6c297a802e8f97a8f40524): zsh PTY timeout is already tracked by sase-13a, and test_start_monitor_serializes_concurrent_starts_in_one_lane matches sase-j7 note #50; test_real_ace_page_query_clear_retry_records_the_live_transition has no matching task bead. All three passed together under xdist on the clean base, so the failures appear load-sensitive; check reported 59,205 passed and 3 failed after escalating on core-identity-changed.

[2026-10-31T00:12:10Z · sase-1q5.6] Implemented the persistent trim worker, off-pump ToolRun token probe, and debounced prompt subtitle; 39 focused tests passed and git diff --check is clean. just check lint/validation passed; its full-lane test stage had 59,205 passed and 3 load-sensitive failures, all 3 passed together on the clean base; recorded the follow-up on this phase. epic-symbol check found none.

## Dependencies

- **Blocks:** [sase-1q5.7](sase-1q5.7.md) ◐ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.6/README.md) | [sase-1q5.6](sase-1q5.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`001351f`](https://github.com/sase-org/sase/commit/001351f5b921b165c52fb13fe2da8e0ea2d91a0a) | perf(tui): move small synchronous work off pump | [sase-1q5.6](sase-1q5.6.md) | 2026-10-30 20:13:22 EDT |
