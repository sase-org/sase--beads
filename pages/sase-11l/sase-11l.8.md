# Bead: sase-11l.8 — TUI, doctor, and deadlock visibility

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.8` · **Size:** medium
**Created:** 2026-09-15 22:46:05 EDT · **Closed:** 2026-09-16 15:30:59 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

hold-visibility: surface holds — held_by on queue markers, Agents-tab and agent list -j rendering, a TUI hold panel modeled on the runner-limit override panel, a doctor stale-hold check, and the admission-deadlock notification.

## Notes

[2026-09-16T19:29:51Z · sase-11l.8] PROPOSED FOLLOW-UP: bug — tests/main/test_init_skills_sources.py::test_shipped_skill_source_is_discoverable_for_all_skill_providers[sase_questions-expected_phrases11] fails on master (confirmed pre-existing, unrelated to hold-visibility): the shipped src/sase/xprompts/skills/sase_questions.md body no longer contains the phrase "Your turn ends as `DONE`" the test expects, so the skill doc and the test drifted apart.

[2026-09-16T19:30:24Z · sase-11l.8] PROPOSED FOLLOW-UP: feature — persist arm-time capture counts (waiting/queued/skipped-running) onto the durable hold record in agent_hold.rs/agent_hold_facade.py, not just the transient AgentHoldArmResult. Today sase agent hold list, sase agent hold show, and the new TUI Holds panel (src/sase/ace/tui/modals/holds_pane.py) can only show selectors/scope/expiry for an already-armed hold; the capture summary ("captures 4 waiting + 2 queued; skips 3 running") is only ever available once, in the arm-time CLI/notification output.

[2026-09-16T19:30:59Z · sase-11l.8] hold-visibility implemented and verified: (1) queue-marker held_by/hold_expires_at persisted by the candidate's own runner (run_agent_wait_slots.py/run_agent_wait_markers.py/agent_scan_wire_markers.py), surfaced through AgentWaitInfo, agent_list_entries.py, the ACE Agents-tab QUEUED row ('held by <armer>'), the render cache key, and 'sase agent list -j'; (2) new 'sase doctor' check agent_holds.stale (src/sase/doctor/checks_agent_holds.py, registered in doctor/runner.py) flagging dead-armer/past-expiry holds a routine read would silently prune; (3) hold-deadlock notification at runner-slot admission (hold_deadlock_armer_record in run_agent_wait_slot_candidate.py + upsert_notification in run_agent_wait_slots.py) for a candidate/armer mutual-wait cycle, dedup'd per candidate+armer; (4) new TUI Holds panel (src/sase/ace/tui/modals/holds_pane.py) listing active holds with selectors/scope/expiry and a release action, registered as a new 'holds' Config-hub sub-tab in config_hub_catalog.py/config_hub_session.py (alphabetically between flags and launch), with existing config-hub navigation tests renumbered accordingly. epic-symbols: none for this phase. just check: all lint gates green; full scoped test suite green except one confirmed pre-existing failure unrelated to this phase (tests/main/test_init_skills_sources.py::...[sase_questions-...], recorded as a PROPOSED FOLLOW-UP note, not fixed here). A second PROPOSED FOLLOW-UP note records that arm-time capture counts aren't persisted onto the durable hold record, so the CLI/TUI can't show them after arm time.

## Dependencies

- **Blocks:** [sase-11l.10](sase-11l.10.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.4](sase-11l.4.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.8/README.md) | [sase-11l.8](sase-11l.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`09cb008`](https://github.com/sase-org/sase/commit/09cb008b22ea90adbf87cdae583fd31491e6ee67) | feat(agent-hold): surface hold visibility in the TUI, doctor, and admission notifications | [sase-11l.8](sase-11l.8.md) | 2026-09-16 15:32:33 EDT |
