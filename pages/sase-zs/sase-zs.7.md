# Bead: sase-zs.7 — Bound clone concurrency and stop stranding workspaces on transient failure

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.7` · **Size:** medium
**Created:** 2026-09-12 09:44:55 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

materialization: cap concurrent remote clones so parallel launches stop saturating the uplink, and let the agent runner degrade or requeue instead of hard-failing and holding a numbered workspace.

## Dependencies

- **Depends on:** [sase-zs.2](sase-zs.2.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.7/README.md) | [sase-zs.7](sase-zs.7.md) | 0 |
