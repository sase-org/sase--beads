# Bead: sase-1r8.1 — Anchor the scanner rules and make scanner-hit blocks rules-versioned (sase-core)

[Bead Pages](../README.md) / [sase-1r8](README.md) / sase-1r8.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.184](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.184.md) · **Assignee:** `sase-1r8.1` · **Size:** medium
**Created:** 2026-11-04 13:54:36 EST
**Plan:** [202611/agent\_publication\_errors.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_publication_errors.md)

## Description

core: in sase-core, add a left token boundary to the prefix credential rules, bump the scanner rules version to 2, make a scanner-hit block enforced only while its evidence is current, supersede stale blocks with provenance on a clean rescan, add a parked-recheck predicate, and expose all of it through bindings with tests.

## Dependencies

- **Blocks:** [sase-1r8.4](sase-1r8.4.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r8.1/README.md) | [sase-1r8.1](sase-1r8.1.md) | 0 |
