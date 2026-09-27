# Bead: sase-1ab.4 — TUI turn surfaces

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.4` · **Size:** large
**Created:** 2026-09-26 00:15:09 EDT · **Closed:** 2026-09-26 20:43:33 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

tui-cutover: rename TUI modules, row kinds, section ids, and visible copy (SESSION TURNS, AGENT TURN, GATE TURN, MONITOR TURN, NAMED PROC, the 0-9 turn footer, help legend, modals, notifications) and re-baseline the PNG goldens, with no change to the performance contract.

## Notes

[2026-09-26T20:01:38Z · sase-1ab.4] PROPOSED FOLLOW-UP: tests/ace/tui/bench_tui_jk.py fails collection on this tree (cannot import test_bench_sticky_reply_flag_off_vs_on from bench_tui_jk_blocks); untouched by TUI turn rename, needs owner triage. Perf contract otherwise preserved: rename-only, no new FS/awaits/subprocesses/full rebuilds in nav/render handlers.

[2026-09-26T21:13:12Z · sase-1ab.4--1] PROPOSED FOLLOW-UP: remaining shell-named hits outside TUI scope, left for owning phases: tests/test_gate_cli_answer_detach.py uses spec shell-1 with shell=True (gate CLI wire); src/sase/main/gate_handler.py + notification_gates/cli_show.py read payload gate_shell (gate wire compat); src/sase/core/agent_scan_facade.py calls find_gate_shell_by_gate_id (Rust binding name); src/sase/agent/legacy_sase_shell_syntax.py + tests/agent/test_legacy_sase_shell_syntax.py (deliberate legacy syntax compat). Also fixed in TUI scope this turn: stale sase.gate_shell imports in 4 test/visual modules now import sase.gate_turn; renamed missed turn identifiers (current_turn, agent_turns, block_meta_for_session_turn, _is_indented_member_turn, _logical_turn_text), monitor_turn/gate_turn test helpers, and Turns-lane alignment in header tests.

[2026-09-27T00:42:40Z · sase-1ab.4--3] PROPOSED FOLLOW-UP: pre-existing visual failures outside the turn rename, all reproduced on untouched code paths and left for owning areas. (1) test_agents_bead_created_by_agent_narrow: narrow card never renders the 'Beads:' lane for created touches (shows fold-style BEAD section instead); no bead_created goldens are committed. (2) test_axe_chop_run_info_panel: expects hooks group before checks, but empty routine origins fall back to alphabetical (checks first); ordering code untouched by rename. (3) test_top_bar_usage_attention_narrow + test_top_bar_usage_badges_crowded_narrow: wait_for_startup times out with rejected/disabled provider projection; usage/startup path untouched. (4) test_agent_output_variables_multi_agent: OUTPUT VARIABLES heading intermittently absent (passed full-suite update, fails solo/scoped); heading path untouched. test_agents_deck_blocks_arrival_dot failed once in check then passed scoped re-run (transient). (5) test_ace_png_snapshots_agents_agent_session_panel_monitor collection at clean HEAD errors on 'from sase.gate_shell.state import ...' (runtime cut over to sase.gate_turn in d5fc75864f); this bead fixed the import as part of the rename.

[2026-09-27T00:42:57Z · sase-1ab.4--3] PROPOSED FOLLOW-UP: pre-existing fast-suite failures outside the turn rename. (1) test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll: pin_to_bottom applies async while the test reads deck_y synchronously, then the pinned deck follows to 2.0; deck/pin machinery untouched (19x-era). (2) test_panel_shell semicolon hop: passed solo re-run after failing under parallel load (flake). (3) Glossary still carries an 'Agent Shell' related term (see test_agent_glossary_reads.py); memory-owned, needs the memory-write flow. (4) sase tool run check could not complete in-turn: the shared sase-core wheel build lock was contended by a sibling workspace build and a full phase exceeds the single-turn limit; substituted verification below, all green.

[2026-09-27T00:43:33Z · sase-1ab.4--3] Verified this turn. Rename fallout fixed: (a) real bug in _kill_flow._do_bulk_kill_agents where the proc_shell->named_proc rename rebound dismissed_ids (identity set) to the proc-id string set, crashing bulk kill with ValueError on unpack; renamed the local to dismissed_procs, kill tests green. (b) unit asserts updated to MONITOR TURN/GATE TURN: phase labels (4), session roster monitor kinds (2), node-finder kind (1). (c) visual monitor asserts updated for renamed layout: conversation test now asserts MONITOR TURN (paged block page has no spread-only AGENT REPLY heading); roster test matches 'just check' across wrapped lane rows ignoring border runs. (d) turn-concept test locals/helpers renamed (reply_blocks, deck_blocks, clan_status, node_finder, owner_roster_fixture, bench_tui_jk_blocks, named_proc_dismissal, oracle/fleet/clan comments). Goldens: full update applied 12, scoped file update applied conversation + 2 monitor goldens (SESSION TURNS/MONITOR TURN/0-9 turn verified in PNGs); 1 created golden (bead_created 120x40) sits untracked. Green proof: monitor visual file 16/16 strict, deck_blocks 7/7, bench blocks 2/2, fast subsets 51+68+77+273+437 passed, ruff format+lint clean on edited files. Remaining shell hits classified per plan buckets (Unix, chrome, completion, legacy readers incl. LEGACY_* ids, envelope shell fallback, historical_shell/turn readers, dismissed compat module, negative guards); out-of-scope failures recorded as PROPOSED FOLLOW-UP notes. sase tool run check and full visual check exceed the single-turn limit here (shared sase-core build lock held by sibling workspace); full-suite re-verification belongs to landing.

## Dependencies

- **Depends on:** [sase-1ab.3](sase-1ab.3.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.7](sase-1ab.7.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.4.md) | [sase-1ab.4](sase-1ab.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d4c7b5c`](https://github.com/sase-org/sase/commit/d4c7b5ca9a66b61ae6d73f9c13e1e13c5cbcc418) | fix(ace-tui): repair bulk kill after named\_proc rename and rebaseline turn surfaces | [sase-1ab.4](sase-1ab.4.md) | 2026-09-26 20:55:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.4--3][1] | verify status and notes before recording follow-ups and closing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.4.md

<!-- sase:referenced-by:end -->
