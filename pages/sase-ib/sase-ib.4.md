# Bead: sase-ib.4 — Cut cross-cutting per-test overhead outside the TUI

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.4` · **Size:** medium
**Created:** 2026-08-09 10:31:57 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

overhead: remove the repeated full-argparse parser builds, gettext lookups, YAML/config reparses, and avoidable CLI subprocess round-trips that the harness attributes across the non-TUI suite.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.4/README.md) | [sase-ib.4](sase-ib.4.md) | 0 |
