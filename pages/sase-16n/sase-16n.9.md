# Bead: sase-16n.9 — sase-telegram and sase-github tag adoption

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.9` · **Size:** small
**Created:** 2026-09-22 18:48:54 EDT · **Closed:** 2026-09-23 07:40:00 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

plugins: Telegram project-context capture and copy-text buttons use tags, its inbound docs and tests are updated, and sase-github docs present +<project> as the default.

## Notes

[2026-09-23T11:38:42Z · sase-16n.9] PROPOSED FOLLOW-UP: sase-telegram just check has 2 pre-existing failures on clean tree — test_telegram_submits_a_shell_backed_gate (gate-shell row validation drift vs sase core) and test_host_plugin_and_native_changes_each_new_generation (receiver generation fingerprint); both fail with my changes stashed too

[2026-09-23T11:39:19Z · sase-16n.9] PROPOSED FOLLOW-UP: sase-github just check cannot set up venv from PyPI (sase>=0.17.0 needs sase-core-rs<0.33, only >=0.34.23 available) — needs SASE_PYTHON_PATH/SASE_RUST_CORE_PATH local-source env; docs-only change here is unaffected

[2026-09-23T11:40:00Z · sase-16n.9] plugins phase done: telegram reads (+Sase) via effective_vcs_workflow_tag with legacy fallback, Fork/Wait/Retry copy text renders tag-form through the humanizer, inbound+github docs present +project as default; verified ruff+mypy clean, 329/329 in test_inbound+test_formatting incl 4 new tag tests, 673 passed full telegram suite except 2 pre-existing clean-tree failures (noted as follow-ups)

## Dependencies

- **Blocks:** [sase-16n.10](sase-16n.10.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.6](sase-16n.6.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.9/README.md) | [sase-16n.9](sase-16n.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-github | [`sase-github@204ffd0`](https://github.com/sase-org/sase-github/commit/204ffd0737e305b3c5ea6f941d9bfe442e588feb) | docs(xprompts): present +\<project\> as the default GitHub project spelling | [sase-16n.9](sase-16n.9.md) | 2026-09-23 07:41:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.9][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.9/README.md

<!-- sase:referenced-by:end -->
