# Bead: sase-s3.2 — Bind the committed Python cleanup path to the released core

[Bead Pages](../README.md) / [sase-s3](README.md) / sase-s3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0av](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0av.md) · **Assignee:** `sase-s3.2` · **Size:** medium
**Created:** 2026-08-22 13:57:33 UTC · **Closed:** 2026-08-22 16:02:03 UTC
**Plan:** [202608/0ak\_failure\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/0ak_failure_recovery.md)

## Description

python_monitor_integration: raise the core dependency floor, prove Rust/Python parity, and verify the committed monitor-stop lifecycle end to end.

## Notes

[2026-08-22T15:28:09Z · sase-s3.2] Raised sase-core-rs floor to >=0.30.0,<0.31.0 and refreshed uv.lock. just install reports package 0.30.0 / wire schema 4; focused facade/parity/persist/named-kill/TUI/owner-cleanup tests pass (70). Strengthened facade tests so live-monitor and clan-sequential cases fail if the Rust planner falls back to Python. First escalated just check had 17 failures from a 2-commit-behind tree (sase-s2.3 archive stubs + contract manifest) and a stale 0.29.9 sase-xprompt-lsp; fast-forwarded origin and rebuilt LSP 0.30.0; those tests now pass. Starting just check-full via monitor.

[2026-08-22T16:01:32Z · sase-s3.2--1] PROPOSED FOLLOW-UP: sase-lk recurrence — tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child failed just check-full with supervisor subprocess did not exit within 15s (36076 passed); isolated rerun passed in 3.78s. Existing READY flake bead sase-lk already covers this node; not caused by the sase-core-rs 0.30.0 floor bump.

[2026-08-22T16:01:33Z · sase-s3.2--1] just check-full: 36076 passed, 11 skipped, 1 failed. Failure is tests/monitor/test_monitor_supervise.py::test_run_supervisor_escalates_term_ignoring_chatty_child (supervisor subprocess did not exit within 15s under the full parallel lane). Isolated rerun passed in 3.78s. Unrelated to the sase-core-rs 0.30.0 floor bump (diff is pyproject.toml, uv.lock, and test_agent_cleanup_facade.py only). Tracked by existing READY flake bead sase-lk. Focused cleanup tests still green: facade/python/targets 58 passed; execution/named-kill/TUI live-monitor-kill/stop-action 18 passed. Installed binding reports schema 4 (dev install is linked sase-core 0.31.0 ahead of the published 0.30.0 window, which is the normal just install path).

[2026-08-22T16:02:03Z · sase-s3.2--1] Raised sase-core-rs floor to >=0.30.0,<0.31.0; installed binding reports schema 4; Rust planner handles live-monitor selection/cascade without Python fallback; focused cleanup tests passed (facade/python/targets 58, execution/named-kill/TUI/stop-action 18). just check-full: 36076 passed / 1 failed on known sase-lk flake test_run_supervisor_escalates_term_ignoring_chatty_child (isolated rerun passed in 3.78s; noted as PROPOSED FOLLOW-UP and +1 on sase-lk).

## Dependencies

- **Depends on:** [sase-s3.1](sase-s3.1.md) ✓ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s3.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-s3.2.md) | [sase-s3.2](sase-s3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`959d559`](https://github.com/sase-org/sase/commit/959d55926de21dc2106a65d943fb3e8e268d1f3b) | feat: raise sase-core-rs floor to 0.30.0 | [sase-s3.2](sase-s3.2.md) | 2026-08-22 16:03:33 UTC |
