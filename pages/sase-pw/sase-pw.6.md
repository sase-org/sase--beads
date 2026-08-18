# Bead: sase-pw.6 — Statistics, inventory, Glossary, and the + picker

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.6` · **Size:** medium
**Created:** 2026-08-18 11:30:34 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

panes: seed the Statistics project filter, the Repos/Workspaces inventory filters, the Glossary project ring, and the `+` project-select cursor from the current project.

## Notes

[2026-08-18T19:05:31Z · sase-pw.6] PROPOSED FOLLOW-UP: just check symvision gate is red due to stale --epic-symbol "sase-pw.4(...)" entries in the Justfile — corroborating the 2026-08-18T17:33/17:49/18:00 notes on this epic about sase-pw.2 symbols going stale, now recurring for sase-pw.4. sase-pw.4 closed (2026-08-18T18:46:44Z) with a note claiming its own tree re-keyed/cleared these, but that fix is not yet merged into master/this workspace: symvision --epic-symbol "sase-pw.4(CurrentProject)", "sase-pw.4(peek_current_project_change_token)", "sase-pw.4(project_accent)", "sase-pw.4(project_accent_map)", "sase-pw.4(resolve_current_project)" all error with "bead sase-pw.4 is closed. Remove this stale --epic-symbol entry". Verified CurrentProject and resolve_current_project are now genuinely consumed by non-test code in this (sase-pw.6) branch (statistics_pane.py, projects_pane.py, glossary_panel_load.py, project_select_modal.py), so those two entries can simply be removed once merged; peek_current_project_change_token/project_accent/project_accent_map remain unconsumed here and need re-keying to a still-open bead (e.g. sase-pw.8 per sase-pw.4 close note, or the parent epic) when this lands. Verified via fmt+ruff+mypy+targeted pytest runs instead since just check bails at this pre-existing, unrelated gate before reaching tests.

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.3](sase-pw.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.6/README.md) | [sase-pw.6](sase-pw.6.md) | 0 |
