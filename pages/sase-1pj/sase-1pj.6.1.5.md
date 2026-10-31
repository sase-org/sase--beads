# Bead: sase-1pj.6.1.5 — Close monitor spawn and held-reservation crash windows

[Bead Pages](../README.md) / [sase-1pj.6.1](sase-1pj.6.1.md) / sase-1pj.6.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.5` · **Size:** medium
**Created:** 2026-10-31 08:56:55 EDT · **Closed:** 2026-10-31 12:18:00 EDT
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

## Description

monitor-replay: recover monitor launch from existing fingerprint and proc identities, including completed commands, and retain or safely restore held reservations and prepared completion evidence across retries.

## Notes

[2026-10-31T16:17:37Z · sase-1pj.6.1.5] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails under host load (fails identically on clean base with this phase overlaid away; module-count siblings pass). Already tracked by sase-1pm.4; re-run on a quiet host before treating as signal.

[2026-10-31T16:17:43Z · sase-1pj.6.1.5] PROPOSED FOLLOW-UP: split src/sase/monitor/start_stage_adopt.py (856 lines, over the 850 toobig warning threshold) following the start_stage persist/adopt/cleanup split precedent once a later phase touches it.

[2026-10-31T16:18:00Z · sase-1pj.6.1.5] monitor-replay complete: adopt-existing-proc recovery (active+terminal reuse, fingerprint refusal, barrier release, claim ensure), held-reservation reacquire (fresh ToolRun on never-ran proof incl. live-stage check; prepared retain-or-restore), held cleanup preserves submitted effects (discard unchanged). Verified: 9 new recovery tests + 36 stage/axe neighbor tests green; ruff/mypy/symvision/test-waits/keep-sorted pass; scoped gate 59398 passed with 1 pre-existing load-flake (import budget, fails on base too, recorded as follow-up citing sase-1pm.4)

## Dependencies

- **Depends on:** [sase-1pj.6.1.1](sase-1pj.6.1.1.md) ✓ · ⧖ 2026-10-31
- **Blocks:** [sase-1pj.6.1.6](sase-1pj.6.1.6.md) ◐ · ⧖ 2026-10-31

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.5/README.md) | [sase-1pj.6.1.5](sase-1pj.6.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b674079`](https://github.com/sase-org/sase/commit/b674079c2be562c75a28f64775da93f4ec820bab) | feat(staged-recovery): close monitor spawn and held-reservation crash windows | [sase-1pj.6.1.5](sase-1pj.6.1.5.md) | 2026-10-31 12:20:19 EDT |
