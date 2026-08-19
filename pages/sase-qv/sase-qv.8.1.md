# Bead: sase-qv.8.1 — Honor recorded stop status in dismissed-archive wait resolution

[Bead Pages](../README.md) / [sase-qv.8](sase-qv.8.md) / sase-qv.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-qv.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qv.land.md) · **Assignee:** `sase-qv.8.1` · **Size:** small
**Created:** 2026-08-19 16:11:12 EDT · **Closed:** 2026-08-19 17:12:06 EDT
**Plan:** [202608/qv\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202608/qv_remaining.md)

## Description

waits: classify dismissed-bundle monitor outcomes from the recorded monitor_stop_status instead of only the literal MONITORED default.

## Notes

[2026-08-19T21:11:16Z · sase-qv.8.1] PROPOSED FOLLOW-UP: tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration failed once in the Justfile-escalated full lane (InstallResult.registered was None); isolation rerun on the same tree passed in 2.02s with -p no:randomly. Not caused by dismissed-archive wait resolution.

[2026-08-19T21:11:34Z · sase-qv.8.1] PROPOSED FOLLOW-UP: Re-keyed stale --epic-symbol entries for closed beads sase-qx.5 (LaunchUnit, LaunchUnitCandidate, blocked_launch_units, plan_launch_units) and sase-r1.5 (UpdatePanel, UpdatePanelResult, build_update_panel_state) to still-open parents sase-qx and sase-r1 so just check is green; dropped UpdateOptionChip/UpdateOptionRow/UpdatePanelState as used. Those land agents must consume or drop the remaining unused public symbols before closing.

[2026-08-19T21:12:06Z · sase-qv.8.1] Dismissed-archive wait resolution now matches status against the bundle recorded monitor_stop_status (clamped, case-insensitive) instead of only the literal MONITORED default. Known-status table still wins first. Verified: test_dismissed_agent_completion.py 35 passed (default MONITORED with no pair still uses monitor_state; recorded TESTED pair uses monitor_state for completed/stopped/failed/timeout/None; mixed-case tested/TESTED resolves; unrecorded SLEPT and mismatched SLEPT/TESTED fail closed). sase bead epic-symbols sase-qv.8.1: none. just check lint green; Justfile justfile-rule escalation ran the full lane 34715 passed / 1 unrelated flake (test_real_zsh_zcompile_and_registration, isolation rerun passed). Re-keyed stale sase-qx.5/sase-r1.5 epic-symbols to open parents so symvision is green.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.8.1/README.md) | [sase-qv.8.1](sase-qv.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3df3452`](https://github.com/sase-org/sase/commit/3df34525c0113a5cb7693c1a52c55e81be914383) | fix(core): honor recorded monitor stop status in dismissed-archive waits | [sase-qv.8.1](sase-qv.8.1.md) | 2026-08-19 17:23:56 EDT |
