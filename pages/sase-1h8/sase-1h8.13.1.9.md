# Bead: sase-1h8.13.1.9 — One mutation algorithm per entry point, with every suite in both modes

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.land`
**Created:** 2026-10-08 21:24:16 EDT · **Closed:** 2026-10-09 04:18:00 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/unify_bead_mutation_algorithms.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 6 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md

<!-- sase:links:end -->

## Description

Every ordinary bead mutation runs one algorithm over MutationView, on both the cached and the replay backing. The parallel MutableStore replay copies are deleted. The nine existing mutation suites run in cached and replay modes. Legacy and no-git stores keep their bytes, proven by goldens. The over-cap read-model files return to their pre-epic sizes. The landing of sase-1h8.13.1, and then of sase-1h8.13, can then resume.

## Notes

[2026-10-09T07:53:09Z · sase-1h8.13.1.9.land] LAND TRIAGE (sase-1h8.13.1.9.land, sase-core 2d009388, sase master bd830064ca, 2026-10-09). Outcome of every PROPOSED FOLLOW-UP:
(1) sase-1h8.13.1.9.3 #2, sase-core tool_run::store::tests::private_argv_is_not_serialized_on_queries load flake: DUPLICATE. Corroborated existing flake sase-17n with +1 (now +2).
(2) sase-1h8.13.1.9.4 #1 and sase-1h8.13.1.9.8 #1, replay goldens pin the wall-clock lock_wait_ms: EPIC-CAUSED and declined as a task. The replay_goldens phase added these goldens. All 82 goldens that carry lock_wait_ms pin 0, but the flock wait can read 1-18ms under parallel load. This goes to the remediation tale, which normalizes it without regenerating any golden.
(3) sase-1h8.13.1.9.7 #1, sase-core sase_macro_lsp metadata_env_ignores_legacy_prefix load flake: CREATED sase-1ik (flake, small). Root cause: project_tags.rs initialize_advertises_project_tag_palette mutates SASE_MACRO_VCS_PROJECT_CATALOG without the file-private ENV_SERIAL lock.
(4) sase-1h8.13.1.9.7 #2, six sase check failures:
  - test_macro_string_literals_avoid_xprompt_terms: DUPLICATE, +1 on sase-1hr (now +3).
  - test_directive_completion_includes_representative_descriptions and test_tab_through_every_subcommand_reaches_the_last_with_a_highlight: DECLINED as new tasks. They are owned by the uncommitted repairs in in-progress sase-1i5.9.1.2.1.7, the same routing sase-1ig.land used. All three still fail on bd830064ca (run 7d658c63, triage KNOWN).
  - Load flakes test_agy_usage_probe_collects_four_windows, test_cross_test_config_reader_is_reported_as_poisoning and test_click_opens_models_panel: no existing bead and no causal active epic. CREATED sase-1il, sase-1im and sase-1in (flake, large); sase-1il is related-linked to sibling flake sase-19m.
Also found while verifying the sase gate (not from a phase):
  - lint (test waits) in test_plan_decision_ace_stale.py:183,310 is already a DISCOVERED ISSUE on sase-1hi.10.7.6.
  - sase/memory/README.md token drift: init memory --check and test_repo_project_memory_notes_match_generator_output are deterministic red, caused by c58ae7491a. Recorded as a DISCOVERED ISSUE on sase-1id.
None of these failures touches files this epic changed.

[2026-10-09T08:18:00Z · sase-1h8.13.1.9.land] LAND (tale 202610/land_unify_bead_mutation_algorithms.md): all 8 phases closed; epic-symbols clean.

Single algorithm: every ordinary mutation entry point runs one closure through runner::run_mutation on both backings; no try_cached_* remains (grep: 0 hits).

Audit: MutableStore::load is reached only by view.rs load_replay (view.rs:186) and store.rs export_jsonl (store.rs:90). One mint helper: shared::mint_stream_event. No allow(dead_code) in view.rs.

Suites and goldens: 143 of 151 suite tests run in both modes, 8 stay replay-only with stated reasons (.9.1). 155 goldens byte-identical; cached-equals-golden holds (.9.2/.9.8). Verified this turn: bead::mutation 244 passed incl. replay_golden_bytes_are_pinned and cached_golden_bytes_match_replay; bead_read_model_mutation_proof 2 passed; goldens/ dir byte-identical (git status clean).

Caps and docs: read_model/store.rs 2047 lines, tail.rs 1317 (.9.7). docs/beads.md fixed in sase 9ed4b0fb93.

Bench: medians match or improve vs file:explicit:cf5bda21694e0423eeb52bd1; after-artifact file:explicit:8ca5f30ead916b9acacf577e. Full table in .9.8 note #2.

This tale's fixes (uncommitted working tree on sase-core HEAD 2d009388): (1) outcome_string in replay_goldens.rs zeroes outcome.lock_wait_ms before serializing (environmental flock-wait telemetry, cf. bead_read_model_mutation_proof precedent); module doc updated; no golden regenerated. (2) Pure move of the Case table (Case struct, case/control_case/remove_case/mk, upd_title..snz_cancel helpers, cases()) into new replay_golden_cases.rs (registered in tests/mod.rs, sorted); replay_goldens.rs 1522 -> 846 lines, replay_golden_cases.rs 702 lines; no macro_rules.

Checks: just fmt clean; just fast zero warnings; sase tool run check green (run 9cf66105568384cf112faf7137b2780a, 504s).

sase gate on clean master bd830064ca failed only where this epic never touched: lint (test waits) recorded on sase-1hi.10.7.6; sase/memory/README.md token drift on sase-1id; three KNOWN tests owned by sase-1hr and sase-1i5.9.1.2.1.7.

Triage: see LAND TRIAGE note: sase-17n and sase-1hr got +1s; sase-1ik, sase-1il, sase-1im, sase-1in created; lock_wait_ms handled here.

Integration: no post-start commit needs integration. sase-core HEAD == 2d009388 (nothing since). sase commits since bd830064ca are 3b3d876911 (plugin install/update lifecycle) and 6bc2a18bbc (ace-tui gate split) - install/ACE surface work, never bead mutation code. No sase pin move: no new binding called.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.9.land.md) | [sase-1h8.13.1.9](sase-1h8.13.1.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d2a954b`](https://github.com/sase-org/sase-core/commit/d2a954b056ef7ed30dee9b932f8fa0e702714446) | fix(bead): normalize lock\_wait\_ms in replay goldens and split golden case table | [sase-1h8.13.1.9](sase-1h8.13.1.9.md) | 2026-10-09 04:55:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.9.1][1] | epic decisions and symbols | 2 |
| read-by | [agent:sase-1h8.13.1.9.2][2] | epic scope and decisions | 1 |
| read-by | [agent:sase-1h8.13.1.9.3][3] | epic scope decisions | 1 |
| read-by | [agent:sase-1h8.13.1.9.4][4] | epic decisions and scope | 1 |
| read-by | [agent:sase-1h8.13.1.9.5][5] | epic decisions for claims-deps phase | 2 |
| read-by | [agent:sase-1h8.13.1.9.7][6] | epic decisions | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.7/README.md

<!-- sase:referenced-by:end -->
