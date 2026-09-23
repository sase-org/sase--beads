# Bead: sase-16t.3 — Never lose a pane report, never treat loading as absence

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.3` · **Size:** medium
**Created:** 2026-09-23 08:23:33 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

seam: fix the confirmed root cause (Beads/Plans/Agents/Files resolve a request synchronously, the report is dropped during dispatch, and the pane returns PENDING so the transaction hangs), capture synchronous reports at the host seam, make fold-hidden pending targets truthful, wait on loading panes, re-resolve refs after load, fix project scope handling, re-index hydrated rows, and add real-pane regression tests.

## Dependencies

- **Blocks:** [sase-16t.4](sase-16t.4.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.3/README.md) | [sase-16t.3](sase-16t.3.md) | 0 |
