# Bead: sase-12w.4 — Detached execution for remote sudo targets

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.4` · **Size:** medium
**Created:** 2026-09-18 08:50:41 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

remote: extend `sase sudo exec` and the SSH relay so a remote target authenticates interactively, spawns its own detached executor, and the local finalize proc polls for and fetches the remote ledger; gate the path on an additive contract capability with a synchronous fallback.

## Dependencies

- **Depends on:** [sase-12w.2](sase-12w.2.md) ◐ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.5](sase-12w.5.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.4/README.md) | [sase-12w.4](sase-12w.4.md) | 0 |
