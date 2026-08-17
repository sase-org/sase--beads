# Bead: sase-op.3 — sase glossary group with list and show

[Bead Pages](../README.md) / [sase-op](README.md) / sase-op.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.050](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.050.md) · **Assignee:** `sase-op.3` · **Size:** medium
**Created:** 2026-08-17 12:03:31 EDT · **Closed:** 2026-08-17 13:59:42 EDT
**Plan:** [202608/glossary\_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_command.md)

## Description

cli: register the `sase glossary` command group with project selection, the filtered multi-format `list` subcommand, and the recursive `show` subcommand with its provenance-annotated rendering.

## Notes

[2026-08-17T17:59:42Z · sase-op.3] Implemented sase glossary command group: cli_common (project resolution + errors), cli_list, cli_show, render, parser_glossary, glossary_handler, wired into parser.py/parser_full_registrars.py/entry.py, plus completion spec regen. Verified: 26 targeted pytest tests pass, ruff clean, mypy clean, symvision clean, full parallel suite (just test) 32460 passed/13 skipped/0 failed in ~18min, epic-symbols check shows no remaining sase-op.3 entries (re-keyed 2 to parent epic sase-op, 3 resolved).

## Dependencies

- **Depends on:** [sase-op.1](sase-op.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-op.4](sase-op.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-op.6](sase-op.6.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-op.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-op.3/README.md) | [sase-op.3](sase-op.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f6d757e`](https://github.com/sase-org/sase/commit/f6d757e2c96a7865d7958ad2b6d8bcc4a0abda4f) | feat(glossary): add glossary command group with list and show | [sase-op.3](sase-op.3.md) | 2026-08-17 14:00:52 EDT |
