# Bead: sase-1qn.4 — Fix the zsh sbd alias completion PTY flake (sase-13a)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.4` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

zsh-completion-pty-flake: reproduce tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree timing out in loaded full lanes (+15, latest 2026-10-31). Identify whether PTY startup, completion-cache warmup, or shared state causes the stall, and fix the cause without dropping the alias completion assertion or simply raising its timeout.

## Notes

[2026-11-01T20:13:17Z · sase-1qn.4] PLANNING EVIDENCE: Clean base 078e3da1d6a784cfc8fd2ab783273246318660c2, zsh 5.9; no prior phase work notes or landed fix to test_zsh_smoke.py (last change 82fae375ba, 2026-09-15). The unchanged helper uses inherited PATH when bin_dir is omitted. A logged fixture shows sbd sh calls no backend, but sbd show --for invokes <completion><candidates><bead> before inserting --format. Immediate empty fixture response: startup 0.343s, completion 0.281s, exact expected buffer. Delaying only that response 6s: startup 0.339s, completion timeout 5.025s, exact reported symptom (only b'sbd show --for' received). Controlled delay reproduction, not a fresh natural full-lane reproduction. Existing ZDOTDIR and zsh disk cache are per invocation. One medium tale is sufficient: default test-owned candidate executable, inherited-PATH sentinel regression, unchanged real-zsh assertions/timeouts, bounded loaded module runs and check. Plan sase_plan_zsh_completion_pty_isolation.md validated with zero warnings; submitting it before source changes. No tracked files changed. No epic-symbol entries currently. Implementation and closure belong to the approved coder; this is planning evidence, not a TASK RESOLVED claim.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.4.md) | [sase-1qn.4](sase-1qn.4.md) | 0 |
