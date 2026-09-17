# Bead: sase-11l.5.1.2.1.3 — Pre-arm typed plans and follow units to dispatch

[Bead Pages](../README.md) / [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) / sase-11l.5.1.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.3` · **Size:** medium
**Created:** 2026-09-16 16:01:38 EDT · **Closed:** 2026-09-17 09:29:35 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

## Description

typed-arm: pre-arm hold-carrying units under the admission lock, with idempotent per-unit markers and rollback on failure. The coordinator re-anchors the holds before it acks startup. Agent dispatch passes the key and re-anchors the hold to the spawned runner; proc dispatch rebinds the hold to the proc. Units that never dispatch release their hold, and proc candidates and proc capacity admission use the key and the implied priority.

## Notes

[2026-09-17T13:29:35Z · sase-11l.5.1.2.1.3] Implemented typed-plan %hold pre-arm, re-anchor, dispatch carry, proc rebind/release, self-exclusion, and implied priority; verified focused launch/hold/proc/typed tests and just check (including full-suite escalation for Justfile).

## Dependencies

- **Depends on:** [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.3/README.md) | [sase-11l.5.1.2.1.3](sase-11l.5.1.2.1.3.md) | 0 |
