# Bead: sase-1h7.3 — Grammar, diagnostics, and persisted policy

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.3` · **Size:** medium
**Created:** 2026-10-06 18:17:37 EDT · **Closed:** 2026-10-07 09:19:41 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Previously Closed

> ↺ Closed 2026-10-07T02:33:22Z · done
>
> (none)
>
> Reopened 2026-10-07T11:59:11Z by a status update

## Description

contract: accept and strictly validate `for_epic=` on `%wait` with identical launcher and editor errors. Compute the effective positive `wait_for_epics_of` list (default still false), persist it in agent_meta.json and waiting.json and the scan wires, round-trip it through PromptWaitDirective, and add editor completion.

## Notes

[2026-10-07T02:33:04Z · sase-1h7.3--1] PROPOSED FOLLOW-UP: just check lint-symvision still reports _runs private-import in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py; both reproduce identically on the clean base tree (triage witness 05b9fc696a324977dde864aadd60a092)

[2026-10-07T02:33:22Z · sase-1h7.3--1] Verified: fixed NEW symvision private-import by renaming _durable_wait_names to public durable_wait_names; fixed missed completion assertion to include for_epic keyword; 96 targeted tests pass (wait_for_epic, directives_wait, macro contract, metadata, completion interactions); ruff, ruff format, and mypy clean on touched files; symvision shows only the 2 pre-existing base-tree _runs items (recorded as follow-up); no epic-symbol leftovers

[2026-10-07T03:48:34Z · sase-1h7.3--2] PROPOSED FOLLOW-UP: stale wait-completion expectations miss for_epic= — tests/ace/tui/widgets/test_directive_arg_completion.py (3 tests), tests/ace/tui/widgets/test_directive_completion_candidates.py::test_directive_completion_includes_representative_descriptions (argument_hint now ends for_epic=), tests/test_macro_directive_completion_parity.py::test_failure_degradation_retains_static_directive_rows; all fail only with this commit (sole for_epic commit in history), update expected rows to agent/bead/for_epic/hood/proc/time|unit per sibling updates in test_wait_directive_completion_interactions.py

[2026-10-07T03:48:49Z · sase-1h7.3--2] PROPOSED FOLLOW-UP: wire trailing-field test vs new wait_for_epics_of — tests/test_core_agent_scan_wire_agent_meta.py::test_finalizer_status_is_trailing_wire_field expects [-3:]==[proc_id,finalizer_status,created_epics] but this commit appends wait_for_epics_of after created_epics in AgentMetaWire; land agent to decide trailing order (interacts with 997b9e26ff created_epics) and update test

[2026-10-07T03:49:00Z · sase-1h7.3--2] PROPOSED FOLLOW-UP: full-check leftovers need clean-base triage — test_tui_app_import_stays_under_startup_budget at exact ceiling (3570<3570), test_foreground_run_records_context_usage_and_grant peak_tree_rss_kib==0, test_persist_monitor_result timing 2.11s vs 2.0s bound, zsh completion pty timeout; none reference wait content, verify on clean base before attributing

[2026-10-07T13:19:24Z · sase-1h7.3--1] PROPOSED FOLLOW-UP: full-check NEW flake tests/ace/tui/widgets/decks/test_deck_block_spread_pilot.py::test_block_spread_bracket_top_aligns — 5s pilot scroll_y settle timeout under full-suite load (loadavg ~40); passes in isolation on both working tree (3.6s) and clean base tree (2.35s); triage marks it touched=False with no owner; no wait/for_epic content involved

[2026-10-07T13:19:41Z · sase-1h7.3--1] Contract verified: for_epic= accepted/strictly validated on %wait with identical launcher+editor errors; effective wait_for_epics_of persisted in agent_meta.json/waiting.json/scan wires and round-tripped via PromptWaitDirective + editor completion. 63 targeted tests pass (wait, wait_for_epic, macro contract). Full check: only 1 NEW failure, deck spread-pilot scroll settle flake untouched by this bead (touched=False, no owner; passes isolated on tree and clean base); 2 KNOWN symvision _runs items pre-existing on base. No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.5](sase-1h7.5.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.3.md) | [sase-1h7.3](sase-1h7.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@21c539f`](https://github.com/sase-org/sase-core/commit/21c539fd30aff96530611f56903c5026e70ce3c3) | feat(wait): mirror wait\_for\_epics\_of in scan wires and editor grammar (sase-1h7.3) | [sase-1h7.3](sase-1h7.3.md) | 2026-10-06 22:35:05 EDT |
| sase | [`7c5fa40`](https://github.com/sase-org/sase/commit/7c5fa40d11f61c94b1dc34981a21232d2d56f143) | feat(wait): accept and validate for\_epic= on %wait with persisted wait\_for\_epics\_of (sase-1h7.3) | [sase-1h7.3](sase-1h7.3.md) | 2026-10-07 09:21:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.3--1][1] | Need the phase scope and design file | 4 |
| read-by | [agent:sase-1h7.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.land/README.md

<!-- sase:referenced-by:end -->
