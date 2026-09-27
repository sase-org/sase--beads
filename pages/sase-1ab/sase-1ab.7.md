# Bead: sase-1ab.7 — sase-core contract flip

[Bead Pages](../README.md) / [sase-1ab](README.md) / sase-1ab.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ss](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ss.md) · **Assignee:** `sase-1ab.7` · **Size:** medium
**Created:** 2026-09-26 00:15:13 EDT · **Closed:** 2026-09-26 22:56:31 EDT
**Plan:** [202609/sase\_turn\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_turn_rename.md)

## Description

contract-flip: breaking feat! sase-core change. Serialize the new key and value names, drop the legacy binding names, rename the gate_turn_id index column, bump the changed schema versions and the fleet protocol, and prove current sase master still passes against the new core before landing.

## Notes

[2026-09-27T02:55:14Z · sase-1ab.7--1] PROPOSED FOLLOW-UP: fleet parity/projection fixtures still feed legacy row_kinds (agent_shell/historical_shell) — owned by sase-1ab.8 pin-bump; tests/ace/tui/test_fleet_agents_display_parity.py::test_project_fleet_agents_render_like_local_rows_modulo_host_chip and test_fleet_agents_projection_agent_session_tree.py::test_project_fleet_agents_drops_container_plus_concrete_duplicates fail against the flipped core (emits agent_turn/historical_turn via fleet_normalize_federation_response) and cannot pass against both cores with exact-match asserts

[2026-09-27T02:55:28Z · sase-1ab.7--1] PROPOSED FOLLOW-UP: 14 stale shell-spelling test expectations from earlier turn-rename phases fail identically on the clean base tree (verified via git-stash targeted rerun, no core involvement): tests/main/test_parser_proc.py (5: --shell/-N mapping, named-proc-shell help), tests/test_keybinding_footer_agent.py (3: shell digit label), tests/test_gate_cli_show.py::test_show_rejects_neither_ref_nor_id_and_kind (gate-shell), tests/agent/test_legacy_agent_family_syntax.py::test_gate_help_lists_only_canonical_next_fork_value (--next-fork shell), tests/test_dynamic_agent_session_root_zero_suffix.py (AGENT SHELL header), tests/test_agent_session_wire_mirrors.py::test_scan_wire_json_emits_only_new_spellings (self-contradictory: asserts agent_session_turn present then lists it as legacy), tests/test_procs_models_surface.py (stale __all__), tests/ace/tui/widgets/test_agent_header_panel.py::test_expanded_overflowing_header_claims_half_page_scroll (scroll math)

[2026-09-27T02:55:44Z · sase-1ab.7--1] PROPOSED FOLLOW-UP: lint lanes fail identically on the clean base tree (triage verdict KNOWN with witnesses 50b8ebe46608c2e340787d08360f25d8/a3cf3cd395fb68df8648a2c3913a5b6a): mypy 4 errors (agent_groups/_tree.py no-redef/arg-type x3, _agent_display_hint_sections.py LEGACY_NAMED_PROC_SECTION_ID) and symvision 16 unused-public-symbol reports; untouched by this phase

[2026-09-27T02:56:31Z · sase-1ab.7--1] contract-flip verified: core emits turn/named-proc spellings (scan-11, index-34, proc-4, fleet-contract-7, runner-7, hold-3, launch-plan-3, dispatch-2, fleet-protocol-3 confirmed in checkout), legacy bindings removed (asserted absent: find_gate_shell_by_gate_id + validate_standalone_proc_shell_name gone, turn/named-proc canonical present), gate_turn_id column + index v34 migration, fleet+sase-spec goldens regenerated; sase-core gate green (tool run 1ebf1c573aa9fd3c776d5d996d2a073e, core untouched since). Sase dual-compatible fixes with NO mirror bumps: validate probe accepts scan 10|11 and proc-shell|named-proc lifecycles with core-aware reserve version; bindings audit exempts the 2 removed legacy fallback names; added SUPPORTED index/scan/proc version sets; version asserts loosened to set membership (facade x2, scan_options, scan_records, var_integration); conflict regexes accept shell_name|proc_name (service, facade); dispatch test uses core-reported version; proc JSON key asserts corrected to named_proc (src-emitted). Targeted proof: 108 tests across 11 files green, ruff+mypy clean on touched files. Residual red recorded as PROPOSED FOLLOW-UPs on this bead: fleet parity/projection fixtures need new spellings (sase-1ab.8 owns), 14 stale shell-spelling expects + header scroll test fail identically on base, KNOWN lint (4 mypy + 16 symvision). Pin-bump (sase-1ab.8) mirrors: agent_scan_wire_records AGENT_SCAN 10->11 and INDEX 33->34, procs/models/common PROC 3->4, dispatch/models FLEET_PROTOCOL 2->3, agent_launch_wire_records LAUNCH_PLAN 2->3, validate_sase_core_rs probes, sase-core-revision.txt

## Dependencies

- **Depends on:** [sase-1ab.4](sase-1ab.4.md) ✓ · ⧖ 2026-09-26
- **Depends on:** [sase-1ab.6](sase-1ab.6.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ab.8](sase-1ab.8.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.7.md) | [sase-1ab.7](sase-1ab.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55e9e96`](https://github.com/sase-org/sase/commit/55e9e96decd7e1bf8f9e2524994597a80cd73e56) | feat(turn-rename): accept sase-core contract-flip spellings and schemas dual-compatibly | [sase-1ab.7](sase-1ab.7.md) | 2026-09-26 22:58:52 EDT |
