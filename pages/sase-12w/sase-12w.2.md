# Bead: sase-12w.2 — Detached sudo answer path and finalize proc

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.2` · **Size:** large
**Created:** 2026-09-18 08:50:39 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

cli: add an opt-in --detach path to `sase sudo answer` that runs the runner in auth-then-spawn mode, records a durable in-flight execution record, and submits a supervised finalize proc; add the internal `sase sudo finalize` subcommand that waits for the executor, validates the ledger, answers the gate, and settles the gate shell.

## Dependencies

- **Depends on:** [sase-12w.1](sase-12w.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.3](sase-12w.3.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.4](sase-12w.4.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.2/README.md) | [sase-12w.2](sase-12w.2.md) | 0 |
