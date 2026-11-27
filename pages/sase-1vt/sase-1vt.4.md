# Bead: sase-1vt.4 — Conflict replay for unmergeable zero-spawn graph publication

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.4` · **Size:** medium
**Created:** 2026-11-27 15:24:25 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

replay: carry the integration status out of the managed sync worker, raise a typed publication-conflict error, and in the plan-launch retry loop discard the launch's own unpublished graph commit under a recovery ref and re-mint, with cause-first error text.

## Dependencies

- **Depends on:** [sase-1vt.3](sase-1vt.3.md) ◐ · ⧖ 2026-11-27
- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.4/README.md) | [sase-1vt.4](sase-1vt.4.md) | 0 |
