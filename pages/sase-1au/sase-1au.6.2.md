# Bead: sase-1au.6.2 — Retire dead prompt modal surface and repair extraction test drift

[Bead Pages](../README.md) / [sase-1au.6](sase-1au.6.md) / sase-1au.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1au.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1au.land.md) · **Assignee:** `sase-1au.6.2` · **Size:** medium
**Created:** 2026-09-26 20:02:02 EDT · **Closed:** 2026-09-26 20:48:22 EDT
**Plan:** [202609/prompts\_overlay\_cutover\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompts_overlay_cutover_remainder.md)

## Description

retire_old_modal: resolve cutover unused symbols under Symvision policy and make the residual freeze soak exercise the live History pane.

## Notes

[2026-09-27T00:48:04Z · sase-1au.6.2--1] PROPOSED FOLLOW-UP: just check residual failures reproduce on clean base (proc-shell AgentType.PROC_SHELL AttributeError incl. test_proc_shell_details_show_diagnostics_when_fully_expanded; 8 mypy + 16 symvision KNOWNs) belong to turn-rename epic sase-1ab triage, not this phase

[2026-09-27T00:48:22Z · sase-1au.6.2--1] retire_old_modal done: PromptHistoryModal deleted, trash/stash helpers privatized, soak+modal suites green (76+10 passed), 5 cutover symvision findings absent, mypy clean on modals; just check residuals reproduce identically on clean base

## Dependencies

- **Blocks:** [sase-1au.6.3](sase-1au.6.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1au.6.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1au.6.2.md) | [sase-1au.6.2](sase-1au.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cdcc882`](https://github.com/sase-org/sase/commit/cdcc88251ff4ebb24d409055d590eb03b0fdf626) | feat(ace): retire dead prompt modal surface and repair soak extraction (sase-1au.6.2) | [sase-1au.6.2](sase-1au.6.2.md) | 2026-09-26 20:50:21 EDT |
