# Bead: sase-1bc.8 — The o/O layout ladder

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.8` · **Size:** medium
**Created:** 2026-09-27 10:57:12 EDT · **Closed:** 2026-09-28 15:06:03 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

layout-ladder: replace the merged boolean with a Split/Merged/All-tabs level; turn the grouping modal's layout row into a segmented control with o (next) and O (previous); add titles, info-row chip, all-tabs strip state, row tab chips, tribe-roster tab chips, and anchor-preserving transitions.

## Notes

[2026-09-28T18:13:34Z · sase-1bc.8] PROPOSED FOLLOW-UP: just validate init-memory check drifts on clean tree (sase_artifacts.md, README.md +3/-3, +2/-2); regenerate via sase init memory

[2026-09-28T18:34:57Z · sase-1bc.8] Verified: just fmt/ruff/mypy/keep-sorted/flags/symvision green; 376 focused tests green (ladder 21, grouping modal+picker, catalogs, help, tab scope/switch, fold, titles, info panel, rail, strip); 4 new PNG goldens created and test-visual green; flag-off views byte-identical. Full test-scoped lane exceeds sync limit (48% green, no failures at timeout) — handed to verify monitor; pre-existing validate memory drift recorded as follow-up.

[2026-09-28T19:05:18Z · sase-1bc.8--1] PROPOSED FOLLOW-UP: test_current_source_avoids_agent_family_identifiers fails on src/sase/agents/cli_tab.py:34 ("agent_family" key, present in HEAD, untouched by sase-1bc.8)

[2026-09-28T19:05:31Z · sase-1bc.8--1] PROPOSED FOLLOW-UP: test_default_config_matches_public_schema fails (ace.keymaps.tool_runs run_tool/stop_run unexpected; default_config.yml and schema untouched by sase-1bc.8, likely sase-1bt keymap drift)

[2026-09-28T19:05:43Z · sase-1bc.8--1] PROPOSED FOLLOW-UP: just _lint-flags rule 7 fails (closed flag bead sase-1bv still defines ace_tool_runs); no flag files touched by sase-1bc.8

[2026-09-28T19:06:03Z · sase-1bc.8--1] Verified: fmt/ruff/mypy/keep-sorted/symvision green; owned test-scoped failure (merged fold-scope) fixed via ladder-state mirror in display test fake, 77 focused tests green (display focus/display/sticky, group focus, fold intent, layout ladder, grouping modal); 4 ladder PNG goldens green; flag-off views byte-identical. Remaining test-scoped failures (terminology cli_tab, config-schema tool_runs) plus _lint-flags sase-1bv are pre-existing on files untouched by this bead, recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-1bc.12](sase-1bc.12.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bc.7](sase-1bc.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.8.md) | [sase-1bc.8](sase-1bc.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6205ae3`](https://github.com/sase-org/sase/commit/6205ae345ea619d2e7b1789e55d890da985e6fc7) | feat(ace): complete the Agents o/O layout ladder (sase-1bc.8) | [sase-1bc.8](sase-1bc.8.md) | 2026-09-28 15:19:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.8--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.8.md

<!-- sase:referenced-by:end -->
