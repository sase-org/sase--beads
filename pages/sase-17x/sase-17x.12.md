# Bead: sase-17x.12 — Flip \`:\` and \`;\`, remove the flag, and land

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.12` · **Size:** medium
**Created:** 2026-09-24 11:29:32 EDT · **Closed:** 2026-09-24 19:04:19 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

flip-and-land: bind `:` to the Command Line and `;` to the palette only. Add the palette-side hop key, the fallback row and the one-time tip. Update every help, onboarding, docs and test touchpoint, delete the flag's Off branch, close the flag bead, and regenerate the PNG goldens.

## Notes

[2026-09-24T23:03:10Z · sase-17x.12] PROPOSED FOLLOW-UP: just check blocked by 15 pre-existing mypy errors on clean tree (agent_detail mixins lack attrs; command_line LineContext vs dict in input.py:159 and screen.py:1368-1387)

[2026-09-24T23:03:37Z · sase-17x.12] PROPOSED FOLLOW-UP: symvision flags _dispatch_preview_source_summary private-misuse and toobig flags screen.py/panel.py on clean tree; both pre-existing, unrelated to colon flip

[2026-09-24T23:03:49Z · sase-17x.12] PROPOSED FOLLOW-UP: test_agents_help_describes_zoom_and_isolation_and_capital_h_collapsing and test_all_tab_help_guides_show_forward_jump fail on clean tree (missing Z zoom row)

[2026-09-24T23:04:19Z · sase-17x.12] Flip landed: default_config.yml binds open_command_line to colon and open_command_palette to semicolon; ace_command_line registry entry and Off-branch gate deleted (flag.py removed; palette row unconditional); palette : -hop on empty filter plus no-match fallback row prefilling the Command Line (CommandPaletteResult.command_line_prefill, dismiss handler sets session draft); one-time palette-moved tip with sase_home marker on first open; help rows added; docs/ace.md Command Line section plus palette/custom-mode updates; flag schema resynced. Verified: focused suites pass (keymaps/catalog/palette modal/wiring/e2e/command_line panel, transcript, run-policies, popup, extras, quickstart, flags, procs; 16 wiring incl new hop+prefill e2e, 41 modal incl 3 new flip tests, tip marker test); goldens updated+inspected (onboarding x2, help keymaps, fleet empty, changespecs x2) and 4 missing run-policies goldens created+inspected (declined/denied/foreground/help); live TUI walkthrough on checkout build (: opens panel, signature/diagnostics, proc submit block, hide). just check blocked only by pre-existing clean-tree failures (15 mypy, symvision, toobig; recorded as follow-ups). sase-181 flag bead left open for land agent (flags lint shows expected landing warning).

## Dependencies

- **Depends on:** [sase-17x.1](sase-17x.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.10](sase-17x.10.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.11](sase-17x.11.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.3](sase-17x.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.12/README.md) | [sase-17x.12](sase-17x.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c83e3bd`](https://github.com/sase-org/sase/commit/c83e3bd916be309d8ffc9e4bc0b258131ea1d253) | feat(ace): flip command-line and palette keys to colon and semicolon | [sase-17x.12](sase-17x.12.md) | 2026-09-24 19:06:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.1][1] | Determine whether remaining phase 17x.12 will consume symvision-flagged command-line symbols | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.1/README.md

<!-- sase:referenced-by:end -->
