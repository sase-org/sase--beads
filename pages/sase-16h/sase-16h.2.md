# Bead: sase-16h.2 — Record child process facts and authorize reaping in sase-core

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.2` · **Size:** medium
**Created:** 2026-09-22 13:05:40 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

core-child-facts: add the sase-core wire, store write, and binding that persist a running run's child pid, pgid, and process identity, extend reconcile to return identity-matched reap candidates, and move sase's core revision pin past that commit.

## Dependencies

- **Depends on:** [sase-16h.1](sase-16h.1.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16h.3](sase-16h.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.2/README.md) | [sase-16h.2](sase-16h.2.md) | 0 |
