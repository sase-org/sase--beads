# Bead: sase-1bc.6.1.6.1 — Scope pipeline, tab switch memory, catalog maintenance, and key yield fixes

[Bead Pages](../README.md) / [sase-1bc.6.1.6](sase-1bc.6.1.6.md) / sase-1bc.6.1.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) · **Assignee:** `sase-1bc.6.1.6.1` · **Size:** medium
**Created:** 2026-09-27 20:11:24 EDT · **Closed:** 2026-09-27 22:11:26 EDT
**Plan:** [202609/agent\_tabs\_scope\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md)

## Description

switch-pipeline-repairs: apply worker-path status overrides over the tab-independent query result; make the tab-index memo hit on an unchanged roster without retaining old rosters; restore each tab's own row index, focused panel, and scroll anchor; latch emptied machine tabs instead of stranding the user; fix the doubled machine-gone toast glyph, the empty-first-catalog startup skip, and the attention-tab choice; unbind only the colliding bracket key in the legacy yield; hide the agent-tab help rows with the flag off.

## Notes

[2026-09-28T01:59:05Z · sase-1bc.6.1.6.1] PROPOSED FOLLOW-UP: Reconcile clean-base completion assertions with %tab candidates — test_agent_completion failures include tab-kind main candidates with agent_tabs disabled; source and tests are unchanged here, and the %tab completion feature is tracked by sase-1bc.4.

[2026-09-28T01:59:14Z · sase-1bc.6.1.6.1] PROPOSED FOLLOW-UP: Resolve the clean-base rail Symvision warnings — check f37938d440316d52fb95bab27de859e4 classified rail_panel_title, rail_tooltip_text, and rail_urgency as KNOWN with prior witness 237f06811ee5ce85a9e8512439736bea; the open sase-1bn bead tracks their downstream rail wiring.

[2026-09-28T02:11:26Z · sase-1bc.6.1.6.1--1] Verified 115 focused agent-tab tests passed; targeted flag-off Help panel visual check passed (5 snapshots, 0 created or updated; 5 unchanged). Recorded full-check follow-ups for clean-base completion failures tracked by sase-1bc.4 and known rail Symvision warnings tracked by sase-1bn. epic-symbols reported no remaining phase entries.

## Dependencies

- **Blocks:** [sase-1bc.6.1.6.2](sase-1bc.6.1.6.2.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.6.3](sase-1bc.6.1.6.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.6.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.6.1.md) | [sase-1bc.6.1.6.1](sase-1bc.6.1.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dae0f6e`](https://github.com/sase-org/sase/commit/dae0f6efad9f08622c954cfa536dba769bf23b1d) | fix(ace): repair agent tab scope and switching | [sase-1bc.6.1.6.1](sase-1bc.6.1.6.1.md) | 2026-09-27 22:13:18 EDT |
