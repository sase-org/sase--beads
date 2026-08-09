# Bead: sase-ij.2 — Build the window ratchet tool

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.2` · **Size:** medium
**Created:** 2026-08-09 15:18:09 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

ratchet-tool: add a stdlib-only tools/ratchet_core_window that selects the newest fully published stable sase-core-rs from PyPI, rewrites only that requirement in pyproject.toml through one tested ceiling-policy function, refreshes uv.lock with a bounded diff guard, and supports --check/--report-only with idempotence and downgrade refusal.

## Dependencies

- **Depends on:** [sase-ij.1](sase-ij.1.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-ij.4](sase-ij.4.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.2/README.md) | [sase-ij.2](sase-ij.2.md) | 0 |
