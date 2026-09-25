# Bead: sase-17x.13.4 — Apply the ace.keymaps.command\_line scope

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.4` · **Size:** medium
**Created:** 2026-09-24 20:28:44 EDT · **Closed:** 2026-09-24 23:39:04 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

keymap-config: build the panel's bindings and input routing from `CommandLineKeymaps`, add the Block-nav actions to the scope, and render hints from live key names. Update the schema, the docs and the onboarding touchpoints.

## Notes

[2026-09-25T03:17:41Z · sase-17x.13.4] PROPOSED FOLLOW-UP: panel-to-palette hop wedges Pilot press (animator never idles after dismiss+push); reproduces on clean base tree via press semicolon with panel open, while direct hop_to_palette() completes and opens CommandPaletteModal

[2026-09-25T03:37:14Z · sase-17x.13.4] PROPOSED FOLLOW-UP: just check stays red on unrelated gates with this phase applied: mypy flags tools/sase_core_wheel_cache (contextmanager/Iterator, missing annotation) and symvision flags stale sase-18i --epic-symbol entries in the Justfile; neither file is touched by this phase

[2026-09-25T03:39:04Z · sase-17x.13.4] keymap-config done: 15 block_* actions added to CommandLineKeymaps with defaults+twins; screen BINDINGS built from registry via build_command_line_bindings (unbound skipped); input/screen route history/hop/Block-nav through live scope; hints rendered from key_display_name with unbound omitted; schema+docs+onboarding in sync; configuration.md prefix fixed to B. Verified: 90 focused tests pass (7 new in test_keymap_config.py incl. mounted override+unbound pilots), 193 command_line/scope/onboarding and 129 keymaps/registry/help tests pass; fmt/ruff/keep-sorted/mypy-src clean. No epic-symbols. Known pre-existing issues filed as PROPOSED FOLLOW-UP notes: panel-to-palette hop wedges Pilot press (reproduces on base), tools mypy + symvision sase-18i entries keep just check red. PNG goldens showing hints/onboarding rows intentionally left for goldens-perf.

## Dependencies

- **Depends on:** [sase-17x.13.3](sase-17x.13.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.13.7](sase-17x.13.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.4/README.md) | [sase-17x.13.4](sase-17x.13.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bde335d`](https://github.com/sase-org/sase/commit/bde335de55acb2d17ce120213046d2f26fd33e19) | feat(command-line): apply the ace.keymaps.command\_line scope | [sase-17x.13.4](sase-17x.13.4.md) | 2026-09-24 23:41:09 EDT |
