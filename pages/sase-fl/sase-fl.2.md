# Bead: sase-fl.2 — Agent runners survive mid-run editable source swaps

[Bead Pages](../README.md) / [sase-fl](README.md) / sase-fl.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tl/README.md) · **Assignee:** `sase-fl.2` · **Size:** medium
**Created:** 2026-08-05 18:32:24 EDT
**Plan:** [202608/epic\_launch\_false\_failure.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_launch_false_failure.md)

## Description

skew_guard: preload the post-gate import surface once at agent-runner start so a later `sase dev update` cannot tear a deferred import, snapshot the source revision the process booted against, and label failures whose cause is an import error after a swap as a code swap rather than an unusable store.

## Dependencies

- **Blocks:** [sase-fl.3](sase-fl.3.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fl.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fl.2/README.md) | [sase-fl.2](sase-fl.2.md) | 0 |
