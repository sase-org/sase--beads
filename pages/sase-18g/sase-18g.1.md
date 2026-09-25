# Bead: sase-18g.1 — Pure xprompt preview fitting and header settings

[Bead Pages](../README.md) / [sase-18g](README.md) / sase-18g.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rk.md) · **Assignee:** `sase-18g.1` · **Size:** medium
**Created:** 2026-09-24 17:41:29 EDT · **Closed:** 2026-09-24 19:34:33 EDT
**Plan:** [202609/agent\_header\_xprompt\_preview.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_header_xprompt_preview.md)

## Description

preview: add a pure module that reflows the highlighted xprompt, fits it to a width and row budget behind a quote bar, and reports hidden lines; add the row-budget helper and the inert ace.agent_header.collapsed_max_share setting (schema, default config, parser, app wiring) with unit tests.

## Notes

[2026-09-24T23:34:07Z · sase-18g.1] PROPOSED FOLLOW-UP: master is red on a clean base tree independent of this phase — just check fails at mypy (agent_detail mixins, command_line/screen.py+input.py), test-waits (tests/ace/tui/command_line/test_completion_popup.py:181), toobig (command_line/screen.py 1979 lines, widgets/decks/panel.py 1067 lines) and symvision (49 unused-public findings, mostly command_line/*); 44 scoped tests fail identically with and without this diff (kill_and_edit_prompt_name, agent_prompt_panel_monitor/semantic/xprompts, config_schema command_line keymap, app_import_budget, visual-fixture host paths, ...). Reproduced by stashing this phase; see existing beads sase-183, sase-188, sase-16m, sase-175, sase-176 for partial overlap.

[2026-09-24T23:34:33Z · sase-18g.1] Added agent_header_preview.py (fit_xprompt_preview, XpromptPreviewFit, preview_row_budget) and agent_header_settings.py (inert ace.agent_header.collapsed_max_share; schema, default_config.yml, _state_init_late parse, startup annotation). 73 preview tests + 21 settings/schema-parity tests pass; ruff, fmt, keep-sorted, flags, pyscripts, changelog, validate pass; my files add no mypy/toobig findings. Four Justfile --epic-symbol entries keyed to sase-18g for sase-18g.3 to remove. Remaining just check failures (mypy, test-waits, toobig, symvision, 44 tests) reproduce identically on the clean base tree and are recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-18g.3](sase-18g.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18g.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.1/README.md) | [sase-18g.1](sase-18g.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`67b1b6c`](https://github.com/sase-org/sase/commit/67b1b6c5a88fd973812adc2f537038a535d16715) | feat(ace): add pure xprompt header preview fitting and header settings (sase-18g.1) | [sase-18g.1](sase-18g.1.md) | 2026-09-24 19:35:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18g.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-18g.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18g.land/README.md

<!-- sase:referenced-by:end -->
