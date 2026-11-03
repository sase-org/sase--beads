# Bead: sase-1qz.3 — Runner settlement that keeps custody

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.33.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.33.linker.w0.md) · **Assignee:** `sase-1qz.3` · **Size:** medium
**Created:** 2026-11-02 17:42:15 EST · **Closed:** 2026-11-03 02:38:33 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

settle: add the Python ledger store, the hijack-mode user-kill intent, and the runner capability stamp. The runner learns to settle `outcome: hijacked` while holding its workspace claim: the SIGTERM handler, the killed iteration, the shutdown hold, done.json, and the finalize boundary.

## Notes

[2026-11-03T07:38:18Z · sase-1qz.3--2] PROPOSED FOLLOW-UP: tests/footprint/test_tui.py::test_bump_microbench_stays_within_two_microseconds still exceeds 2µs here (2.209µs) after hijack settlement — already tracked by sase-1q0; other NEW items from the full-suite just check did not reproduce on re-run.

[2026-11-03T07:38:33Z · sase-1qz.3--2] Settle phase complete: Python hijack ledger, hijack-mode user-kill intent, runner_capabilities stamp, SIGTERM hold, killed-iteration outcome hijacked, done.json recovery pending, claim pin with expected_pid, no notify/auto-dismiss, finalize skip, TUI HIJACKED mirrors. 95 targeted tests passed after routing hijacked done.json through write_done_marker_and_update_index (fixes marker-mutation audit). Full-suite just check lint was green; remaining bump microbench is sase-1q0.

## Dependencies

- **Depends on:** [sase-1qz.1](sase-1qz.1.md) ✓ · ⧖ 2026-11-02
- **Blocks:** [sase-1qz.4](sase-1qz.4.md) ◐ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1qz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1qz.3.md) | [sase-1qz.3](sase-1qz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`01a2828`](https://github.com/sase-org/sase/commit/01a28287c8f7d2ce5c7ae71e769e74a377892ea7) | feat(agent-hijack): settle hijacked runner outcome while holding custody | [sase-1qz.3](sase-1qz.3.md) | 2026-11-03 03:22:28 EST |
