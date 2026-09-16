# Bead: sase-11l.5.1.2.1.2 — Python hold facade and launch-hold primitives

[Bead Pages](../README.md) / [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) / sase-11l.5.1.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.2` · **Size:** medium
**Created:** 2026-09-16 16:01:38 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

## Description

hold-facade: extend the facade with an explicit armer and selectors, rebind, a shared TTL resolver, and `launch`-kind validation and liveness (a receipt only counts once it is complete). Add `launch_hold.py` with the key, armer, arm, pre-arm, rebind, re-anchor, and release primitives, plus `HOLD_ARMER_WAIT_PRIORITY`. The CLI reuses the TTL resolver.

## Dependencies

- **Depends on:** [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.2.1.3](sase-11l.5.1.2.1.3.md) ◐ · ⧖ 2026-09-16
- **Blocks:** [sase-11l.5.1.2.1.4](sase-11l.5.1.2.1.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) | 0 |
