# Bead: sase-10r.2 — Runner-exit scratch cleanup and low-free-space pressure reaping

[Bead Pages](../README.md) / [sase-10r](README.md) / sase-10r.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.0l](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.0l.md) · **Assignee:** `sase-10r.2` · **Size:** medium
**Created:** 2026-09-14 06:56:22 EDT
**Plan:** [202609/apollo\_disk\_reclaim\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/apollo_disk_reclaim_1.md)

## Description

agent-scratch-exit-cleanup: remove the runner's launch-assigned cargo-targets and agent-tmp directories at exit, and use a 1h pressure min age whenever the free-space floor is breached regardless of which pressure trigger fired, with tests.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.kellys\_mbp.sase-10r.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.kellys_mbp.sase-10r.2/README.md) | [sase-10r.2](sase-10r.2.md) | 0 |
