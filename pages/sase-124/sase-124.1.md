# Bead: sase-124.1 — Stop refresh-pulse writes from poisoning the bounded artifact-delta path

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.1` · **Size:** medium
**Created:** 2026-09-17 10:59:41 EDT · **Closed:** 2026-09-17 12:35:39 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

pulse-delta: classify project-level .ace_refresh_pulse watcher paths as a pure freshness kick instead of an unknown_watcher_path fallback (leaving per-agent-directory pulses exact for sase-zr.7.3), and fix sase-zc by routing the two misplaced pulse writers through the existing touch_shell_refresh_pulse helper.

## Notes

[2026-09-17T16:34:54Z · sase-124.1] PROPOSED FOLLOW-UP: Resolve sase-zc when epic lands — the misplaced shell-handoff and plan-propose refresh-pulse writers now route through touch_shell_refresh_pulse(project_name_from_artifacts_dir(...)) and write the project artifacts root pulse for sharded layouts.

[2026-09-17T16:35:39Z · sase-124.1] Implemented project-level refresh-pulse delta classification and routed shell/plan pulse writers through touch_shell_refresh_pulse; verified focused pytest coverage, artifact-dir audit tests, git diff --check, just fmt, and just check lint/validation gates. The just check test lane escalated to full suite and hit three unrelated failures; all three passed on direct rerun.

## Dependencies

- **Blocks:** [sase-124.6](sase-124.6.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-124.7](sase-124.7.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.1/README.md) | [sase-124.1](sase-124.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43ddcf1`](https://github.com/sase-org/sase/commit/43ddcf15f5a72a8bdbcb708692b8d9fe2ab106d1) | fix(tui): keep refresh pulses out of broad fallback | [sase-124.1](sase-124.1.md) | 2026-09-17 12:37:30 EDT |
