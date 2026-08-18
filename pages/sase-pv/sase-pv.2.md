# Bead: sase-pv.2 — Declare the \`flag\` task type in project config

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.2` · **Size:** small
**Created:** 2026-08-18 11:26:03 EDT · **Closed:** 2026-08-18 12:55:42 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

type: add the seven-field `flag` task-type spec to `bead.task_types` in this repo's project config, pin its glyph and accent, and refresh the committed catalog snapshot.

## Notes

[2026-08-18T16:55:11Z · sase-pv.2] PROPOSED FOLLOW-UP: Pre-existing mypy error in src/sase/glossary/render.py:74 — Console(color_system=console.color_system) is str | None vs Literal[auto/standard/256/truecolor/windows] | None. I did not touch this file (commit 88fa6e949); just check fails on it.

[2026-08-18T16:55:27Z · sase-pv.2] PROPOSED FOLLOW-UP: Pre-existing symvision unused publics project_accent and project_accent_map in src/sase/ace/tui/project_styles.py. I did not touch that file; just _lint-symvision fails on them.

[2026-08-18T16:55:42Z · sase-pv.2] Declared the seven-field project-local flag task type in sase/sase.yml (glyph ⚑, accent #FF875F, agent_creatable false). sase bead task-type show flag assembles the spec; the committed sase/task_types.json snapshot has source=project package=sase and does not list flag in the agent-creatable memory note. resolve_created_task_type now surfaces when_to_use (sase flag new) instead of the plugin-reserved message. Quoted YAML On/Off labels so they are not parsed as booleans. No leftover --epic-symbol entries. Full escalated pytest: 33434 passed, 12 skipped. just check still fails on unrelated pre-existing mypy (glossary/render.py) and symvision (project_styles.py) — recorded as PROPOSED FOLLOW-UP.

[2026-08-18T16:56:43Z · sase-pv.2] Declared the seven-field project-local flag task type in sase/sase.yml (glyph ⚑, accent #FF875F, agent_creatable false). sase bead task-type show flag assembles the spec; committed sase/task_types.json has source=project package=sase and does not list flag in the agent-creatable memory note. resolve_created_task_type surfaces when_to_use (sase flag new) instead of the plugin-reserved message. Quoted YAML On/Off labels so they are not parsed as booleans. No leftover --epic-symbol entries. Full escalated pytest: 33434 passed, 12 skipped.

## Dependencies

- **Depends on:** [sase-pv.1](sase-pv.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.3](sase-pv.3.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.4](sase-pv.4.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.2/README.md) | [sase-pv.2](sase-pv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`88d2a15`](https://github.com/sase-org/sase/commit/88d2a1582a1d4a94f75e55fc61c230f049b75691) | feat(task-types): declare the project-local flag task type | [sase-pv.2](sase-pv.2.md) | 2026-08-18 12:57:33 EDT |
