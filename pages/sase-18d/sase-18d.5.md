# Bead: sase-18d.5 — Additive dismissed-index persistence for every writer

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.5` · **Size:** medium
**Created:** 2026-09-24 16:28:35 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

additive-dismissals: switch the cleanup transactions and every other dismissed-agents writer from full-snapshot saves to the core-wire add/remove API. Revive becomes a removal. Concurrent procs, runners, and TUIs can no longer lose each other's dismissals.

## Dependencies

- **Depends on:** [sase-18d.1](sase-18d.1.md) ◐ · ⧖ 2026-09-24
- **Depends on:** [sase-18d.4](sase-18d.4.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.6](sase-18d.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.5/README.md) | [sase-18d.5](sase-18d.5.md) | 0 |
