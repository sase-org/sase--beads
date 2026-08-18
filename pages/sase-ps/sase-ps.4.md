# Bead: sase-ps.4 — Documentation sweep and cross-surface consistency check

[Bead Pages](../README.md) / [sase-ps](README.md) / sase-ps.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.063](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.063.md) · **Assignee:** `sase-ps.4` · **Size:** small
**Created:** 2026-08-18 10:20:06 EDT · **Closed:** 2026-08-18 12:41:37 EDT
**Plan:** [202608/monitor\_runner\_slots.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_runner_slots.md)

## Description

docs: retire the "serial family follow-ups do not consume slots" claim everywhere it appears, document the sase-agent occupancy rule and the monitor handoff, and verify every surface agrees end to end.

## Notes

[2026-08-18T16:40:31Z · sase-ps.4] PROPOSED FOLLOW-UP: just check mypy is red on master — src/sase/glossary/render.py:74 Console(color_system=console.color_system) is typed str|None vs Literal; not caused by this docs phase.

[2026-08-18T16:40:56Z · sase-ps.4] PROPOSED FOLLOW-UP: just check symvision is red on master — unused public monitor_row_is_settled (agent_family_members.py) and project_accent/project_accent_map (project_styles.py); no --epic-symbol entries; not caused by this docs phase.

[2026-08-18T16:41:11Z · sase-ps.4] Live consistency (this tree, monitors live): ACE chip R=5 L=10 Q=2; gate running_agent_slot_count=5; sase agent list holders=5 (sase-pt.3--mon, sase-pv.1--2, sase-pw.1, sase-ps.4, sase-pq.7); Statistics last-5-min peak=6 average≈5.26 (74% of window at 5). Host uv-tool sase still reported 4 because it predates the occupancy landing.

[2026-08-18T16:41:37Z · sase-ps.4] Retired the serial-follow-ups-do-not-consume-slots claim in default_config.yml, configuration.md, xprompt.md, ace.md (capacity chip + wait modal), troubleshooting/runner-slots.md, and llms.md. Added monitors.md Runner slots subsection (monitor holds the family slot for its lifetime and hands it to --next; not a way to free capacity) plus the operational note that the same max_running_agents now admits fewer new agents on monitor-heavy hosts (packaged default stays 10). Live consistency on this tree with monitors running: ACE chip R=5 L=10 Q=2; gate running_agent_slot_count=5; sase agent list holders=5 (sase-pt.3--mon, sase-pv.1--2, sase-pw.1, sase-ps.4, sase-pq.7); Statistics last-5-min peak=6 average≈5.26. No --epic-symbol leftovers. just check: fmt/ruff/remaining lint, validate, and scoped tests escalated to the full suite (src-data-asset default_config.yml) passed; mypy and symvision fail on pre-existing unrelated symbols (PROPOSED FOLLOW-UP).

[2026-08-18T16:43:25Z · sase-ps.4] Retired the serial-follow-ups-do-not-consume-slots claim in default_config.yml, configuration.md, xprompt.md, ace.md, troubleshooting/runner-slots.md, llms.md, monitors.md, and getting_started.md. A serial family holds one slot while any of its shells is live (root, serial child, monitor, or --next). Live consistency: ACE chip, gate slot count, and agent list agreed. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-ps.1](sase-ps.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-ps.2](sase-ps.2.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-ps.3](sase-ps.3.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ps.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ps.4/README.md) | [sase-ps.4](sase-ps.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5bb381f`](https://github.com/sase-org/sase/commit/5bb381f4a22eb2943a13e4eefcaaae5c34cfd86e) | docs(runner-slots): document serial-family occupancy including monitors | [sase-ps.4](sase-ps.4.md) | 2026-08-18 12:44:05 EDT |
