# Bead: sase-wn.5 — Per-surface change tokens for ace auto-refresh

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.5` · **Size:** large
**Created:** 2026-09-04 12:11:07 EDT · **Closed:** 2026-09-04 16:07:21 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-refresh-tokens: replace ace's unconditional full reconcile every refresh_interval with cheap per-surface change tokens (agents, axe, notifications, patches, procs) that work without an fs watcher, restoring the dirty-gate design on macOS and under Linux churn, with a periodic full-sanity reconcile and a sunset flag keeping the old unconditional path reachable.

## Notes

[2026-09-04T20:06:24Z · sase-wn.5--1] PROPOSED FOLLOW-UP: split src/sase/ace/tui/actions/link_follow.py — pre-existing toobig (1066 lines on master, limit 1000). This phase did not touch that file; just check remains blocked by it.

PROPOSED FOLLOW-UP: capture a 30-minute watcherless ACE idle CPU soak on Linux and macOS (idle CPU, stall-watchdog records, RSS trajectory). Flag sase-wr remove-when already requires this soak; this turn did not capture one.

[2026-09-04T20:07:21Z · sase-wn.5--1] Verified ace-refresh-tokens on sase-wn.5. Sunset flag ace_refresh_tokens (flag bead sase-wr) gates per-surface stat-only tokens for ACE auto-refresh and ProcObserver; Off restores watcherless unconditional refresh. Added sase ace -s/--sanity-refresh-interval (default 300s). Lazy event_refresh package export breaks the proc_observer→EventRefreshMixin import cycle.

Tests: previously failing 7 now pass (completion snapshot after just sync-completion-spec; test_provider_drain_e2e_flag_on_relaunches_stranded_agent 8.7s; 4 link-follow panel tests after navigator .get()). Also 72 auto-refresh/token/handler tests, 45 link-follow+state-init+flags+nav-gate, 9 proc-observer token tests. Lint: ruff, mypy (4007 files), flags, test-waits, changelog, terminology, symvision, prettier. just check still blocked by pre-existing toobig on link_follow.py. sase bead epic-symbols sase-wn.5: none leftover. Did not close parent sase-wn.

## Dependencies

- **Blocks:** [sase-wn.10](sase-wn.10.md) ◐ · ⧖ 2026-09-04
- **Blocks:** [sase-wn.6](sase-wn.6.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wn.5.md) | [sase-wn.5](sase-wn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2eb1335`](https://github.com/sase-org/sase/commit/2eb13350f991a84b340f4d6619334b9311bd7f9c) | feat(ace): gate auto-refresh on per-surface change tokens | [sase-wn.5](sase-wn.5.md) | 2026-09-04 20:53:28 EDT |
