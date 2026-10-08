# Bead: sase-1ig.3 — Context-aware reinstall remedies in runtime code

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.3` · **Size:** small
**Created:** 2026-10-08 18:23:29 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

remedies: add one install-context helper that picks `sase update`, `just install-dev`, or `just install-venv` and route every src/ reinstall hint (core/rust.py, query facades, doctor, completion finalizer) through it; doctor's import-root-drift warning stops suggesting a global reinstall.

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.3.md) | [sase-1ig.3](sase-1ig.3.md) | 0 |
