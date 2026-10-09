# Bead: sase-1ig.5 — Execution pipeline and the live \`just install\`

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.5` · **Size:** medium
**Created:** 2026-10-08 18:23:30 EDT · **Closed:** 2026-10-08 22:31:16 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

engine-pypi: build the shared pipeline (progress renderer, log, code-swap lock, backup and restore command, uv swap, verification, scheduler restart, summary) and ship PyPI mode end to end by replacing the bare `install` placeholder.

## Notes

[2026-10-09T00:54:19Z · sase-1ig.5] uv --force --reinstall does NOT preserve the tool interpreter (3.13 env came back 3.14.7), so the swap passes the existing envs own python via --python unless the user asked with --python

[2026-10-09T02:31:16Z · sase-1ig.5] engine-pypi live: new tools/_sase_install_run.py pipeline (log, code-swap lock with 120s retry, backup+restore command, uv swap, verify, scheduler restart, summary), progress/summary UI in _sase_install_ui.py, PyPI wiring in tools/sase_install, live just install recipe (uv-run flags verified, python -I -S isolation). Verified: 102 tests in tests/sase_install incl 19 new hermetic test_run_pypi tests green, 19 justfile tests green, 262 neighbor tests green, full repo mypy + extensionless-tools mypy + pyscripts clean, governed check run 9e782ac6 all 15 lint/validation stages green with the full-suite stage still running under machine load at close. Measured: uv --force --reinstall resets the tool interpreter, so the swap pins the existing env python via --python.

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1ig.2](sase-1ig.2.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.8](sase-1ig.8.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.5/README.md) | [sase-1ig.5](sase-1ig.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`10f5e21`](https://github.com/sase-org/sase/commit/10f5e2169fc60e9c1c7b9ea04ca1bb2bf05525d1) | feat(install): add shared PyPI execution pipeline with logging, locking, and verification | [sase-1ig.5](sase-1ig.5.md) | 2026-10-08 23:28:19 EDT |
