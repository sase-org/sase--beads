# Bead: sase-ku — sase monitor hardening — a supervisor that cannot silently orphan, wedge, or lie

[Bead Pages](../README.md) / sase-ku

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-kp.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-kp.land.w1.md) · **Assignee:** `sase-ku.land`
**Created:** 2026-08-13 09:02:19 EDT
**Plan:** [202608/monitor\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_hardening.md)

## Description

The monitor supervisor survives every command shape a real build throws at it — continuous output, partial lines, binary bytes, backgrounded grandchildren, TERM-ignoring children — enforces its deadline on every tick, never leaves a live process group behind when it dies, reconciles wedged lanes without a human, and only reports a monitor terminal once the claim, the log, and the follow-up have actually been settled.

## Notes

[2026-08-13T13:39:31Z · zd] HEADS-UP FROM ADJACENT WORK (no conflict expected): on 2026-08-13 the project owner asked for the monitor command string to be removed from the ACE Agents-tab LEFT PANE row. Rows previously rendered '⏱ <monitor_label> · <monitor_command> (<STATUS>)'; e.g. an epic-launch monitor read '⏱ Epic launch · artifacts_tab_icons · sase bead work /home/bryan/.sase/plans/202608/artifacts_tab_icons.md --ye', which swamped the tree at normal terminal widths. They now render '⏱ <monitor_label> (<STATUS>)'. monitor_label always exists (src/sase/monitor/start.py:113 falls back to _default_label(command)), and the full command is unchanged in the right-hand detail panel (src/sase/ace/tui/widgets/prompt_panel/_agent_monitor_section.py:67-70).

Files touched: src/sase/ace/tui/widgets/_agent_list_render_agent.py (dropped the ' · <command>' append), _agent_list_render_cache.py (dropped agent.monitor_command from agent_render_key, now unread by the row renderer), src/sase/ace/tui/modals/help_modal/agents_bindings.py:421 ('Monitor member (command)' -> 'Monitor member (label)'), and tests/ace/tui/widgets/test_agent_list_monitor_rows.py.

