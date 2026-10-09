# Bead: sase-1if.5 — Command-aware plugin install, update, and uninstall

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.5` · **Size:** medium
**Created:** 2026-10-08 15:26:25 EDT · **Closed:** 2026-10-09 01:58:22 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

lifecycle: fix the inventory groups, carry command names in the installed index, diff the command set around every plugin mutation, refresh completion in a fresh child process, and announce added or removed commands in CLI results and JSON.

## Notes

[2026-10-09T04:28:23Z · sase-1if.5] PROPOSED FOLLOW-UP: test_macro_string_literals_avoid_xprompt_terms fails on clean base (tests/test_plugin_commands_mount.py:124 assert "xprompt" in reserved lacks an allowlist row; file and pairs table untouched by this phase)

[2026-10-09T05:58:22Z · sase-1if.5--1] Command-aware plugin lifecycle verified: 16 new tests in tests/test_plugin_lifecycle.py pass; broad plugin suites green (233 passed: ops install/update/uninstall/resolve, CLI install/update/uninstall, catalog, required-gate, commands-mount, doctor plugin checks); extra suites green (72 catalog/renderables/qualified-id/list/show; 16 version-inventory-plugins + update-status-compute). Full 'sase tool run check' timed out on 60m budget during Rust/LSP rebuilds (62m release build), not on test failures; fmt (python/markdown/docs) passed in retained log. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1if.1](sase-1if.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1if.4](sase-1if.4.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.6](sase-1if.6.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1if.5.md) | [sase-1if.5](sase-1if.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3b3d876`](https://github.com/sase-org/sase/commit/3b3d8769114298c58d8f136c55baaab93a367514) | feat(plugins): command-aware plugin install, update, and uninstall lifecycle | [sase-1if.5](sase-1if.5.md) | 2026-10-09 03:17:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.5--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1if.5.md

<!-- sase:referenced-by:end -->
