# Bead: sase-1q4.8 — Show and edit bound turns in the TUI

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.8` · **Size:** medium
**Created:** 2026-10-30 17:43:14 EDT · **Closed:** 2026-10-31 05:20:55 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

wait_tui: surface bound turns via an additive scan-wire field, accept turn= entries in the agent Wait modal, and disable follow-epics for turn targets.

## Notes

[2026-10-31T09:12:44Z · sase-1q4.8] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt after the wait_turn_bindings scanner commit lands on sase-core master — pin already matches remote HEAD 80f5af40 so this phase cannot ratchet uncommitted core work

[2026-10-31T09:20:55Z · sase-1q4.8] wait_tui: additive wait_turn_bindings scan-wire, TUI bound-turn labels, Wait modal turn= authoring, bind-new-at-apply, follow-toggle disable for turn/plan-only remaining targets. Verified: sase-core sase tool run check green; rust wait_turn + history_only_fork tests; wait_modal_turn pytest; targeted PNG wait_modal_100x32 and wait_modal_beads_focused_100x32 updated (placeholder agent, turn=other), inspected vs prior frames, TZ=UTC --check twice clean with no unstable; epic-symbols none leftover; just _lint-symvision green after durable_wait_names public rename.

[2026-10-31T09:53:00Z · sase-1q4.8--1] Repaired just check NEW failures after wait_tui close: deferred agent_scan_wire_markers_wait_turn off TUI first-paint (import budget 2860/2861) and reviewed _bind_new_turn_wait_records marker-path site. Flaky agents_sync handle_agents_sync NameError is unrelated.

## Dependencies

- **Depends on:** [sase-1q4.7](sase-1q4.7.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q4.8.md) | [sase-1q4.8](sase-1q4.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dddcb0b`](https://github.com/sase-org/sase-core/commit/dddcb0b712600b5635df5bed91e1220c0b2bd31d) | feat(agent-scan): project wait\_turn\_bindings on scan wire | [sase-1q4.8](sase-1q4.8.md) | 2026-10-31 07:10:33 EDT |
| sase | [`4a4b6fe`](https://github.com/sase-org/sase/commit/4a4b6fede82aff9cdab6a29a8cfc1d993cf4dadb) | feat(tui): surface and edit bound turn waits | [sase-1q4.8](sase-1q4.8.md) | 2026-10-31 07:11:46 EDT |
