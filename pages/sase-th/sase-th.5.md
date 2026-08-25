# Bead: sase-th.5 — Isolate the pooled-alias round-robin cursor from tests

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.5` · **Size:** medium
**Created:** 2026-08-25 07:32:02 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

pool-cursor: stop the machine-global llm_lb.json cursor from leaking between concurrently running test files, which is why the pooled-alias consumption tests fail only in CI's parallel lane.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-th.5.md) | [sase-th.5](sase-th.5.md) | 0 |
