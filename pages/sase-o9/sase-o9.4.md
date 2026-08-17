# Bead: sase-o9.4 — \<enter\> opens the monitor's agent on the Agents tab

[Bead Pages](../README.md) / [sase-o9](README.md) / sase-o9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md) · **Assignee:** `sase-o9.4` · **Size:** medium
**Created:** 2026-08-17 06:54:28 EDT · **Closed:** 2026-08-17 08:35:05 EDT
**Plan:** [202608/procs\_tab\_monitor\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)

## Description

agent-jump: add the <enter> keymap that resolves a monitor row to its agent and reveals it on the Agents tab, with honest failure messages and help/hints coverage.

## Notes

[2026-08-17T12:34:19Z · sase-o9.4] PROPOSED FOLLOW-UP: `just lint`/`just check` fail repo-wide at the symvision gate — Justfile:326-330 lists --epic-symbol whitelist entries for sase-o8.3 and sase-o8.4, both now closed; symvision refuses stale entries for closed beads. Remove the sase-o8.3(*) and sase-o8.4(load_common_placeholder_index) entries (and delete the now-unused symbols if still private/unused) so the lint gate is unblocked for every agent. Confirmed pre-existing on a clean master via git stash, unrelated to this phase.

[2026-08-17T12:34:39Z · sase-o9.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_stays_open_when_submit_collides is flaky under the 4-worker xdist full-suite run (just test-scoped escalated to the full 2827-file suite and it failed on a 5s expect_modal timeout waiting for PluginActionConfirmModal); it passes reliably in isolation. Unrelated to this phase (Procs pane agent-jump) — likely CPU-contention timing sensitivity worth a longer timeout or serial marker.

[2026-08-17T12:35:05Z · sase-o9.4] Added ProcsPaneAgentJumpMixin (procs_pane_agent_jump.py) with action_open_monitor_agent + OptionSelected routing so <enter>/click on a monitor row scans app._agents for a matching monitor_id, dismisses the Admin Center via ConfigCenterModal.action_close() (remembers Procs), and reveals the agent via _reveal_agent_row(..., subject='Monitor agent') after call_after_refresh; threaded an optional subject kwarg through _reveal_agent_row/_notify_member_reveal_failure (default 'Member' preserves existing member-jump wording, verified via test_member_jump_navigation.py + test_member_jump_from_member_rows.py). Added conditional '⏎: agent' hints-line token (shown only when the row resolves to a loaded Agent) wired via _update_hints() on rebuild and on highlight change. Added Enter row to ADMIN_CENTER_TASKS_SECTION help text. New/updated tests in test_procs_pane.py (dismiss+reveal, no-match notify, plain-row no-op, jump-mode inertness, click path, conditional hint) plus ProcsTestApp harness stubs for current_tab/_save_current_tab_position/_reveal_agent_row. Verified: ruff check, ruff format, mypy all clean; full procs-pane + member-jump + help-modal suites pass (72 tests); just test-scoped escalated to the full 2827-file suite (stale coverage baseline) with 1405 passed/1 failed, and the failure (test_comprehensive_confirmation_stays_open_when_submit_collides) reproduces only under xdist contention and passes in isolation — unrelated pre-existing flake, filed as PROPOSED FOLLOW-UP. just lint/just check symvision gate fails repo-wide on stale sase-o8.3/sase-o8.4 --epic-symbol whitelist entries in Justfile, confirmed pre-existing via git stash on clean master — filed as PROPOSED FOLLOW-UP.

[2026-08-17T12:35:50Z · sase-o9.4] Implemented ProcsPaneAgentJumpMixin (Enter on a monitor row dismisses Admin Center and reveals the agent on the Agents tab), threaded subject through _member_jump.py, wired procs_pane.py binding/hints and help_modal binding_common.py Enter row. ruff/mypy/format clean; procs-pane, member-jump, help-modal suites pass (72 tests, 6 new). just test-scoped escalated to full suite: 1405/1406 passed (1 pre-existing unrelated xdist flake). just check symvision gate fails repo-wide on stale closed-bead whitelist entries, confirmed pre-existing on clean master. Both recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-o9.2](sase-o9.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o9.5](sase-o9.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o9.4/README.md) | [sase-o9.4](sase-o9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`790cb61`](https://github.com/sase-org/sase/commit/790cb61ee128b097842616881b92dfa3f91cf46c) | feat(ace-tui): jump from a Procs pane monitor row to its agent with Enter | [sase-o9.4](sase-o9.4.md) | 2026-08-17 08:36:36 EDT |
