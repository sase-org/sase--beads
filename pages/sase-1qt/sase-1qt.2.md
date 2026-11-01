# Bead: sase-1qt.2 — Fix the agents-sync bounded-drain publication flake (sase-xo)

[Bead Pages](../README.md) / [sase-1qt](README.md) / sase-1qt.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.land.md) · **Assignee:** `sase-1qt.2` · **Size:** large
**Created:** 2026-11-01 18:08:20 EST
**Plan:** [202611/task\_backlog\_epic\_5.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_5.md)

## Description

agents-sync-drain-flake: tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued still fails in loaded full lanes after the 1a69c8947d/4adee846d3 fix (recurrences 2026-10-27 and 2026-10-31; one report measured 15.63s after git index-lock backoff). Find what still consumes the wall-clock budget under load and fix it without raising the elapsed bound or dropping the queued-request assertion.

## Notes

[2026-11-01T23:16:06Z · sase-1qt.2] Planning investigation on clean sase 9066546900ccafffcd3846f1ff56b81580c1f515, athena, Python 3.14.7, opened sase-core e60f3e1658d34f1345bc4bef8bf112a396749c87. Both prior fixes are present. Original bounded-render node passed isolated (1.30s call). Deterministic fault injection created a fresh owner-free sidecar .git/index.lock immediately before the existing blocked renderer, using an in-memory pytest plugin and dataclasses.replace on PublicationTransactionHooks; no product/test files changed. Original assertion then failed at elapsed=15.6448s: render entered 0.155s after transaction start and unwound at 0.830s with alarm=True; locked drain duration=15.625s, cleanup=14.6253s, first alarm stage=hood_publish:foo. Git logged six backoffs (0.1..3.2s), then a 7.666s stale-age wait and lock removal. The one-shot alarm is spent before exception cleanup. agents_sync.git.run_git supplies neither a remaining deadline to run_with_git_lock_retry nor a reduced subprocess timeout. Core git_lock::maybe_backoff also ignores remaining deadline/budget fields (age-wait consults them). This proves a concrete post-alarm failure mode, not a spontaneous reproduction of the historical loaded lane. Preparing a medium tale for bounded cleanup, Rust deadline-policy enforcement, and integration regressions; work remains unimplemented pending the requested plan handoff.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qt.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.2.md) | [sase-1qt.2](sase-1qt.2.md) | 0 |
