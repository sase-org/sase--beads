# Bead: sase-1h8.13.1.9.7 — Shrink the over-cap read-model files and fix the stale phase-approval docs

[Bead Pages](../README.md) / [sase-1h8.13.1.9](sase-1h8.13.1.9.md) / sase-1h8.13.1.9.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) · **Assignee:** `sase-1h8.13.1.9.7` · **Size:** small
**Created:** 2026-10-08 21:24:22 EDT · **Closed:** 2026-10-08 23:28:48 EDT
**Plan:** [202610/unify\_bead\_mutation\_algorithms.md](https://github.com/sase-org/sase--plans/blob/main/202610/unify_bead_mutation_algorithms.md)

## Description

caps-docs: move the read-model functions that publish-direct changed out of read_model/store.rs (2,174 lines, 2,099 before the epic) and read_model/tail.rs (1,554, 1,519 before) into new files, so tail.rs is at or under 1,500 and store.rs at or under 2,099; in sase, fix the docs/beads.md sentence that still says phase agents auto-approve epic-tier plans.

## Notes

[2026-10-09T03:28:10Z · sase-1h8.13.1.9.7] PROPOSED FOLLOW-UP: sase-core check hit load flake server::tests::macro_lsp::metadata_env_ignores_legacy_prefix (SASE_MACRO_VCS_PROJECT_CATALOG wins assertion); passes alone and full-crate 242/242 — needs sase-core flake bead

[2026-10-09T03:28:25Z · sase-1h8.13.1.9.7] PROPOSED FOLLOW-UP: sase check (31min full lane, 53998 passed) has 6 pre-existing failures unrelated to caps-docs docs-only change, 3 reproduce on clean base (test_macro_string_literals_avoid_xprompt_terms xprompt literal in tests/test_plugin_commands_mount.py; test_directive_completion_includes_representative_descriptions; test_tab_through_every_subcommand_reaches_the_last_with_a_highlight) and 3 pass alone as load flakes (agy_usage_probe, config_reader_poisoning, click_opens_models_panel)

[2026-10-09T03:28:48Z · sase-1h8.13.1.9.7] caps-docs done: pure move of publish-direct-touched helpers into new read_model/resume.rs (TailLoadPlan/tail_load_plan/IssueIndex/load_issue_index/load_rows/query_dependents/gate_manifest_config/tail_merge_key), refresh.rs (RefreshFinish/refresh_changed_store), meta_keys.rs (tail_meta_defaults/backfill_meta_keys/set_token_in_txn); store.rs 2174->2047 (cap 2099), tail.rs 1554->1317 (cap 1500); docs/beads.md phase-approval sentence now says epic-tier plan parks for human review under %auto:tale. Verified: just fmt+fast clean; read_model unit 20/20, mutation 240/240, bead_event_parity 35/35, mutation_proof 2/2, read_model_parity 6/6, bead_read_parity 16/16, sase_core_py 297/297; sase-core check green except one macro_lsp env load flake (passes alone, 242/242 crate); sase check lint+fmt green, 53998 passed with 6 pre-existing failures (3 reproduce on clean base, 3 pass-alone flakes), all recorded as PROPOSED FOLLOW-UP. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1h8.13.1.9.8](sase-1h8.13.1.9.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.9.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.7/README.md) | [sase-1h8.13.1.9.7](sase-1h8.13.1.9.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5c4033f`](https://github.com/sase-org/sase-core/commit/5c4033f6d2284eaf717795c5cfc892e12827d510) | refactor(bead-read-model): split over-cap store and tail into resume, refresh, and meta-keys modules | [sase-1h8.13.1.9.7](sase-1h8.13.1.9.7.md) | 2026-10-08 23:30:49 EDT |
