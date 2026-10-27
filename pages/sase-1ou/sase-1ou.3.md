# Bead: sase-1ou.3 — Make the weight-two land-agent-session capacity e2e load-robust (sase-12f)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.3` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

capacity-e2e: find what consumes the fakey land agent's 5 s budget under load in tests/fakey/test_monitor_capacity_e2e.py (delayed child bootstrap, capacity scan under the host-wide slot lock, or harness polling), fix the cause instead of the timeout, prove it with a loaded stress loop, and close sase-12f.

## Notes

[2026-10-27T14:41:51Z · sase-1ou.3] PLANNING EVIDENCE: At clean base e608de2db6 the unchanged target passed once in 65.58s, with 61.89s test-call time and 60.608s in settle_named_proc before successor startup. The shared fakey harness creates flat ace-run timestamp paths, while production starter settlement uses canonical date-sharded paths. An in-memory diagnostic probe using canonical agent paths preserved all assertions and five-second budgets and passed in 4.32s total / 1.85s call; the real starter-settlement wait saw done.json already present and returned True immediately. No source implementation edits were made. This proves the wasted settlement wait, not the historical load-only exit-124 cause. The validated medium tale sase_plan_capacity_e2e_load_robust.md requires comparable isolated and loaded before/after evidence before closure. epic-symbols reported no entries for this phase.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.3.md) | [sase-1ou.3](sase-1ou.3.md) | 0 |
