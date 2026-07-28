# Bead: sase-m.1 — Phase 1: Eliminate subprocess work in CommitWorkflow tests

[Bead Pages](../README.md) / [sase-m](README.md) / sase-m.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 14:30:48 UTC · **Closed:** 2026-04-24 14:37:40 UTC
**Plan:** [202604/speed\_up\_slow\_tests.md](https://github.com/sase-org/sase--plans/blob/main/202604/speed_up_slow_tests.md)

## Description

Extend _no_precommit autouse fixtures across five commit workflow test files to additionally patch handle_beads, handle_sase_plan, and capture_pre_commit_diff at the workflow import site. Target: each affected test drops to <=1 s.

## Dependencies

- **Blocks:** [sase-m.3](sase-m.3.md) ✓
