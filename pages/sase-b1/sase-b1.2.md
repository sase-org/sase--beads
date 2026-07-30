# Bead: sase-b1.2 — Thread provenance to the spawn point

[Bead Pages](../README.md) / [sase-b1](README.md) / sase-b1.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.2` · **Size:** medium
**Created:** 2026-07-30 01:09:48 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

launch-env-plumbing: thread the per-segment swarm chain through the CLI and ACE launch paths alongside segment_template_groups, inject it into each spawned slot's environment like SASE_MULTI_AGENT_PROMPT_FILE, cover the single-segment fall-throughs, and scrub it from nested launches.

## Dependencies

- **Depends on:** [sase-b1.1](sase-b1.1.md) ✓
- **Blocks:** [sase-b1.4](sase-b1.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b1.2/README.md) | [sase-b1.2](sase-b1.2.md) | 0 |
