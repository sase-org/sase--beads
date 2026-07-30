# Bead: sase-b1.1 — Carry the swarm chain on expansion records

[Bead Pages](../README.md) / [sase-b1](README.md) / sase-b1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b1.1` · **Size:** small
**Created:** 2026-07-30 01:09:45 UTC · **Closed:** 2026-07-30 01:23:28 UTC
**Plan:** [202607/xprompt\_swarm\_stats.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_swarm_stats.md)

## Description

swarm-provenance: add an ordered outer-to-inner swarm-name chain to the expanded-segment record in sase/agent/xprompt_swarm.py, populated in all four expansion branches and inherited unchanged by pass-through segments, without altering template-group behavior.

## Notes

[2026-07-30T01:23:28Z · sase-b1.1] Implemented swarm_xprompts provenance on expansion records; verified focused expansion suite via .venv pytest and just test; reran just check, which passed fmt/lint/mypy/symvision/toobig before stopping on existing SDD plan-link validation errors.

## Dependencies

- **Blocks:** [sase-b1.2](sase-b1.2.md) ✓
