# Bead: sase-17x.1 — Output color contract

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.1` · **Size:** medium
**Created:** 2026-09-24 11:29:18 EDT · **Closed:** 2026-09-24 11:47:42 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

color-contract: add one shared color resolver (NO_COLOR, then FORCE_COLOR/CLICOLOR_FORCE, then isatty). Adopt it in the bead renderers and every other stdout color branch, so a piped `sase` child renders in color the way a terminal does.

## Notes

[2026-09-24T15:47:25Z · sase-17x.1] PROPOSED FOLLOW-UP: symvision gate fails on pristine tree (private _failure_count imports in doctor/checks_providers.py and llm_provider/usage/_presentation_shared.py); verified pre-existing via stash, unrelated to color-contract

[2026-09-24T15:47:42Z · sase-17x.1] Shared sase.core.term_color.should_colorize (NO_COLOR, then FORCE_COLOR/CLICOLOR_FORCE, then isatty) adopted in bead renderers via resolve_color plus print_command, parser_root_help, project_handler_render, usage_handler, prompt cli_search, init preview_console, fakey help; Rich-auto branches verified native FORCE_COLOR handling. Verified: 21 new tests pass, 230 related existing tests pass, ruff+mypy pass; symvision red is pre-existing (proven on pristine tree) and filed as follow-up.

## Dependencies

- **Blocks:** [sase-17x.12](sase-17x.12.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.1/README.md) | [sase-17x.1](sase-17x.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a79551`](https://github.com/sase-org/sase/commit/5a7955161e960662c41fa496ab5ef699941e3cb1) | feat(cli): add shared stdout color contract honoring FORCE\_COLOR | [sase-17x.1](sase-17x.1.md) | 2026-09-24 11:48:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.1/README.md

<!-- sase:referenced-by:end -->
