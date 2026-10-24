# Bead: sase-1nv.4 — Explicit repair for existing stale-revision outbox rows

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.4` · **Size:** medium
**Created:** 2026-10-24 07:01:33 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

## Description

stale-row-repair: add a report-first, audited `sase agent sync` repair that maps each stale requested revision to the agent's committed revision, or to linked scope, without dropping any request.

## Dependencies

- **Depends on:** [sase-1nv.3](sase-1nv.3.md) ✓ · ⧖ 2026-10-24
- **Blocks:** [sase-1nv.5](sase-1nv.5.md) ◐ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.4/README.md) | [sase-1nv.4](sase-1nv.4.md) | 0 |
