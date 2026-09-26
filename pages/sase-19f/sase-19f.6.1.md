# Bead: sase-19f.6.1 — Carry multiplier through TUI agent models and loaders

[Bead Pages](../README.md) / [sase-19f.6](sase-19f.6.md) / sase-19f.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.land.md) · **Assignee:** `sase-19f.6.1` · **Size:** medium
**Created:** 2026-09-26 04:40:41 EDT · **Closed:** 2026-09-26 06:18:30 EDT
**Plan:** [202609/queue\_multiplier\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_surfaces.md)

## Description

model-projection: Add queue_capacity_multiplier to Agent state and every metadata, filesystem, identity, fleet, dedup, clan, and roster projection that carries queue capacity. Keep integer and multiplier mutually exclusive in setters and copies. Add focused projection and fleet tests.

## Notes

[2026-09-26T10:17:52Z · sase-19f.6.1--2] PROPOSED FOLLOW-UP: full-suite just check flakes under parallel load — test_busy_cluster_compacts_narrow_and_restores_wide, test_child_pytest_of_a_stageless_run_records_no_stage_rows, test_empty_panel_semicolon_hops_to_palette_and_back all pass serially and in small -n 4 runs on this tree; re-run failed once then passed identically

[2026-09-26T10:18:06Z · sase-19f.6.1--2] PROPOSED FOLLOW-UP: sase-19f.6.2 display sites still integer-only — _waiting_digest c-badge (src/sase/ace/tui/models/_agent_clan_sections.py:457) and _agent_runner_slot_capacity.py read wait_runners only; multiplier survives on the row, rendering is 6.2 scope

[2026-09-26T10:18:30Z · sase-19f.6.1--2] Verified: just _lint-symvision green (removed stale format_queue_capacity_multiplier epic-symbol); 856 tests/ace/tui/models tests pass incl 17 new multiplier projection/fleet tests; Agent subclasses AgentState so copies carry the field and set_queue_capacity keeps int/multiplier exclusive; 3 full-suite failures triaged as parallel-load flakes passing serially (recorded as follow-ups)

## Dependencies

- **Blocks:** [sase-19f.6.2](sase-19f.6.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.6.1.md) | [sase-19f.6.1](sase-19f.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`73c47eb`](https://github.com/sase-org/sase/commit/73c47eb84f51e40098a25b53420beeebd4a2398c) | feat(tui): project queue capacity multiplier through agent state, dedup, fleet and loaders | [sase-19f.6.1](sase-19f.6.1.md) | 2026-09-26 06:20:39 EDT |
