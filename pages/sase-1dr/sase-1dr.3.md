# Bead: sase-1dr.3 — Generic git file-history index in sase-core

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.3` · **Size:** medium
**Created:** 2026-09-30 19:09:20 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

file-history: add sase-core `file_history`. It runs a bounded, lock-free git runner and parses a first-parent `--raw -M` log over explicit pathspecs. It builds rename-aware lineage and path aliases, updates incrementally by tip ancestry, detects shallow or incomplete history, reads blobs in batches, reports a path's worktree, index, and tracked state, and persists a serializable snapshot.

## Dependencies

- **Blocks:** [sase-1dr.4](sase-1dr.4.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.3/README.md) | [sase-1dr.3](sase-1dr.3.md) | 0 |
