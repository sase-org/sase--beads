# Bead: sase-qd.2 — Render the current project in the Projects sub-tab

[Bead Pages](../README.md) / [sase-qd](README.md) / sase-qd.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.2` · **Size:** medium
**Created:** 2026-08-18 18:14:39 EDT · **Closed:** 2026-08-18 18:52:48 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

pane-display: give ProjectsPane a reusable off-thread current-project resolve (replacing the seed-only worker), cache it in session state, and render it as a `CUR` column marker plus accent-colored name, a `current: +<name>` segment in the summary line, and a `Current project:` block in the detail panel.

## Notes

[2026-08-18T22:52:03Z · sase-qd.2] PROPOSED FOLLOW-UP: Feature-flag lint names missing beads — `just check` `_lint-flags` fails rule 6 for coder_inherits_planner_chat (sase-nw), commit_finalizer_shared_clone_exempt (sase-pk), completion_refresh_on_update (sase-om), epic_resume_gate (sase-pa), and prettier_enabled (sase-nx). Pre-existing; this phase did not touch flags.

[2026-08-18T22:52:23Z · sase-qd.2] PROPOSED FOLLOW-UP: toobig fails on tests/_suite_gate.py — `_lint-toobig` reports 1197 lines over the 1000-line tests limit. Pre-existing; this phase did not touch that file.

[2026-08-18T22:52:48Z · sase-qd.2] Projects tab now resolves the current project off-thread, caches key/name/accent in session state, and renders a CUR column (+ plus accent name), a current:+<name>|none|… summary segment, and a Current project: detail block (via-project, via-patch, eligible, disabled, not-launchable). Filter seeding still happens once. Regenerated the four Projects PNG goldens. ruff/mypy/symvision passed; scoped selection escalated (core-identity-changed) and the full non-visual suite passed 33782. just check still dies on pre-existing _lint-flags missing beads and _lint-toobig tests/_suite_gate.py (noted as follow-ups).

[2026-08-18T22:54:51Z · sase-qd.2] Projects tab now resolves the current project off-thread, caches key/name/accent in session state, and renders a CUR column (+ plus accent name), a current:+<name>|none|… summary segment, and a Current project: detail block (via-project, via-patch, eligible, disabled, not-launchable). Filter seeding still happens once. Regenerated the four Projects PNG goldens. ruff/mypy/symvision passed; scoped selection escalated (core-identity-changed) and the full non-visual suite passed 33782. just check still dies on pre-existing _lint-flags missing beads and _lint-toobig tests/_suite_gate.py (noted as follow-ups).

## Dependencies

- **Blocks:** [sase-qd.3](sase-qd.3.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.2/README.md) | [sase-qd.2](sase-qd.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec048b1`](https://github.com/sase-org/sase/commit/ec048b168c365fe09dd068fd64c9a51e178e99ae) | feat(tui): show current project in Admin Center Projects tab | [sase-qd.2](sase-qd.2.md) | 2026-08-18 18:57:10 EDT |
