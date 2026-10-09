# Bead: sase-1if.3 — Plugin commands in root help and sase doctor

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.3` · **Size:** small
**Created:** 2026-10-08 15:26:24 EDT · **Closed:** 2026-10-08 18:00:35 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

help-doctor: list plugin commands in sase -H (and sase -h per decision) with provenance and problem states, and add the plugins.commands doctor check.

## Notes

[2026-10-08T22:00:22Z · sase-1if.3] PROPOSED FOLLOW-UP: just check lint(symvision) reports 49 unused-public symbols, byte-identical on the clean base tree (stash + symbol-set diff); zero touch plugin_commands — needs the baseline/bulk triage already tracked by sase-1i5.9.1.2.1.5

[2026-10-08T22:00:35Z · sase-1if.3] help-doctor done and verified: Plugin commands group in sase -h (mounted only, with dim dist provenance) and footer in sase -H (chip+summary+dist/version, WARN rows with sase-doctor pointer, management closing line), plain and colored forms strip-identical; plugins.commands doctor check (OK/WARN/ERROR taxonomy with repair next-steps) plus deep plugins.commands-parsers variant that builds each parser; Justfile hygiene: dropped now-consumed resolve_command_summary entry, re-keyed rich_command_chip/format_command_chip_with_state to sase-1if.5; epic-symbols clean for this phase. Tests: 17 new in tests/test_plugin_commands_help_doctor.py pass, neighbors (mount/narrowing/root-help/doctor-plugins) green. sase tool run check: all fmt/lint gates pass except lint(symvision) 49 unused-public symbols proven byte-identical on the clean base (stash+diff) and filed as PROPOSED FOLLOW-UP citing tracker sase-1i5.9.1.2.1.5.

## Dependencies

- **Depends on:** [sase-1if.1](sase-1if.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.10](sase-1if.10.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.3/README.md) | [sase-1if.3](sase-1if.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`991c8b4`](https://github.com/sase-org/sase/commit/991c8b4dd7c74b7b4c044c53aaffc6d23a169642) | feat(plugin-commands): list plugin commands in root help and sase doctor | [sase-1if.3](sase-1if.3.md) | 2026-10-08 18:02:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.1][1] | Check phase is open before keying epic-symbol rows to it | 1 |
| read-by | [agent:sase-1if.3][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.3/README.md

<!-- sase:referenced-by:end -->
