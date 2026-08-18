# Bead: sase-p1.7 — Prompt keymap entry point and focus handoff

[Bead Pages](../README.md) / [sase-p1](README.md) / sase-p1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.056](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md) · **Assignee:** `sase-p1.7` · **Size:** small
**Created:** 2026-08-17 17:42:40 EDT · **Closed:** 2026-08-17 23:13:36 EDT
**Plan:** [202608/glossary\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)

## Description

entry: claim `G` on the prompt `g` prefix table so `gG` and `<ctrl+g>G` both open the panel with a hint row, post the open request as a message the app handles, seed the selection from the glossary term under the cursor, and restore prompt focus and vim mode on close.

## Notes

[2026-08-18T03:13:12Z · sase-p1.7] PROPOSED FOLLOW-UP: just check is red from stale --epic-symbol entries on closed beads sase-p3.11 (RequiredPluginError, fail_closed_required_plugins) and sase-p4.3 (active_epic_resume, build_epic_resume_argv, epic_resume_origin_from_gate_source, submit_epic_resume_task); re-key each to its still-open parent epic or drop the exemption once the symbol has a consumer. Also observed unrelated doctor.repos tests warning on artifact_providers.entry_point_load_failed and test_help_modal_lists_prompt_pane_focus_and_reorder expecting Ctrl+] label without /repo.

[2026-08-18T03:13:36Z · sase-p1.7] gG from NORMAL and <ctrl+g>G from INSERT and NORMAL post GlossaryPanelRequested; hint rows list glossary… on both g and ^G surfaces; the message carries the cursor term or None; the app handler opens GlossaryPanel with that seed and launch workspace; dismiss restores prompt focus, vim mode, and cursor; gg still jumps to buffer start; sase-p1.7 epic-symbols are gone; ruff/mypy/fmt and the dedicated g-prefix/entry tests passed. just check itself is red on unrelated stale --epic-symbol entries for closed sase-p3.11 and sase-p4.3.

[2026-08-18T03:14:25Z · sase-p1.7] gG from NORMAL and <ctrl+g>G from INSERT and NORMAL post GlossaryPanelRequested; hint rows list glossary… on both g and ^G surfaces; the message carries the cursor term or None; the app handler opens GlossaryPanel with that seed and launch workspace; dismiss restores prompt focus, vim mode, and cursor; gg still jumps to buffer start; sase-p1.7 epic-symbols are gone; ruff/mypy/fmt and the dedicated g-prefix/entry tests passed.

## Dependencies

- **Depends on:** [sase-p1.5](sase-p1.5.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p1.6](sase-p1.6.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p1.8](sase-p1.8.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.7/README.md) | [sase-p1.7](sase-p1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad01e3c`](https://github.com/sase-org/sase/commit/ad01e3c60647c962db7a4f1f4df8dd2453cbd5e1) | feat(tui): open glossary panel from prompt gG and Ctrl+G G | [sase-p1.7](sase-p1.7.md) | 2026-08-17 23:15:45 EDT |
