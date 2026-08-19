# Bead: sase-r1.2 — Pane-free, scope-aware update preview

[Bead Pages](../README.md) / [sase-r1](README.md) / sase-r1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.080](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.080.md) · **Assignee:** `sase-r1.2` · **Size:** medium
**Created:** 2026-08-19 12:05:14 EDT · **Closed:** 2026-08-19 14:08:16 EDT
**Plan:** [202608/update\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/update_panel.md)

## Description

preview: introduce UpdateLeg/UpdateScope, collect preview inputs without the Updates pane, and teach the comprehensive preview and its confirm rendering to cover only the selected legs.

## Notes

[2026-08-19T17:32:56Z · sase-r1.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py reports the checked-in CLI completion spec is out of sync with the argparse tree — reproduce with pytest tests/completion/test_snapshot.py and just sync-completion-spec; this phase did not change the CLI.

[2026-08-19T17:33:14Z · sase-r1.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width asserts compact but gets full; reproduces in isolation and is unrelated to update preview.

[2026-08-19T18:08:16Z · sase-r1.2--1] Verified UpdateLeg/UpdateScope, collect_update_preview_inputs (skips unneeded legs), and build_comprehensive_update_preview plan only selected legs; confirm copy/sections and scoped noop toasts name the chosen scope; unselected legs are omitted rather than skipped. Targeted tests: 60 passed (test_comprehensive_update_preview + pane comprehensive update/confirmation/loading). just check escalated (core-identity-changed, justfile) and failed on known unrelated: CLI completion snapshot drift, tab-strip compact reflow, ACE PNG renderer env (no just install-visual). epic-symbols: no leftovers for sase-r1.2; collect_update_preview_inputs remains keyed to sase-r1.3.

[2026-08-19T18:09:58Z · sase-r1.2--1] Verified pane-free scoped update preview: UpdateLeg/UpdateScope, collect_update_preview_inputs, build_comprehensive_update_preview plans only selected legs; confirm copy/sections/noop toasts omit unselected legs. epic-symbols sase-r1.2 has no leftovers (collect_update_preview_inputs keyed to sase-r1.3). Targeted tests 60 passed (test_comprehensive_update_preview plus pane comprehensive-update, confirmation, loading). Escalated just check 4 failed/14 errors all out of scope: CLI completion snapshot drift, tab-strip compact reflow, ACE PNG renderer env without just install-visual.

## Dependencies

- **Blocks:** [sase-r1.3](sase-r1.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r1.5](sase-r1.5.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r1.2.md) | [sase-r1.2](sase-r1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba03cec`](https://github.com/sase-org/sase/commit/ba03cec630e37b70d0e92da78acdbba2437f80e4) | feat(ace): scope comprehensive update preview to selected legs | [sase-r1.2](sase-r1.2.md) | 2026-08-19 14:11:14 EDT |