Why sase-ku should know: none of these files appear in plans:202608/monitor_hardening.md, and the phases landed so far (afa8178ce, dc9da5576) touch src/sase/monitor/**, src/sase/logs/pipe.py, and the scan wire — disjoint from this diff, so no merge conflict is expected. But phase sase-ku.10's end-to-end exercises inspect the live monitor row ('the monitor row shows live runtime', 'the row shows timeout' — plan lines 749/752). Those behaviors are all preserved: the ⏱ glyph, the label, the status parens, live runtime, and the ✗<exit>/⧖ badges are untouched. Only the command annotation is gone, so sase-ku.10's agent should not report its absence as a regression.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ku.1](sase-ku.1.md) | Monitor supervision fields on the agent scan wire | ✓ closed | small | 2026-08-13 | 1 | 2 |
| [sase-ku.10](sase-ku.10.md) | End-to-end hardening exercises | ◐ in_progress | xsmall | 2026-08-13 | 1 | 0 |
| [sase-ku.2](sase-ku.2.md) | Rebuild the supervisor's stream and wait loop | ✓ closed | medium | 2026-08-13 | 1 | 1 |
| [sase-ku.3](sase-ku.3.md) | Durable process identity for the supervisor and its child | ◐ in_progress | small | 2026-08-13 | 1 | 0 |
| [sase-ku.4](sase-ku.4.md) | Transactional monitor start and settlement | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-ku.5](sase-ku.5.md) | Active, complete reconciliation of dead supervisors | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-ku.6](sase-ku.6.md) | --idle-timeout for commands that hang without exiting | ✓ closed | small | 2026-08-13 | 1 | 1 |
| [sase-ku.7](sase-ku.7.md) | Follow-up prompt trust boundary and inherited routing | ◐ in_progress | medium | 2026-08-13 | 1 | 0 |
| [sase-ku.8](sase-ku.8.md) | Close the monitor fidelity gaps | ◐ in_progress | small | 2026-08-13 | 1 | 0 |
| [sase-ku.9](sase-ku.9.md) | Monitor documentation and skill hazards | ◐ in_progress | small | 2026-08-13 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ku: sase monitor hardening — a supervisor that cannot silently orphan, wedge, or lie [in_progress]"]
    n1["sase-ku.1: Monitor supervision fields on the agent scan wire [closed]"]
    n2["sase-ku.10: End-to-end hardening exercises [in_progress]"]
    n3["sase-ku.2: Rebuild the supervisor's stream and wait loop [closed]"]
    n4["sase-ku.3: Durable process identity for the supervisor and its child [in_progress]"]
    n5["sase-ku.4: Transactional monitor start and settlement [in_progress]"]
    n6["sase-ku.5: Active, complete reconciliation of dead supervisors [in_progress]"]
    n7["sase-ku.6: --idle-timeout for commands that hang without exiting [closed]"]
    n8["sase-ku.7: Follow-up prompt trust boundary and inherited routing [in_progress]"]
    n9["sase-ku.8: Close the monitor fidelity gaps [in_progress]"]
    n10["sase-ku.9: Monitor documentation and skill hazards [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n1 -.-> n4
    n1 -.-> n7
    n1 -.-> n8
    n3 -.-> n4
    n3 -.-> n7
    n3 -.-> n8
    n4 -.-> n5
    n5 -.-> n6
    n5 -.-> n9
    n6 -.-> n10
    n7 -.-> n10
    n8 -.-> n10
    n9 -.-> n10
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ku.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.1/README.md) | [sase-ku.1](sase-ku.1.md) | 2 |
| [bbugyi200.athena.sase-ku.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.10/README.md) | [sase-ku.10](sase-ku.10.md) | 0 |
| [bbugyi200.athena.sase-ku.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.2/README.md) | [sase-ku.2](sase-ku.2.md) | 1 |
| [bbugyi200.athena.sase-ku.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.3/README.md) | [sase-ku.3](sase-ku.3.md) | 0 |
| [bbugyi200.athena.sase-ku.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.4/README.md) | [sase-ku.4](sase-ku.4.md) | 0 |
| [bbugyi200.athena.sase-ku.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.5/README.md) | [sase-ku.5](sase-ku.5.md) | 0 |
| [bbugyi200.athena.sase-ku.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.6/README.md) | [sase-ku.6](sase-ku.6.md) | 1 |
| [bbugyi200.athena.sase-ku.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.7/README.md) | [sase-ku.7](sase-ku.7.md) | 0 |
| [bbugyi200.athena.sase-ku.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.8/README.md) | [sase-ku.8](sase-ku.8.md) | 0 |
| [bbugyi200.athena.sase-ku.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.9/README.md) | [sase-ku.9](sase-ku.9.md) | 0 |
| [bbugyi200.athena.sase-ku.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ku.land/README.md) | [sase-ku](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@87e4a4f`](https://github.com/sase-org/sase-core/commit/87e4a4f455192dd1f930925e2d46a67caacd25c0) | feat(agent-scan): add monitor supervision fields to the agent scan wire | [sase-ku.1](sase-ku.1.md) | 2026-08-13 09:30:37 EDT |
| sase | [`afa8178`](https://github.com/sase-org/sase/commit/afa8178ceec76e7fbbe94110c3af9ed4b7ba6d39) | fix(monitor): decouple supervisor waits from output reads | [sase-ku.2](sase-ku.2.md) | 2026-08-13 09:31:19 EDT |
| sase | [`dc9da55`](https://github.com/sase-org/sase/commit/dc9da557631a7ecb8e16dc5ebefd24cc1f0fda4c) | feat(agent-scan): mirror monitor supervision fields on the Python wire | [sase-ku.1](sase-ku.1.md) | 2026-08-13 09:31:37 EDT |
| sase | [`49f6b98`](https://github.com/sase-org/sase/commit/49f6b98a49614be766b6d03edca49762daba075a) | feat(monitor): add idle timeout support | [sase-ku.6](sase-ku.6.md) | 2026-08-13 10:01:00 EDT |
