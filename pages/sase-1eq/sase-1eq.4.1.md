# Bead: sase-1eq.4.1 — Complete the non-TUI macro syntax cutover

[Bead Pages](../README.md) / [sase-1eq.4](sase-1eq.4.md) / sase-1eq.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.land`
**Created:** 2026-10-03 05:59:56 EDT · **Closed:** 2026-10-03 13:11:57 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/macro_syntax_cutover.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md

<!-- sase:links:end -->

## Description

Make macro spellings canonical across non-TUI SASE surfaces while preserving flag-gated authored aliases and unconditional durable readers.

## Notes

[2026-10-03T16:13:16Z · sase-1eq.4.1.land] LAND FOLLOW-UP TRIAGE (sase-1eq.4.1.land): (1) .1 #1 symvision history_only_node/instruction_display_for_subject_id: DECLINED - no longer flagged at 9f8c4c529e (later memory-pane splits gave them consumers). (2) .2 #1/#2, .3 #1, .5 #3 (PublicationPayloadFile/plan_publication_payload_batches): NOT EPIC-CAUSED - 5c7e7514ae (sase-1ex.7) facade calls a binding that does not exist in sase-core; reproduces on pre-epic base e847b082c2; already owned by active epic sase-1ex (prior DISCOVERED ISSUE notes) - appended corroborating DISCOVERED ISSUE to sase-1ex incl. Master Gate lint 'Check pinned core bindings' failure; no new task. (3) .4 #1/#2 snippet loader 2-vs-3-arg fake: EPIC-CAUSED (6d0d8a0a2d added the accept_legacy arg) - remaining epic work. (4) .4 #3 test_project_beads_skips_when_store_is_absent: duplicate of ready task sase-14o, +1 recorded (repro at HEAD and pre-epic base). (5) .5 #2 mypy EntryPoints.get in checks_config_retired.py:322: EPIC-CAUSED (4f90695659) - remaining epic work. (6) .5 #3 discover_macro_plugin_entry_points unused: EPIC-CAUSED (6d0d8a0a2d) - remaining epic work. (7) .5 #4 test_load_launchable_prunes_provider_mismatched_prefix: duplicate of ready CI task sase-172, +1 recorded (fails on pre-epic base). (8) .5 #5 toobig: the only violation is tests/ace/tui/visual/test_ace_png_snapshots_memory_pane_history_states.py (memory pane, not this epic) - DECLINED, owned by the toobig_split routine. (9) Discovered launch_context rebroadcast load flake: already proposed by sase-1ex.2 #1 for the active sase-1ex land; corroborated on sase-1ex, no task.

[2026-10-03T16:13:39Z · sase-1eq.4.1.land] LAND VERIFICATION (sase-1eq.4.1.land): all 5 phases closed, epic-symbols empty, core pin f50782f7 contains 4eb40d59 (normalize_macro_config_layer binding), flag legacy_xprompt_syntax present, doctor config.retired_xprompt_names runs in both states, sase path macros-* targets exist, sase macro list JSON emits type/kind macro, flag-off sase xprompt / path xprompts-dir exit 2 with retirement errors. REMAINING EPIC WORK found by sase tool run check cb133f344288ad1e9dada5423ff1f722 (full lane, 28 failed) cross-checked against pre-epic base e847b082c2 (scratch worktree): 26 failures are epic-caused and also red on Master Gate run 37134560139. Product regressions: TUI Admin Center XPrompts Enter/Ctrl+I load is dead because xprompt_browser_actions.action_edit_xprompt still compares item.kind to 'xprompt' after workflow_kind_value switched to 'macro'; run_policy._STDIN_PATHS still lists ('xprompt','expand'); mypy EntryPoints.get in doctor/checks_config_retired.py; symvision discover_macro_plugin_entry_points; plan-required hiding not met (sase --full-help lists 'macro (xprompt)', sase path --help advertises xprompts-* choices). Stale tests: export_save (7), %macros_enabled writer expectations (gate_turn 2, question_gate_turn 1, plan followup 1, fork_workflow 5), skill-source hint, reads.md move, root help, shadows-macro warning, arg-assist kind, bash smoke fixture kind, snippet fake loader arity. Integration: CI-only parity suites fail because tests/_macro_directive_completion_parity_lsp_session.py hard-codes sase-xprompt-lsp (CI installs only sase-macro-lsp; pre-existing but should use the epic's canonical-first binary policy; strings-guard whitelisted it). Non-epic commits since start (fd62e962c7, 90193a05d5, 3289046531, 8f910d559b, memory-pane splits) need no changes here; docs/xprompt.md auto_xprompt_menu prose belongs to sase-1eq.6; sase-nvim (1eq.9) only matches workflow kinds and uses the still-accepted sase xprompt list alias.

[2026-10-03T17:11:57Z · sase-1eq.4.1.land] macro cutover landing: fixed TUI admin load (canonical macro kind), save destinations (macros.write_path, single p/h rows), browser classification (macros layout, canonical labels), run_policy stdin table, mypy entry_points(group=), privatized macro entry-points discovery, root-position normalization (xprompt->macro, xprompts-dir/schema->macros-*) with both-flag-state tests; updated stale expectations (export_save macros paths, %macros_enabled writers incl preserved legacy input in deferred fork test, skill hint home/sase/macros, reads.md sase/macros path and unescaped helpers, root help macro wording, shadows macro, arg-assist kind macro, bash macro fixture, snippet loader 3rd arg); LSP canonical-first binary with fallback; refreshed 21 visual goldens (macro save/location flows, config_center, frontmatter, jump, preview, agents); focused suites green (253 tests incl terminology); live checks pass (macro list type macro, path macros-* exist, doctor clean both states, flag-off exits 2, help clean); check run 2bf7ef819af8c377ea80bac84cc7543e joined to monitor

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.land.md) | [sase-1eq.4.1](sase-1eq.4.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bca08d1`](https://github.com/sase-org/sase/commit/bca08d1242e025bbc60d2cbba54231ed8aa532bc) | feat(macro): land macro syntax cutover implementation | [sase-1eq.4.1](sase-1eq.4.1.md) | 2026-10-03 14:17:57 EDT |
| sase--plans | [`sase--plans@83bd226`](https://github.com/sase-org/sase--plans/commit/83bd226f816b3d23ec6584df897cfee385d81c75) | docs(plans): record macro syntax cutover plan | [sase-1eq.4.1](sase-1eq.4.1.md) | 2026-10-03 14:23:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.3][1] | Need parent epic scope | 1 |
| read-by | [agent:sase-1eq.4.1.4][2] | parent scope | 1 |
| read-by | [agent:sase-1eq.4.1.land--1][3] | macro cutover landing follow-up: need land verification notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.1.land.md

<!-- sase:referenced-by:end -->
