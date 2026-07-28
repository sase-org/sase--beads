# Bead: sase-aj.4 — Deterministic bead projection output

[Bead Pages](../README.md) / [sase-aj](README.md) / sase-aj.4

**Status:** ◎ claimed · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aj.4` · **Size:** medium
**Created:** 2026-07-28 20:21:43 UTC
**Plan:** [202607/beads\_commit\_consolidation.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_commit_consolidation.md)

## Description

detproj: make `issues.jsonl` and every other regenerated projection byte-stable across all writers so clones never dirty their worktree with pure reorders that later get swept into commits under recycled semantic messages.

## Dependencies

- **Depends on:** [sase-aj.1](sase-aj.1.md) ✓
