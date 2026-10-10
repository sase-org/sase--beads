# Bead: sase-1j6.10.3 — Correct probe module names and quiescence code-change times

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.3` · **Size:** small
**Created:** 2026-10-10 08:09:07 EDT · **Closed:** 2026-10-10 08:42:00 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

probe-quiescence: map frame paths in src-layout editable checkouts to importable module names so the W4 probe can pass, and measure managed-root code changes from ref and reflog mtimes instead of commit times.

## Notes

[2026-10-10T12:41:52Z · sase-1j6.10.3] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on the clean base tree — closed flag bead sase-zg still has a surviving agents_unified_query definition (sase-1jc.6 retired the flag; no open task bead tracks the leftover).

[2026-10-10T12:42:00Z · sase-1j6.10.3] Mapped src-layout editable frames to importable names (src/sase/axe/x.py -> sase.axe.x) and flat plugin frames (sase_telegram/notify.py -> sase_telegram.notify); quiescence now uses HEAD/branch-ref/reflog mtimes so pulling an older commit still counts as a recent change. Verified with tests/test_agent_auto_restart_probe_quiescence.py plus healer probe/quiescence tests (21 passed). sase tool run check failed at lint (feature flags) on the clean tree (sase-zg leftover); recorded as PROPOSED FOLLOW-UP. No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1j6.10.5](sase-1j6.10.5.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.3/README.md) | [sase-1j6.10.3](sase-1j6.10.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9b7fb99`](https://github.com/sase-org/sase/commit/9b7fb99ef7b688d23e9c99fef67c1a11835cd7ac) | fix(agent-auto-restart): map probe modules and use ref mtimes for quiescence | [sase-1j6.10.3](sase-1j6.10.3.md) | 2026-10-10 08:43:44 EDT |
