# Bead: sase-1s5.2 — Batched dismissal-lineage resolution makes fleet snapshot builds fast

[Bead Pages](../README.md) / [sase-1s5](README.md) / sase-1s5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cy--6` · **Assignee:** `sase-1s5.2` · **Size:** medium
**Created:** 2026-11-08 06:51:28 EST
**Plan:** [202611/health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/health_watch_fixes.md)

## Description

fleet-lineage-batch: in sase-core, replace the per-candidate SQL lineage walk in resolve_agent_session_dismissal_lineage with one lineage-column load per (project, workflow dir) pair and an in-memory walk with identical results, prove equivalence and O(pairs) query count in tests, move sase's sase-core pin, and verify on apollo (F10).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s5.2/README.md) | [sase-1s5.2](sase-1s5.2.md) | 0 |
