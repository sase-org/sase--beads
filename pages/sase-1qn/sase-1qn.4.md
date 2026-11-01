# Bead: sase-1qn.4 — Fix the zsh sbd alias completion PTY flake (sase-13a)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.4` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST · **Closed:** 2026-11-01 16:12:26 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

zsh-completion-pty-flake: reproduce tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree timing out in loaded full lanes (+15, latest 2026-10-31). Identify whether PTY startup, completion-cache warmup, or shared state causes the stall, and fix the cause without dropping the alias completion assertion or simply raising its timeout.

## Notes

[2026-11-01T20:13:17Z · sase-1qn.4] PLANNING EVIDENCE: Clean base 078e3da1d6a784cfc8fd2ab783273246318660c2, zsh 5.9; no prior phase work notes or landed fix to test_zsh_smoke.py (last change 82fae375ba, 2026-09-15). The unchanged helper uses inherited PATH when bin_dir is omitted. A logged fixture shows sbd sh calls no backend, but sbd show --for invokes <completion><candidates><bead> before inserting --format. Immediate empty fixture response: startup 0.343s, completion 0.281s, exact expected buffer. Delaying only that response 6s: startup 0.339s, completion timeout 5.025s, exact reported symptom (only b'sbd show --for' received). Controlled delay reproduction, not a fresh natural full-lane reproduction. Existing ZDOTDIR and zsh disk cache are per invocation. One medium tale is sufficient: default test-owned candidate executable, inherited-PATH sentinel regression, unchanged real-zsh assertions/timeouts, bounded loaded module runs and check. Plan sase_plan_zsh_completion_pty_isolation.md validated with zero warnings; submitting it before source changes. No tracked files changed. No epic-symbol entries currently. Implementation and closure belong to the approved coder; this is planning evidence, not a TASK RESOLVED claim.

[2026-11-01T21:12:26Z · sase-1qn.4] TASK RESOLVED: sase-13a — zsh PTY smoke helper no longer forks an inherited live `sase` when `bin_dir` is omitted.

Base: 078e3da1d6a784cfc8fd2ab783273246318660c2, zsh 5.9. Last test_zsh_smoke.py change remained 82fae375ba (2026-09-15). Natural flake was not observed on the unchanged module (ToolRun 2d80d9ef83ea69fe2c0923e55c875282: 4/4 workers, 21 passed in 9.26s). Controlled delayed-reply reproduction retained as evidence.

Before (logged empty fixture, existing `_read_until` budgets unchanged):
- `sbd sh`: no candidate call; startup 0.349s; completion 0.272s; buffer `sbd show `
- `sbd show --for` immediate: log `<completion><candidates><bead>`; startup 0.350s; completion 0.265s; buffer `sbd show --format `
- `sbd show --for` with 6s fixture delay: same log; startup 0.353s; completion timeout 5.025s; received only `sbd show --for`

Fix: `_pty_capture_completion` always prepends a test-owned `sase` to PATH. Explicit `bin_dir` is unchanged. Omitted `bin_dir` gets a per-capture logged empty-candidate fixture under `pty-sase-<nonce>/`. Live compsys, alias expansion, TAB, capture-widget, and timeout budgets are unchanged.

Sentinel regression `test_pty_capture_without_bin_dir_ignores_inherited_sase`:
- Original helper: ToolRun 4f4a3548f404a3372f3077f00fafa79b FAILED; exact buffer still `sbd show --format `, inherited sentinel was invoked (`assert not sentinel_log.exists()`).
- After fix: ToolRun ed8234978402aa4fdac6cc9f63aa7909; sentinel + both static alias parameters 3 passed.

After inherited 6s slow-provider probe (no `bin_dir`): startup 0.411s; completion 0.328s (inside 5s budget); buffer `sbd show --format `; inherited sentinel never invoked.

Loaded module runs (SASE_PYTEST_WORKERS=4, distinct TMPDIR, 22 tests including sentinel):
- 3a8e7de191f6562d30018c586a6339c3: 4/4 workers, 22 passed in 9.91s
- 551d056cb37f380233c206261e57f148: 4/4 workers, 22 passed in 9.67s
- 07db0f3bd2a2b7f406a2b4d379dde92c: 4/4 workers, 22 passed in 8.76s

`sase tool run check` b6a56cfa45850e3172adeb78a4f3323e succeeded (triage pass/exited_zero). test (scoped) 38m 47s exit 0; selector escalated to the full suite (`core-identity-changed`). No skips, xfails, timeout raises, or flake-baseline edits.

Limits: injected 6s delay is a controlled subprocess stall, not a fresh natural full-lane reproduction. Dynamic callers still supply their own fixtures and call-count/log assertions. Leave sase-13a and epic sase-1qn to the lander. No --epic-symbol entries for this phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.4.md) | [sase-1qn.4](sase-1qn.4.md) | 0 |
