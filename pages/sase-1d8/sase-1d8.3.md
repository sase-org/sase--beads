# Bead: sase-1d8.3 — TUI submissions carry their history text and origin

[Bead Pages](../README.md) / [sase-1d8](README.md) / sase-1d8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ud](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ud.md) · **Assignee:** `sase-1d8.3` · **Size:** medium
**Created:** 2026-09-30 07:44:50 EDT · **Closed:** 2026-09-30 11:32:55 EDT
**Plan:** [202609/prompt\_history\_human\_only.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_history_human_only.md)

## Description

tui-provenance: keep the pre-remodel prompt on PendingLaunch and send it as history_text; mark member-agent relaunches and mentor-apply launches generated across submit, cancel and failed-launch recovery.

## Notes

[2026-09-30T15:32:16Z · sase-1d8.3--2] PROPOSED FOLLOW-UP: just check _setup fails at tools/validate_sase_core_rs prompt-prediction probe (confident=False, no ghost; validator expects confident=True ghost=[the]) on clean base too — sase-core 0.36.1 checkout drift vs validator; needs core-side triage

[2026-09-30T15:32:55Z · sase-1d8.3--2] tui-provenance done: PendingLaunch.history_prompt + prompt_origin plumbing, history_text/history_origin payload, generated member-relaunch + mentor-apply marking, recovery paths use original text. Verified: 54 TUI tests pass (test_tui_provenance 9 + pending_launch/kill-edit/editor-stack), ruff + fmt + mypy clean. just check blocked pre-existing: validate_sase_core_rs probe fails identically on clean base (recorded as follow-up).

## Dependencies

- **Depends on:** [sase-1d8.2](sase-1d8.2.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d8.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d8.3.md) | [sase-1d8.3](sase-1d8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a8bf3e4`](https://github.com/sase-org/sase/commit/a8bf3e41a8ecc98bf4cf5833d2a0c68384bf134d) | feat(history): TUI submissions carry history text and origin | [sase-1d8.3](sase-1d8.3.md) | 2026-09-30 11:35:35 EDT |
