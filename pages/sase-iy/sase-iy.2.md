# Bead: sase-iy.2 — Fix the deterministic prompt-catalog convergence hang in the PNG lane

[Bead Pages](../README.md) / [sase-iy](README.md) / sase-iy.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xb/README.md) · **Assignee:** `sase-iy.2` · **Size:** medium
**Created:** 2026-08-10 11:01:31 EDT
**Plan:** [202608/retire\_sase\_ct\_umbrella.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_sase_ct_umbrella.md)

## Description

catalog: make the ACE startup prompt-catalog rebuild worker stop holding wait_for_visual_idle open for its full 30s deadline. Reproduced deterministically in isolation on clean master; fix it centrally in the visual fixtures rather than per file, and prove the PNG lane green.

## Dependencies

- **Blocks:** [sase-iy.5](sase-iy.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iy.2/README.md) | [sase-iy.2](sase-iy.2.md) | 0 |
