# Bead: sase-1d7.3 — Trace spans, leader-key perf capture, and unread/idle benches

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.3` · **Size:** small
**Created:** 2026-09-30 07:18:09 EDT · **Closed:** 2026-09-30 08:23:15 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

unread-instrumentation: add tui_trace spans and SASE_TUI_PERF key-to-paint capture for leader unread keys, plus unread and idle-tick bench scenarios that record the baseline later phases compare against.

## Notes

[2026-09-30T12:21:21Z · sase-1d7.3] Baseline (sandbox host, shared-load; 220 loaded/153 visible rows, 20 clan containers, 3 tribes; later phases compare against these, not the generous committed ceilings): ,u key-to-paint p50/p95/max ms: visible 106.12/124.62/124.62, collapsed_panel 74.42/99.56/99.56, collapsed_clan 77.93/86.33/86.33, off_tab 51.77/83.72/83.72 (n=10). ,j: visible 100.39/109.13/109.13, collapsed_panel 92.57/208.73/208.73, collapsed_clan 96.13/112.03/112.03, off_tab 102.86/109.11/109.11 (n=8; 2 off-tab jumps recorded as agents_tab_switch 175.57/178.04/178.04 since the switch starts its own sample). Idle 1Hz tick (134 rows patched): 73.15/133.61/358.03. fleet_refresh unchanged (signature skip-path still reprojects today): 80.78/104.09/124.12. fleet_refresh forced: 97.94/159.75/166.89. All far above the 16ms R4 budget, confirming the epic diagnosis.

[2026-09-30T12:22:27Z · sase-1d7.3] PROPOSED FOLLOW-UP: symvision gate fails on clean base tree: src/sase/bead/show_images.py imports private _kitty_graphics_support from src/sase/doctor/checks_deep_terminal.py (untouched by this phase); needs making public or a pragma.

[2026-09-30T12:22:41Z · sase-1d7.3] PROPOSED FOLLOW-UP: patch/stitch terminology audit flags 14 pre-existing defects in sase-core sidecar fixtures (note_attachment at_bearing_notes.jsonl); none from this phase.

[2026-09-30T12:23:15Z · sase-1d7.3] Done: 5 tui_trace spans (leader.unread_bulk_ack, leader.unread_jump, unread.ack_complete with worker-thread store_bytes, unread.reconcile, agent_nodes.projection_index), SASE_TUI_PERF capture for ,u/,j/,J, new bench_tui_jk_unread (,u/,j x 4 branches) re-exported from bench_tui_jk, idle tick+fleet scenario in bench_tui_trace, runbook recipe, 5 new span tests. Verified: ruff+format+mypy clean on changed files; 119+60+139 existing tests pass incl. unread/tab/leader suites; new benches pass with baselines in bead note (all over 16ms budget as diagnosed). Full just check blocked by cold sase-core Rust rebuild exceeding sync limit (environmental); symvision+terminology failures are pre-existing on untouched files, filed as follow-ups.

## Dependencies

- **Blocks:** [sase-1d7.10](sase-1d7.10.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.11](sase-1d7.11.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.3/README.md) | [sase-1d7.3](sase-1d7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d6f2b23`](https://github.com/sase-org/sase/commit/d6f2b237a6a48b5290d7356dfeb0c63f62b14a58) | feat(tui): instrument unread paths with tui\_trace spans and key-to-paint benches | [sase-1d7.3](sase-1d7.3.md) | 2026-09-30 08:27:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.3/README.md

<!-- sase:referenced-by:end -->
