# Bead: sase-1if.1 — Plugin command contract, discovery, and dispatch

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.1` · **Size:** medium
**Created:** 2026-10-08 15:26:22 EDT · **Closed:** 2026-10-08 16:42:08 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

mount: add the generic sase_commands contract, metadata-only discovery and validation, the pre-argparse dispatch fast path, helpful misses, the shared command chip, a fake-distribution test harness, and the hermetic test guard.

## Notes

[2026-10-08T20:41:58Z · sase-1if.1] PROPOSED FOLLOW-UP: just check lint(symvision) reports 49 unused-public symbols that reproduce identically on the clean base tree (verified via stash + symbol-set diff; zero are plugin_commands) — needs a baseline/bulk triage pass, no owner found

[2026-10-08T20:42:08Z · sase-1if.1] mount done and verified: new sase.plugin_commands package (scan/registry/adapter/dispatch/chip/hints) wired after run fast path; dispatch/hints exit codes, sys.argv shape, SystemExit propagation, shadowed/conflict/invalid states, disable switches, and all four miss branches covered by 35 tests in tests/test_plugin_commands_mount.py with tests/_plugin_commands_fake.py harness; hermetic SASE_DISABLE_PLUGIN_COMMANDS guard in conftest; docs Command plugins section + group/disable rows + cli.md row; memory decisions:plugin-commands strand + cli_rules exemption, republished via sase memory init. sase tool run check: all fmt/lint gates pass except lint(symvision), which fails identically on the clean base tree (49 pre-existing symbols, filed as PROPOSED FOLLOW-UP); just validate blocker is only the untracked new strand awaiting host-side commit. Ran: mount suite 35 passed; narrowing+ensure-contract+leak-detector 62 passed; plugin catalog/cli suites 93 passed; print-command+bead-routing 38 passed; mypy/ruff clean.

## Dependencies

- **Blocks:** [sase-1if.3](sase-1if.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.4](sase-1if.4.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.5](sase-1if.5.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.1/README.md) | [sase-1if.1](sase-1if.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b9693bc`](https://github.com/sase-org/sase/commit/b9693bc695751cbc6ea6d0228d21e792cea7733e) | feat(plugin-commands): add sase\_commands contract, discovery, and dispatch | [sase-1if.1](sase-1if.1.md) | 2026-10-08 16:43:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.1/README.md

<!-- sase:referenced-by:end -->
