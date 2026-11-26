# Bead: sase-1vb.4 — Root-cause the flakes that turned recent master SHAs red

[Bead Pages](../README.md) / [sase-1vb](README.md) / sase-1vb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ge](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ge.md) · **Assignee:** `sase-1vb.4` · **Size:** medium
**Created:** 2026-11-26 06:30:38 EST · **Closed:** 2026-11-26 08:23:35 EST
**Plan:** [202611/green\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202611/green_github_actions.md)

## Description

master-gate-flakes: reproduce and fix the four intermittent Master Gate failures at their source, or record evidence-backed follow-ups.

## Notes

[2026-11-26T13:22:49Z · sase-1vb.4] PROPOSED FOLLOW-UP: Textual active_worker contextvar pins finished thread workers (test_refresh_warmup_gc leftover FinalizerInventoryWorkerResult). Mechanism proven: textual Worker._run does active_worker.set(self) with the token discarded; for thread workers the set executes in the pooled asyncio_N executor thread, and CPython 3.14 Thread._context retains active_worker -> finished Worker -> _result indefinitely; a later Textual thread worker (name=body, spawned by ticks) landing on the same pooled thread overwrites the entry mid-window and the freed cycle is counted by SAVEALL. Evidence: instrumented failing run showed exactly 1 schedule + 1 apply both before drain-return, yet the wrapper was counted; gc.get_referrers chain ended at thread asyncio_1 _context var active_worker. Fix belongs upstream (token + reset in Worker._run/_run_threaded). Possibly shared root with other SAVEALL GC flakes. Candidate owner: sase-1v2 (READY, same test).

[2026-11-26T13:23:00Z · sase-1vb.4] PROPOSED FOLLOW-UP: Full CI PR #319 leftovers share no root cause with the four Master Gate targets and were left untouched per the phase: tests/tool/test_admission_processes.py::test_nested_agent_check_keeps_parent_and_never_queues (tool admission subprocess/timeout domain) has no flake owner; tests/test_config_cache_token.py::test_getter_never_starts_thread_after_warmup (thread-start counting) is adjacent to sase-t6 (live config-token refresh threads) but a different test with no proven shared mechanism — possible lead is executor pool-thread growth under load, unconfirmed.

[2026-11-26T13:23:10Z · sase-1vb.4] Phase evidence: archive focus flake reproduced locally with the exact CI signature (2/10 iters, -n 8 + CPU burners: assert None is ArchiveList at line 160) and fixed; link-follow planner flake did not reproduce locally (~40 loaded runs green) but the CI signature matches exactly one code path (same-pane fast-path select on unsettled rows, no reveal rewrite) and the dispatch precondition was hardened per the files own worker-settle idiom; scoped-prep wall-clock inverted sample replaced by deterministic copy counts (scoped 60-67 new objects vs full 1054 on n=1054, bounds <=80 and 4x); warmup drain now waits for prompt-inventory delivery + applied state instead of worker completion alone. Verification: sase tool run check 3b5be4eaa5dbb32b73a4b5e1df83c406 — every lint gate green (ruff, mypy, symvision, test-waits, etc.) and the scoped test lane green; the run then escalated to the full suite on the environmental core-identity-changed rule (check reinstalled sase_core_rs from a different cached wheel; this phase touches no core identity), which cannot finish in one turn and is covered by ci-proof Full CI on the tip.

[2026-11-26T13:23:35Z · sase-1vb.4] Fixed 3 of 4 Master Gate flakes at source with stress evidence; 4th (warmup GC) hardened in-repo with the remaining Textual-upstream pin mechanism recorded as follow-up for sase-1v2. Lint gates all green and scoped lane green in check run 3b5be4eaa5dbb32b73a4b5e1df83c406 (full-suite escalation environmental, covered by ci-proof). Extras triaged as follow-ups (no shared root).

## Dependencies

- **Blocks:** [sase-1vb.5](sase-1vb.5.md) ✓ · ⧖ 2026-11-26
- **Blocks:** [sase-1vb.6](sase-1vb.6.md) ◐ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.4/README.md) | [sase-1vb.4](sase-1vb.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5db9dbf`](https://github.com/sase-org/sase/commit/5db9dbf33b5c824174942a445fa8fda8a2e3897e) | fix(tui): root-cause Master Gate flakes at their source | [sase-1vb.4](sase-1vb.4.md) | 2026-11-26 08:25:10 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vb.4][1] | check prior notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.4/README.md

<!-- sase:referenced-by:end -->
