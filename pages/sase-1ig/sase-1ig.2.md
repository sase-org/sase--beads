# Bead: sase-1ig.2 — Installer engine foundation and dry-run planning

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.2` · **Size:** medium
**Created:** 2026-10-08 18:23:29 EDT · **Closed:** 2026-10-08 18:57:29 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

engine-core: create the stdlib-only `tools/sase_install` engine with its CLI, agent and durable-source guards, receipt/env snapshot, plugin source policy, consequential-change classification, argv/overrides parity with `sase.uv_tool`, the plan panel and JSON renderers, and the confirmation policy, with `-n` working for both modes.

## Notes

[2026-10-08T22:57:20Z · sase-1ig.2] PROPOSED FOLLOW-UP: bugyi-chops 0.9.0 is now published on PyPI, so the plan example of an unpublished plugin staying editable no longer triggers live; later phases should confirm the fallback still has a live unpublished case

[2026-10-08T22:57:29Z · sase-1ig.2] engine-core done: tools/sase_install + 5 stdlib-only helpers with -n working for pypi/dev; guard matrix, receipt/swap/overrides/ephemeral parity vs sase.uv_tool, plugin policy, consequential classification, non-TTY policy, fixed-width panels + golden flip snapshot, 14-key JSON. Verified: 80 passed (tests/sase_install + typecheck-tool tests), ruff src+tests clean, mypy extensionless incl helpers clean (66 files), pyscripts gate clean, epic-symbols empty, live smoke of pypi -n against real tool env OK

[2026-10-08T23:41:14Z · sase-1ig.2--1] Post-close fmt fix: monitored just check failed only on ruff format (8 test/helper files); ran ruff format so `ruff format --check src/ tests/` is clean. Full just check re-run handed to a verify monitor.

## Dependencies

- **Blocks:** [sase-1ig.5](sase-1ig.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.6](sase-1ig.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.2.md) | [sase-1ig.2](sase-1ig.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0b6e2e`](https://github.com/sase-org/sase/commit/d0b6e2e99d180dc132ab735967565cdd1c62e81b) | feat(install): add stdlib-only sase\_install engine with dry-run planning | [sase-1ig.2](sase-1ig.2.md) | 2026-10-08 20:44:30 EDT |
