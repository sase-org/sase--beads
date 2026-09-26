# Bead: sase-1ap.4.1 — Restore the visual test runtime

[Bead Pages](../README.md) / [sase-1ap.4](sase-1ap.4.md) / sase-1ap.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ap.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ap.land.md) · **Assignee:** `sase-1ap.4.1` · **Size:** small
**Created:** 2026-09-26 14:32:48 EDT · **Closed:** 2026-09-26 14:44:01 EDT
**Plan:** [202609/1ap\_visual\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/1ap_visual_completion.md)

## Description

visual_runtime: Rebuild the workspace Rust binding from the linked sase-core revision and prove both new Context visual tests reach rendering. Repair a real source or binding incompatibility only if a fresh build still fails.

## Notes

[2026-09-26T18:43:13Z · sase-1ap.4.1] PROPOSED FOLLOW-UP: narrow created-bead visual test needs sentinel/render fix for sase-1ap.4.2 — test_agents_bead_created_by_agent_narrow_png_snapshot times out waiting for SVG sentinel Beads: at 90x32 (stable digest 2d5cebfef83e across serial and xdist runs); the Context card renders but the lane header shows as BEAD-truncated, so phase visual_goldens must fix the sentinel or the narrow header wrap before capturing agents_bead_created_by_agent_90x32.png

[2026-09-26T18:43:35Z · sase-1ap.4.1] PROPOSED FOLLOW-UP: pre-existing collection ImportErrors on clean tree at HEAD 7606e5d8c7 — tests/ace/tui/models/test_agent_proc_shells.py (PROC_LIFECYCLE_PROC_SHELL vs LEGACY_ export), test_gate_rows.py/test_monitor_rows.py (AgentSessionShellGateWire/MonitorWire missing), test_agent_panel_title_monitor_badges.py/test_gate_failure_recovery.py (sase.gate_shell.state gone), plus 9 more collectors; reproduced with git status clean so unrelated to visual_runtime work, but they turn broad-collection runs red

[2026-09-26T18:44:01Z · sase-1ap.4.1] just install rebuilt sase-core-rs 0.34.73 from linked sase-core checkout (e654e7c, includes pinned e579d1d creation-reason wire); no startup runner-capacity error. Wide test test_agents_bead_created_by_agent_png_snapshot passes all SVG sentinels (SASE CONTEXT, Beads:, sase-1c, CREATED, why:, assigned, CLOSED, created) and reaches PNG capture; missing goldens left for sase-1ap.4.2. Narrow test starts and renders (agents tab, agent_count 1, Context card visible) but times out on the Beads: sentinel — recorded as follow-up for visual_goldens. No tracked files changed; no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ap.4.2](sase-1ap.4.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ap.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.4.1/README.md) | [sase-1ap.4.1](sase-1ap.4.1.md) | 0 |
