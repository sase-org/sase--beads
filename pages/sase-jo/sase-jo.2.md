# Bead: sase-jo.2 — Tracked-commit provenance invariant

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.2` · **Size:** medium
**Created:** 2026-08-11 06:58:28 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

invariant: stamp `SASE_TYPE=stitch` on every commit created through the tracked `sase stitch create` workflow, audit every remaining commit-creating call site so each stamps a `SASE_TYPE=` value, and add a contract test that keeps new call sites from regressing the invariant.

## Dependencies

- **Blocks:** [sase-jo.6](sase-jo.6.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.2/README.md) | [sase-jo.2](sase-jo.2.md) | 0 |
