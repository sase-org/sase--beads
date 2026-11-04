# Bead: sase-1r8.2 — One drain loop that never lets a failing row starve its project

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.2` · **Size:** medium
**Created:** 2026-11-04 13:54:36 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

drain: replace the hinted-then-fallback loops in publication_job with one loop that excludes keys already attempted this pass, stops only on repository-scope failures, reports failure scope on the drain outcome, and compacts claimed hint files to at most one per project.

## Dependencies

- **Blocks:** [sase-1r8.5](sase-1r8.5.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.2/README.md) | [sase-1r8.2](sase-1r8.2.md) | 0 |
