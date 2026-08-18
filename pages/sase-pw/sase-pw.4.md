# Bead: sase-pw.4 — Top-bar +project indicator

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.4` · **Size:** medium
**Created:** 2026-08-18 11:30:33 EDT · **Closed:** 2026-08-18 14:46:44 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

indicator: add the `CurrentProjectIndicator` widget, mount it in the top-bar cluster right of the model indicator, and give it the poll/peek/off-thread resolve lifecycle, tooltip, and click action.

## Notes

[2026-08-18T18:45:41Z · sase-pw.4] PROPOSED FOLLOW-UP: ci mypy src/sase/glossary/render.py:74 — Console.color_system is str | None but Console() expects Literal[auto|standard|256|truecolor|windows] | None. Reproduces on 88fa6e949 without this phase tree and still blocks just check before scoped tests (same defect sase-pw.1 already noted).

[2026-08-18T18:45:55Z · sase-pw.4] PROPOSED FOLLOW-UP: ci tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and test_current_structural_view_matches_checked_in_snapshot — field-order drift in the checked-in CLI spec vs argparse tree. Unrelated to the current-project chip (no parser/CLI files in this phase); escalated just test-scoped surfaced it because Justfile lost the sase-pw.4 --epic-symbol lines.

[2026-08-18T18:46:44Z · sase-pw.4] Added CurrentProjectIndicator, mounted at #current-project-indicator immediately after ProviderDisablesIndicator, with 5s peek/worker lifecycle, +<display_name> accent chip, tooltip, and click -> start_custom_agent. Verified: resolved project renders ' +sase ' with accent on both runs; unresolved and indicator:false render '' and take zero width; Patch-origin chip still shows the project name and names the Patch only in the tooltip; tick peeks without calling resolve when the token is unchanged; a token change schedules exactly one worker and a second tick before it lands does not schedule another; click dispatches start_custom_agent; both 80-col top-bar bounds tests still pass with the chip rendered. Re-keyed leftover project_accent_map onto still-open sase-pw.8; sase bead epic-symbols sase-pw.4 reports no leftovers. just check: fmt/ruff/keep-sorted/symvision/toobig/validate green; mypy still fails on pre-existing glossary/render.py:74; escalated scoped suite 33481 passed, 2 unrelated completion-snapshot failures (noted as PROPOSED FOLLOW-UP).

[2026-08-18T18:48:40Z · sase-pw.4] Added CurrentProjectIndicator mounted after ProviderDisablesIndicator with 5s peek/worker lifecycle, +<display_name> accent chip, tooltip, and click -> start_custom_agent. Verified: resolved project renders ' +sase ' with dim + and bold name in the project accent; unresolved and indicator:false render empty and take zero width; Patch-origin chip shows the project name and names the Patch only in the tooltip; tick peeks without resolve when the token is unchanged; a token change schedules exactly one worker and a second tick before it lands does not schedule another; click dispatches start_custom_agent; both 80-col top-bar bounds tests still pass with the chip painted. sase bead epic-symbols sase-pw.4 reports no leftovers (unused project_accent_map re-keyed to still-open sase-pw.8).

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.2](sase-pw.2.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.3](sase-pw.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.4/README.md) | [sase-pw.4](sase-pw.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7596e4e`](https://github.com/sase-org/sase/commit/7596e4e46ed68e977072df94d0a69a93069909ee) | feat(ace): add current-project chip to the ACE top bar | [sase-pw.4](sase-pw.4.md) | 2026-08-18 14:49:32 EDT |
