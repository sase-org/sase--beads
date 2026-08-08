# Bead: sase-h7.13.5 — Land the epic

[Bead Pages](../README.md) / [sase-h7.13](sase-h7.13.md) / sase-h7.13.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.land/README.md) · **Assignee:** `sase-h7.13.5` · **Size:** small
**Created:** 2026-08-07 23:12:36 EDT · **Closed:** 2026-08-08 00:05:27 EDT
**Plan:** [202608/gate\_inputs\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_inputs_landing.md)

## Description

land: run the full gate across both repos, close epic bead sase-h7 with a verification note, clear the epic's expired symvision whitelist entries, and mark the epic plan file done.

## Notes

[2026-08-08T04:08:17Z · sase-h7.13.5] just install; just check-full: all 6 previously-recorded epic-caused failures now pass (27554 passed, 10 skipped); 2 failures remain but are unrelated master drift outside this epic (test_content_layout schema_version 1 vs 2; an ACE commits-pane test that passes in isolation, an xdist ordering flake) — filed as follow-up, not fixed here. just test-visual: 561 passed, 1 known pre-existing PNG snapshot failure (frontmatter_panel_raw_diagnostics) confirmed still failing, outside epic scope — filed as follow-up per the plan's own instruction. sase-telegram, verified with this workspace's sase installed over the PyPI copy: ruff clean, mypy clean (22 files), pytest 557 passed / 3 failed — presentation.title fix fully verified (0 title failures, down from 9; _custom_spec and _inputs_gate_spec both already set title/icon/notes; build_task_triage_gate_spec is task_triage kind, unaffected, confirmed no change needed), the 3 remaining failures are unrelated regressions from already-closed epic phases h7.2/h7.11 (per-option feedback buttons) plus a pre-existing bead_snooze registry gap predating this epic — filed as follow-up. just symvision: clean, no --epic-symbol whitelist entries existed for this epic to clear. plans/202608/gate_input_collection.md: status: done committed to the plans sidecar. Could NOT close epic bead sase-h7 as this bead's description asked: the close guard requires parent epic sase-h7.13 closed first, and I was explicitly instructed not to close the parent epic — left for sase-h7.13's assigned land agent (sase-h7.13.land) now that all 5 phases are closed. Note: this bead auto-closed via the before-commit hook during the plans-sidecar commit before I could attach this note, reproducing the same premature-close bug recorded against sase-h7.3.

[2026-08-08T04:08:30Z · sase-h7.13.5] PROPOSED FOLLOW-UP: sase commit's before-commit hook auto-closed sase-h7.13.5 itself during an unrelated plans-sidecar commit, before the land agent finished its verification work — the same premature-close bug already recorded against sase-h7.3 in this epic's notes, now confirmed to also fire on a plans-sidecar (not just sase-core) commit.

[2026-08-08T04:08:43Z · sase-h7.13.5] PROPOSED FOLLOW-UP: just check-full on clean master (with sase-h7.13's 4 phases merged) has 2 unrelated failures outside this epic's scope: tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical asserts schema_version == 1 but the Rust core now returns 2 (deterministic, reproduces in isolation); tests/ace/tui/test_commits_pane_rendering.py::test_commits_renderer_builds_compact_single_line_rows fails only under the full parallel xdist run and passes in isolation (test-order/pollution flake).

[2026-08-08T04:08:57Z · sase-h7.13.5] PROPOSED FOLLOW-UP: sase-telegram's tests/test_custom_gates.py has 3 failures unrelated to this epic's own scope (presentation.title is fully fixed): test_registry_declared_generic_forms_render_keyboards KeyErrors on 'bead_snooze' (a generic_form=True adapter that predates epic sase-h7 entirely, never wired into that test's notifications dict); test_task_triage_outbound_renders_tracks_attaches_and_launches and test_launch_approval_uses_the_same_singleton_renderer both expect stale keyboards that don't account for the per-option feedback buttons and task_triage snooze option that already-closed epic phases sase-h7.2 (feedback-input) and sase-h7.11 (retire-smuggling) shipped before sase-h7.13 began. sase-telegram's fixtures need updating to match current sase behavior.

## Dependencies

- **Depends on:** [sase-h7.13.1](sase-h7.13.1.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.13.2](sase-h7.13.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.13.3](sase-h7.13.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.13.4](sase-h7.13.4.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.13.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.13.5/README.md) | [sase-h7.13.5](sase-h7.13.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@c03880e`](https://github.com/sase-org/sase--plans/commit/c03880e1c13e9a6aaee3321fae2532a835f44062) | docs(plans): mark the gate input collection epic done | [sase-h7.13.5](sase-h7.13.5.md) | 2026-08-08 00:05:38 EDT |
