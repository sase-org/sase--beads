# Bead: sase-fp.3 — Scoped run mode and the no-lease path

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.3` · **Size:** medium
**Created:** 2026-08-05 20:56:13 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

runner: add a `scoped` mode to tools/run_pytest that runs the selection serially with the suite-gate explicitly disabled, escalates to the governed full lane when the selection is too large, and never queues for tokens.

## Dependencies

- **Depends on:** [sase-fp.1](sase-fp.1.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fp.2](sase-fp.2.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.4](sase-fp.4.md) ◐ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.5](sase-fp.5.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.3/README.md) | [sase-fp.3](sase-fp.3.md) | 0 |
