# Bead: sase-18d.3 — Verified process-tree termination in the durable cleanup proc

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.3` · **Size:** medium
**Created:** 2026-09-24 16:28:32 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

tree-kill: add a shared terminator that finds an agent's whole process set (process group, session, ppid tree, and inherited launch scratch key). It sends SIGTERM, escalates to SIGKILL, and verifies death. The durable persist-cleanup proc runs it before it releases workspaces or deletes artifacts. The TUI only sends the immediate SIGTERM. Also stop the in-flight guard from dropping whole batches.

## Dependencies

- **Depends on:** [sase-18d.2](sase-18d.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18d.4](sase-18d.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.3/README.md) | [sase-18d.3](sase-18d.3.md) | 0 |
