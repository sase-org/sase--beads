# Bead: sase-17x.13.2 — Fix call\_from\_thread misuse on the app loop

[Bead Pages](../README.md) / [sase-17x.13](sase-17x.13.md) / sase-17x.13.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.land.md) · **Assignee:** `sase-17x.13.2` · **Size:** small
**Created:** 2026-09-24 20:28:41 EDT
**Plan:** [202609/command\_line\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_fixes.md)

## Description

worker-hops: stop calling `call_from_thread` from coroutines that already run on the app loop. This fixes the `v` pager crash on an unloaded tail and the popup that never leaves `indexing commands…`. Sweep the package for the same pattern and add pilot tests on the real paths.

## Dependencies

- **Blocks:** [sase-17x.13.3](sase-17x.13.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.13.2/README.md) | [sase-17x.13.2](sase-17x.13.2.md) | 0 |
