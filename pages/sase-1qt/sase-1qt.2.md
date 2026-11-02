# Bead: sase-1qt.2 — Fix the agents-sync bounded-drain publication flake (sase-xo)

[Bead Pages](../README.md) / [sase-1qt](README.md) / sase-1qt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.land.md) · **Assignee:** `sase-1qt.2` · **Size:** large
**Created:** 2026-11-01 18:08:20 EST · **Closed:** 2026-11-01 19:57:08 EST
**Plan:** [202611/task\_backlog\_epic\_5.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_5.md)

## Description

agents-sync-drain-flake: tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued still fails in loaded full lanes after the 1a69c8947d/4adee846d3 fix (recurrences 2026-10-27 and 2026-10-31; one report measured 15.63s after git index-lock backoff). Find what still consumes the wall-clock budget under load and fix it without raising the elapsed bound or dropping the queued-request assertion.

## Notes

[2026-11-01T23:16:06Z · sase-1qt.2] Planning investigation on clean sase 9066546900ccafffcd3846f1ff56b81580c1f515, athena, Python 3.14.7, opened sase-core e60f3e1658d34f1345bc4bef8bf112a396749c87. Both prior fixes are present. Original bounded-render node passed isolated (1.30s call). Deterministic fault injection created a fresh owner-free sidecar .git/index.lock immediately before the existing blocked renderer, using an in-memory pytest plugin and dataclasses.replace on PublicationTransactionHooks; no product/test files changed. Original assertion then failed at elapsed=15.6448s: render entered 0.155s after transaction start and unwound at 0.830s with alarm=True; locked drain duration=15.625s, cleanup=14.6253s, first alarm stage=hood_publish:foo. Git logged six backoffs (0.1..3.2s), then a 7.666s stale-age wait and lock removal. The one-shot alarm is spent before exception cleanup. agents_sync.git.run_git supplies neither a remaining deadline to run_with_git_lock_retry nor a reduced subprocess timeout. Core git_lock::maybe_backoff also ignores remaining deadline/budget fields (age-wait consults them). This proves a concrete post-alarm failure mode, not a spontaneous reproduction of the historical loaded lane. Preparing a medium tale for bounded cleanup, Rust deadline-policy enforcement, and integration regressions; work remains unimplemented pending the requested plan handoff.

[2026-11-02T00:07:15Z · sase-1qt.2] Implementation in progress (athena, .venv Python 3.14.7, sase a79207993c9, sase-core e60f3e1658 plus uncommitted fix). Rust git_lock::decision now enforces effective budget (min recovery, caller deadline) in maybe_backoff, decide_index_lock, retry_or_give_up, and aged-lock branch; added expired/shorter-than-backoff/aged-deadline Rust tests plus cleanup-budget constant (1s) with binding. Python adds 1s PublicationCleanupBudget, bounded SIGALRM alarm (preserves drain attribution), bounded git runner (caps subprocess + lock-retry remaining, never None on zero), eager-probe cap, and shared-deadline clean_publication_worktree. New regressions: blocked-render+young-index.lock stays under 5s (2.48s call, cleanup under 2s, attempts==1, lock released, later retry publishes), stalled 5s cleanup stays under 5s with timeout preserved, expired-budget executor test. Before: probe 15.6448s elapsed, cleanup 14.6253s. After: contention 2.48s, stalled 2.13s, original 1.28s. Parallel reps: 3x -n4 bounded-drain (9 passed) plus git_sync (33 passed). PROPOSED FOLLOW-UP: tests/agents_sync/test_commit_publication_drain_accounting.py 9 failures reproduce identically on clean base (scanner-timeout, caps-at-25, completion-gate, cleanup-after-success, mixed-hood, fully-blocked, unverified-sibling, fully-unverified, second-drain) - pre-existing, not caused here. Full sase tool run check still running (run a17ced1a91cff09ea4654b4a30fdf7e6); sase-core check and pin move still pending (host owns pin).

[2026-11-02T00:50:34Z · sase-1qt.2--1] PROPOSED FOLLOW-UP: tests/agents_sync/test_commit_publication_drain_accounting.py shows 9 failures (scanner-timeout, caps-at-25, completion-gate, cleanup-after-success, mixed-hood, fully-blocked, unverified-sibling, fully-unverified, second-drain) that reproduce identically on the clean base without this fix (verified during phase investigation on sase 9066546900); pre-existing, not caused by the bounded-cleanup change. PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget failed once under sase tool run check (run a17ced1a91cff09ea4654b4a30fdf7e6, verdict no_new_failures, 1 KNOWN witness 02ee4a669bcb10115e81429c94035534, no owner); unrelated to agents-sync drain work.

[2026-11-02T00:56:59Z · sase-1qt.2--2] TASK RESOLVED: sase-xo — bounded-drain cleanup fix verified on both sides. Before: deterministic fault-injection probe 15.6448s elapsed / 14.6253s cleanup (blocked render + owner-free sidecar .git/index.lock). After: bounded-drain module 9 passed in 16.36s (blocked-render+young-lock 2.41s, stalled-cleanup 2.08s, original 1.25s); sase_core git_lock lib tests 20 passed including 3 new budget tests. sase check run a17ced1a91cff09ea4654b4a30fdf7e6 settled no_new_failures with 1 KNOWN (TUI import-budget witness 02ee4a669bcb10115e81429c94035534, recorded as PROPOSED FOLLOW-UP). sase-core check run dabb65c5c9d19f8f83bc5d423107cb28 verdict pass. sase bead epic-symbols sase-1qt.2 reports no entries. Drain-accounting 9 failures are pre-existing on clean base, recorded as PROPOSED FOLLOW-UP, not blocking.

[2026-11-02T00:57:08Z · sase-1qt.2--2] Bounded-drain cleanup verified: sase run a17ced1a91cff09ea4654b4a30fdf7e6 no_new_failures (1 KNOWN TUI import-budget), sase-core run dabb65c5c9d19f8f83bc5d423107cb28 pass; bounded-drain 9 passed (2.41s/2.08s/1.25s vs pre-fix 15.6448s/14.6253s); git_lock lib 20 passed; epic-symbols clean. Do not close sase-xo or sase-1qt.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qt.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.2.md) | [sase-1qt.2](sase-1qt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f061f5f`](https://github.com/sase-org/sase-core/commit/f061f5f623c34381105fccf529bd56d9c77ef013) | fix(git-lock): enforce effective budget in backoff and aged-lock decisions | [sase-1qt.2](sase-1qt.2.md) | 2026-11-01 19:58:03 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qt.2--2][1] | Verify bounded cleanup fix before close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.2.md

<!-- sase:referenced-by:end -->
