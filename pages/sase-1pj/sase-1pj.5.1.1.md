# Bead: sase-1pj.5.1.1 — Define staged monitor and ToolRun reservation contracts

[Bead Pages](../README.md) / [sase-1pj.5.1](sase-1pj.5.1.md) / sase-1pj.5.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) · **Assignee:** `sase-1pj.5.1.1` · **Size:** medium
**Created:** 2026-10-29 14:48:36 EDT
**Plan:** [202610/monitor\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md)

## Description

contracts: implement Rust-owned staged monitor payload validation, staged-owner liveness and self-wait decisions, and atomic ToolRun join reservation/activation/release. Add bindings, contract tests, thin Python adapters, and the required core revision pin. Keep public monitor starts on their existing path until activation.

## Notes

[2026-10-29T20:28:53Z · sase-1pj.5.1.1] Progress: Rust contracts + bindings + Python adapters + contract tests implemented and green (Rust staged_handoff/staged_join/prepared_reservation unit tests pass; sase_core_py 370 pass; 15 Python contract tests pass; symvision clean). sase-core `sase tool run check` (run f5f47f7b0b5093c86232d63010ee52a7) still running; sase-repo `just check` and bead close remain.

[2026-10-29T20:57:50Z · sase-1pj.5.1.1--1] PROPOSED FOLLOW-UP: sase_gateway IPC test listener_creates_private_socket_and_rejects_symlink flaked under host load (loadavg ~27) in full sase-core check run f5f47f7b0b5093c86232d63010ee52a7 with AlreadyRunning lock error; passes in isolation and full -p sase_gateway --lib rerun showed 243 passed — consider serializing or hardening that test

## Dependencies

- **Blocks:** [sase-1pj.5.1.2](sase-1pj.5.1.2.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.1.md) | [sase-1pj.5.1.1](sase-1pj.5.1.1.md) | 0 |
