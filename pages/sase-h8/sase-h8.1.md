# Bead: sase-h8.1 — A contention harness for the default (non-visual) lane

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v5/README.md) · **Assignee:** `sase-h8.1` · **Size:** medium
**Created:** 2026-08-07 18:04:16 EDT
**Plan:** [202608/parallel\_suite\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/parallel_suite_flake_class.md)

## Description

harness: add a `just test-contention` recipe and `run_pytest` mode that oversubscribes a pinned CPU set the way `test-visual-contention` already does for the PNG lane, plus a repeat/soak knob and a per-node failure tally, so the class can be reproduced and a fix can be falsified on demand.

## Dependencies

- **Blocks:** [sase-h8.3](sase-h8.3.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.1/README.md) | [sase-h8.1](sase-h8.1.md) | 0 |
