# Bead: sase-am.2 — Build the Rust core once per run

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.2

**Status:** ◎ claimed · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.2` · **Size:** medium
**Created:** 2026-07-28 22:05:55 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

core-wheel-once: add a build-core root job that builds one abi3 sase_core_rs wheel per run, teach the Justfile a SASE_CORE_WHEEL install path, fan the wheel out via artifact and a setup-sase composite action, and drop the duplicated sase-core rust-check from bead-backend.

## Dependencies

- **Depends on:** [sase-am.1](sase-am.1.md) ✓
- **Blocks:** [sase-am.3](sase-am.3.md) ◎

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.2/README.md) | [sase-am.2](sase-am.2.md) | 0 |
