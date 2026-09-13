# Bead: sase-zt.6.3 — Complete capacity metadata, colors and both-state presentation

[Bead Pages](../README.md) / [sase-zt.6](sase-zt.6.md) / sase-zt.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.land.md) · **Assignee:** `sase-zt.6.3` · **Size:** medium
**Created:** 2026-09-13 07:09:20 EDT · **Closed:** 2026-09-13 11:10:13 EDT
**Plan:** [202609/queue\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_landing_repairs.md)

## Description

presentation: show authored capacity in the detail header and every eligible row, fix large-budget accents, preserve the legacy flag branch, and prove real scan-to-render behavior.

## Notes

[2026-09-13T15:09:20Z · sase-zt.6.3] PROPOSED FOLLOW-UP: Restore continuation_decide_resume_adoption Rust binding coverage — full just check escalates to the governed full suite and currently fails monitor/core binding tests because sase_core_rs==0.34.23 does not expose continuation_decide_resume_adoption.

[2026-09-13T15:10:13Z · sase-zt.6.3] Verified queue-capacity presentation with focused tests: just test tests/ace/tui/widgets/test_agent_list_runner_slot_status.py tests/ace/tui/widgets/test_agent_queue_section.py tests/test_run_agent_runner_slot_scan_capacity.py passed (32); just fmt-py and just _lint-symvision passed; epic-symbols clear. Full just check escalated to governed full suite and failed unrelated monitor/core binding tests because sase_core_rs lacks continuation_decide_resume_adoption; proposed follow-up recorded.

## Dependencies

- **Depends on:** [sase-zt.6.2](sase-zt.6.2.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zt.6.4](sase-zt.6.4.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.3/README.md) | [sase-zt.6.3](sase-zt.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`84a3ea2`](https://github.com/sase-org/sase/commit/84a3ea2dd685a3ea677b51fe5529fae5b38c286d) | feat(tui): show authored queue capacity metadata | [sase-zt.6.3](sase-zt.6.3.md) | 2026-09-13 11:48:57 EDT |
