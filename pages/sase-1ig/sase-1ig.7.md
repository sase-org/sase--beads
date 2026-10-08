# Bead: sase-1ig.7 — Rename install to install-venv in the plugin repos

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.7` · **Size:** medium
**Created:** 2026-10-08 18:23:30 EDT · **Closed:** 2026-10-08 19:36:42 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

plugin-repos: in sase-github, sase-telegram, sase-research-artifacts, and sase-listen, rename the venv recipe to a grouped, documented `install-venv`, keep `install` as a private forwarding alias that names the new recipe, and migrate each repo's CI, tests, and docs.

## Notes

[2026-10-08T23:36:26Z · sase-1ig.7] PROPOSED FOLLOW-UP: Remove the private [private] install forwarding alias from sase-github, sase-telegram, sase-research-artifacts, and sase-listen Justfiles after one release

[2026-10-08T23:36:31Z · sase-1ig.7] PROPOSED FOLLOW-UP: Full per-repo check lanes (sase-telegram/research need coordinated .sase-deps sase+sase-core checkouts and maturin release builds) only run in CI; here verified via just --list/--dry-run plus contract tests

[2026-10-08T23:36:42Z · sase-1ig.7] Renamed install to group('install') install-venv with one-line doc in sase-github, sase-telegram, sase-research-artifacts, sase-listen Justfiles; kept [private] install alias printing 'just install is now just install-venv' to stderr then forwarding; migrated each repo's CI run steps, README/AGENTS/CLAUDE/CONTRIBUTING docs, and contract tests; install-source-sase untouched. Verified: just --list shows clean [install] group with alias hidden, --dry-run install shows notice+forward and install-venv bodies intact in all four repos; tests pass (github 3, telegram 16, research 9), ruff check/format clean, all 16 workflow YAMLs parse. Full venv-backed check lanes are CI-only (telegram/research need coordinated .sase-deps checkouts absent here; same import failures reproduce on base).

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.9](sase-1ig.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.7/README.md) | [sase-1ig.7](sase-1ig.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-github | [`sase-github@69e1b0a`](https://github.com/sase-org/sase-github/commit/69e1b0a9e83f4a7d27fdcbe0ddac74a2e2570e32) | feat(install): rename venv recipe to install-venv with private install alias | [sase-1ig.7](sase-1ig.7.md) | 2026-10-08 19:38:26 EDT |
| sase-listen | [`sase-listen@1b82d27`](https://github.com/sase-org/sase-listen/commit/1b82d27f3eba92b3c77b87d6a60b90884bd69577) | feat(install): rename venv recipe to install-venv with private install alias | [sase-1ig.7](sase-1ig.7.md) | 2026-10-08 19:42:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ig.7][1] | declaration recovery: need bead status to choose keep vs close | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.7/README.md

<!-- sase:referenced-by:end -->
