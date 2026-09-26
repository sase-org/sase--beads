# Bead: sase-1ab.2 — Python persistence and wire cutover

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.2` · **Size:** large
**Created:** 2026-09-26 00:15:07 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

wire-cutover: bump the core pin and switch sase to the new binding names. Rename the Python wire mirrors and every durable key and value (agent meta, plan-gate meta and files, gate bundles, proc rows, runner-slot records, dismissed procs): new data is written only with turn/named-proc spellings, and readers accept both.

## Notes

[2026-09-26T13:49:25Z · sase-1ab.2--3] Verification status (sase-1ab.2--3): repaired the wire-cutover fallout instead of closing. Root causes fixed in src: (1) gate settlement followup_policy only read the legacy envelope shell block, so NO follow-up launched for new turn-block gates; now turn-first w/ shell fallback. (2) same single-spelling miss in 11 envelope shell-backed readers (service, cli_answer, decision, adapters, approval_projection, cli_wait, failure_notifications, plan_approval_response, mobile actions, user_question, launch_approval, TUI gate refresh). (3) monitor proc_adapter.proc_shell_owns only matched lifecycle proc-shell, so proc-service monitors stopped via the legacy path and rows wedged at settling; now uses is_named_proc_row (proven against base tree via stash: base passes, cutover failed, fix passes). (4) CLI usage-error heuristic keyed on the old 'named proc shell' validator wording; new core validator says 'named proc ...' (exit 1 vs 2); now matches 'named proc '. Tests: ~35 stale-caller files moved to new constructor kwargs (agent_session_turn, proc_name) and new-spelling output assertions (turn block/keys, turn_kind incl. proc->monitor normalization, gate_next_fork turn, named-proc lifecycle, named-proc: key prefix, proc_name JSON); private _rust_find_gate_turn_by_gate_id patches; added legacy-fallback assertion for capacity keys. PROPOSED FOLLOW-UP: just check was never green this turn -- selection escalates to FULL_SUITE (4393 files, rename-or-delete + stale baseline) and timed out at 1h and 3h in monitors; just recipes also now SIGTERM in _setup rebuilding sase_core_rs under host memory pressure (installed wheel imports fine; direct runners used instead). Remaining gates all green via direct runners: ruff check/format, mypy (5003 files), committed-plans, epic-symbols clean, ~1000 focused tests across every touched area. Contract-flip audit: core/health.py + bindings checks pass; no new schema-version hard errors observed beyond the known later-phase flip.

[2026-09-26T14:38:18Z · sase-1ab.2--5] Verification repair (sase-1ab.2--4): two remaining just-check failures fixed. (1) Justfile _lint-symvision: dropped stale --epic-symbol entries for closed sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading). (2) tests/test_agent_session_terminology.py NEW failure: docstring in agent_scan_wire_agent_session_turn.py named legacy agent_session_shell/family_shell identifiers; reworded to 'legacy pre-rename shell keys' -- targeted terminology tests green (13 passed). (3) 5 symvision NEW unused-public items in 19x code (ReadingAnchor, capture_reading_anchor, restore_block_offset, render_block_rail, block_rail_text) are intentional public API per plan:202609/agent_data_card_blocks.md but have no non-test consumer yet; deferred via --epic-symbol sase-19x.9 (IN_PROGRESS, goldens/bench/flag-removal owns this surface) with a Justfile comment -- that phase consumes, privatizes, or deletes them. just _lint-symvision green. No new schema-version hard errors or model_shell invalid_shell codes observed.

[2026-09-26T15:38:10Z · sase-1ab.2--7] Verification status (sase-1ab.2--7): full just check via monitor 7yb75jtfpv4z (sase tool run check, 21m51s) still red: 3 failed, 48044 passed, 19 skipped. All three failures are out of scope for the turn/named-proc wire cutover and this turn made no source edits: (1) tests/test_docs_getting_started_providers.py::test_getting_started_muse_grok_wording_separates_provider_selection -- docs/getting_started.md no longer contains the Grok Build alias-pool routing sentence; caused by closed phase sase-1aa.5.2 refresh_prose rewrite (see its note #2), not by this bead. git diff confirms no getting_started touch. (2) tests/ace/tui/widgets/test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll -- assert deck_scroll.scroll_y 2.0 == 0.0; no bead match for header scroll, diff touches no header/deck-scroll code. (3) tests/ace/tui/test_event_driven_pause_fixture.py::test_fixture_patch_does_not_leak_from_previous_test -- FLAKY per triage (assert _LEAK_SENTINEL is not None), routed as DISCOVERED ISSUE to active epic sase-j7. Per handoff instruction sase-1ab.2 stays OPEN; close only on a green check.

## Dependencies

- **Depends on:** [sase-1ab.1](sase-1ab.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.3](sase-1ab.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.2.md) | [sase-1ab.2](sase-1ab.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c051b9a`](https://github.com/sase-org/sase/commit/c051b9a31a3c91c329bb029ea6dcda0ef0ceb0db) | fix(turn-cutover): repair sase-1ab.2 verification fallout | [sase-1ab.2](sase-1ab.2.md) | 2026-09-26 10:02:24 EDT |
| sase | [`4ef7166`](https://github.com/sase-org/sase/commit/4ef7166481dbf359c1dae0ca4cb783d7398295dc) | test(1ab.2): repair proc-rename fallout in wire-cutover tests | [sase-1ab.2](sase-1ab.2.md) | 2026-09-26 11:39:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ab.2--3][1] | check remaining scope notes before verification repair | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.2.md

<!-- sase:referenced-by:end -->
