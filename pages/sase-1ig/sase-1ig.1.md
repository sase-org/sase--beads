# Bead: sase-1ig.1 — Rename the venv recipes to install-venv and park bare install

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.1` · **Size:** medium
**Created:** 2026-10-08 18:23:28 EDT · **Closed:** 2026-10-08 18:52:20 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

venv-rename: consolidate the three copy-pasted venv recipes into `_install-venv EXTRAS`, expose them as the `[install]` group's `install-venv*`, park bare `install` behind a loud exit-2 placeholder, and migrate CI, the tool catalog, tests, docs, tools/ strings, the sase_monitor skill source, and the lint_and_test/symvision memory notes.

## Notes

[2026-10-08T22:52:07Z · sase-1ig.1] PROPOSED FOLLOW-UP: just check lint(symvision) reports ~48 NEW unused-public symbols; reproduces identically on the clean base tree (just _lint-symvision exit 1, ~51 symbols) and is tracked by sase-1i5.9.1.2.1.5

[2026-10-08T22:52:20Z · sase-1ig.1] venv-rename done: _install-venv EXTRAS + install-venv/install-venv-visual/install-venv-terminal-smoke in [install] group, bare install placeholder exit 2, CI/tool-catalog/tests/tools-docs/skill/memory migrated; verified just --list group, just --dry-run install-venv-visual wheel branch, bare install exit 2 text, 98+90 targeted tests pass, just fmt clean; sase tool run check red only on pre-existing symvision unused-public backlog reproduced on clean base (tracked by sase-1i5.9.1.2.1.5, recorded as PROPOSED FOLLOW-UP); no epic-symbols

## Dependencies

- **Blocks:** [sase-1ig.3](sase-1ig.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.4](sase-1ig.4.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.5](sase-1ig.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.7](sase-1ig.7.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.1/README.md) | [sase-1ig.1](sase-1ig.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f240b3`](https://github.com/sase-org/sase/commit/6f240b3c96480ffa52b07630f24957d3b7c8347d) | feat(install): rename venv recipes to install-venv and park bare install | [sase-1ig.1](sase-1ig.1.md) | 2026-10-08 18:54:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.1/README.md

<!-- sase:referenced-by:end -->
