# Bead: sase-1ig.8 — The live \`just install-dev\`

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.8` · **Size:** medium
**Created:** 2026-10-08 18:23:31 EDT · **Closed:** 2026-10-09 00:59:48 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

engine-dev: wire dev mode through the pipeline (dev swap argv and overrides, core plus LSP re-apply via `rust-dev-install-uv-tool`, stamp check, dev verification including `sase update -n -j` agreement, repeat-run no-op) and add the `install-dev` recipe.

## Notes

[2026-10-09T04:14:09Z · sase-1ig.8] Manual live smoke (agent-safe subset): `just install-dev -n` and `SASE_AGENT=1 just install-dev -n` both exit 2 through the recipe with the agent-guard refusal naming `just install-venv` and the bypass; `just install-dev --help` renders the dev epilog. A real global install plus `sase update -n` must be run by the human from the durable checkout (agents must not run global installs).

[2026-10-09T04:14:17Z · sase-1ig.8] PROPOSED FOLLOW-UP: `sase update -n -j` reports mode mixed (not dev) when the dev install carries a PyPI-sourced plugin, but install-dev agreement requires mode dev — decide whether mixed-with-PyPI-plugins should agree

[2026-10-09T04:59:39Z · sase-1ig.8--1] PROPOSED FOLLOW-UP: just check 3 KNOWN failures reproduce identically on clean base tree (stashed phase changes, same 3 tests fail): test_macro_string_literals_avoid_xprompt_terms (tests/test_plugin_commands_mount.py "xprompt" literal), test_directive_completion_includes_representative_descriptions (%auto description drift), test_tab_through_every_subcommand_reaches_the_last_with_a_highlight (bead Tab index 17 vs 33-1); triage witness 012177c3b06f977c05c34805ad32f991, no owner; unrelated to install-dev phase files

[2026-10-09T04:59:48Z · sase-1ig.8--1] install-dev phase verified: 77 phase tests pass (test_run_dev, test_run_pypi, test_justfile_sase_core_dir); epic-symbols empty; full just check triaged no_new_failures with 3 KNOWN failures that reproduce identically on clean base tree (stashed rerun, same 3 tests fail) and are unrelated to phase files

## Dependencies

- **Blocks:** [sase-1ig.10](sase-1ig.10.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.11](sase-1ig.11.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1ig.4](sase-1ig.4.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1ig.5](sase-1ig.5.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1ig.6](sase-1ig.6.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.9](sase-1ig.9.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.8.md) | [sase-1ig.8](sase-1ig.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`33bc9ca`](https://github.com/sase-org/sase/commit/33bc9ca36c911988c621fcb8a1721ef5aeab07f0) | feat(install): wire dev mode through pipeline and add install-dev recipe (sase-1ig.8) | [sase-1ig.8](sase-1ig.8.md) | 2026-10-09 01:01:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.4--1][1] | check if mode_switch belongs to sibling bead | 1 |
| read-by | [agent:sase-1ig.8--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.8.md

<!-- sase:referenced-by:end -->
