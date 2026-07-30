# Bead: sase-b0.7 — Visual snapshots and documentation polish

[Bead Pages](../README.md) / [sase-b0](README.md) / sase-b0.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b0.7` · **Size:** small
**Created:** 2026-07-29 23:14:15 UTC · **Closed:** 2026-07-30 02:06:03 UTC
**Plan:** [202607/artifacts\_files\_subtab.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifacts_files_subtab.md)

## Description

visual-docs: add populated and empty PNG snapshot coverage for the Files pane, verify icons and chips render distinctly, and finish the docs/ace.md, help, onboarding, and quickstart sweeps including six-way sub-tab numbering and the stale path-copy doc line.

## Notes

[2026-07-30T02:06:03Z · sase-b0.7] visual-docs phase complete. Added tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files.py (populated: all 5 view modes incl. every glyph, an explicit ◆ row, an unenriched None-metadata row, 2 projects, Today/Yesterday groups, live+missing path badges) and ..._files_empty.py, with new goldens artifacts_files_{populated,empty}_120x40.png accepted via --sase-update-visual-snapshots after visually confirming the four glyphs and the origin badge are distinguishable and columns align. Also refreshed the stale help_keymaps_changespecs_120x40.png golden (scrollbar drift from this epic's help-modal Files Pane section). Docs: docs/ace.md now says six focused sub-tabs, strip '1 Commits · 2 Plans · 3 Chats · 4 Bugs · 5 PRs · 6 Files', a new '### Files Pane' section (glyph/view-mode table, chips, off-thread two-phase load, detail panel, full key table, Filtering Files subsection), Files copy-mode row expanded to %@ %! %% %p %o %l %j, Navigation/Marks headings and the query-key table include Files, and the stale 'workspace-relative when possible' Y line in the artifact-file modal now describes anchored stored-path copy with the shared-helper note; docs/cli.md sase artifact row cross-references ace.md#files-pane; docs/getting_started.md five→six sub-tabs. Verified help modal, onboarding card, and tab quickstart already carry six-way numbering and every Files key. Extended tests/test_command_availability_changespecs.py so copy.artifacts_files.* is asserted available exactly on the Files pane. just lint clean; just test-visual 389 passed; full just test green (3 unrelated flakes pass in isolation). just check still fails only on pre-existing SDD plan-link errors in the plans sidecar (copy_as_palette, xprompt_swarm_stats, artifacts_files_subtab prompt links) which I did not touch. Note for follow-up: at 120 cols the row SIZE column is always elided away by the label, so sizes are only visible in the detail panel.

## Dependencies

- **Depends on:** [sase-b0.3](sase-b0.3.md) ✓
- **Depends on:** [sase-b0.4](sase-b0.4.md) ✓
- **Depends on:** [sase-b0.6](sase-b0.6.md) ✓
