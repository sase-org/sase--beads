# Bead: sase-1jx.13.6.3 — Integrate wizard outcomes with the real Projects pane

[Bead Pages](../README.md) / [sase-1jx.13.6](sase-1jx.13.6.md) / sase-1jx.13.6.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.13.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.13.land.md) · **Assignee:** `sase-1jx.13.6.3` · **Size:** medium
**Created:** 2026-10-12 19:35:35 EDT
**Plan:** [202610/new\_project\_wizard\_final\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_final_repairs.md)

## Description

projects-pane: find the Projects pane through the screen stack, stop the double filter pass, fix show-project status copy, make ? help and Show new project keyboard-usable, fix the stale create docstring, restore lost tests, make the Failed t test hermetic, and capture a narrow hints golden that shows the hints.

## Notes

[2026-10-13T00:14:13Z · sase-1jx.13.6.3] PROPOSED FOLLOW-UP: 80x24 Admin Center Projects golden still clips the list, detail, and #projects-hints under chrome — add an 80-col capture at the smallest height where hints render rather than redesigning Admin Center.

[2026-10-13T00:44:44Z · sase-1jx.13.6.3] PROPOSED FOLLOW-UP: test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data expects Project: sase vs tmp — reproduces identically on clean master (stash -u); tracked by sase-1k4

[2026-10-13T00:44:50Z · sase-1jx.13.6.3] PROPOSED FOLLOW-UP: TUI import budget 3517 vs 3513 cap is +0 vs origin/master (both 3517) so the cap is already stale on master — tracked by sase-1ic / sase-13p

[2026-10-13T00:44:55Z · sase-1jx.13.6.3] PROPOSED FOLLOW-UP: agent-display meta Project: my_project vs fake and stale path-label exemption for revive_agent_modal.py both reproduce on clean master — sase-1k4 and sase-1jx.13 notes

## Dependencies

- **Blocks:** [sase-1jx.13.6.4](sase-1jx.13.6.4.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.6.3/README.md) | [sase-1jx.13.6.3](sase-1jx.13.6.3.md) | 0 |
