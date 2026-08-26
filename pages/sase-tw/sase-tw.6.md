# Bead: sase-tw.6 — One derivation module behind one flag

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.6` · **Size:** medium
**Created:** 2026-08-25 15:34:39 EDT · **Closed:** 2026-08-25 18:27:06 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

derivation-core: add the Textual-free derivation module that turns facts SASE already owns into `derived` rows -- research-swarm `__a`/`__b` lineage and plan `bead_id:` frontmatter -- behind a beta feature flag, with no call sites yet.

## Notes

[2026-08-25T22:25:34Z · sase-tw.6] PROPOSED FOLLOW-UP: completion spec + CLI option snapshot drift after sase-tw.5 — tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift, test_current_structural_view_matches_checked_in_snapshot, and tests/main/test_artifact_handler.py::test_public_long_options_are_alphabetical_and_have_short_aliases (expects link subcommands [add, list, migrate-notes, rm], missing the landed `relation` subcommand) all fail on a clean master; likely needs `just sync-completion-spec` plus updating the artifact_handler expected-subcommand list.

[2026-08-25T22:25:53Z · sase-tw.6] PROPOSED FOLLOW-UP: tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections fails on a clean master — expects (Ctrl+J / Ctrl+K, "Cycle metadata through top") in the agents-pane keymap help bindings but it is missing; unrelated to sase-tw.6.

[2026-08-25T22:26:11Z · sase-tw.6] PROPOSED FOLLOW-UP: two agent-naming tests fail on a clean master — tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation (is_stale.call_count == 2, expected 1) and tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix (get_next_auto_name() returns "0" instead of "n" after single-char names before "m" are taken); unrelated to sase-tw.6.

[2026-08-25T22:26:34Z · sase-tw.6] PROPOSED FOLLOW-UP: two tests fail only under `just check`s full parallel scoped run but pass in isolation — tests/test_axe_process_start.py::test_ensure_recovers_unpublished_lock_holder_after_grace and tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo — likely order/parallel-dependent flakes; unrelated to sase-tw.6.

[2026-08-25T22:27:06Z · sase-tw.6] Added the Textual-free src/sase/artifact_links/derive/ package (DerivableDocument, DerivedLinkCandidate, derive_research_swarm_lineage for research __a/__b lineage, derive_plan_implements_bead for plan bead: frontmatter, and the derive_candidate_links fan-out entry point) plus the artifact_link_derivation beta flag (bead sase-tx) with its artifact_link_derivation_enabled() check helper for future call sites. No call sites yet, matching the phase scope. Verified: 16 new unit tests over fixture trees cover both rules' skip cases (no siblings, swarm-source-as-lead, non-matching kind, missing/blank/unresolvable bead field, invalid frontmatter) plus the flag's on/off states; just lint is fully green (fmt, ruff, mypy, feature-flags, symvision, etc.); just check's scoped lane escalated to the full suite (schema.json is a data asset) and surfaced 8 failures, all confirmed via git stash to be pre-existing on master and unrelated to this change (recorded as PROPOSED FOLLOW-UP notes on this bead).

## Dependencies

- **Blocks:** [sase-tw.10](sase-tw.10.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.3](sase-tw.3.md) ✓ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.5](sase-tw.5.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.7](sase-tw.7.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.6/README.md) | [sase-tw.6](sase-tw.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7015c79`](https://github.com/sase-org/sase/commit/7015c7938d984037447ed7de29ff952b5aab0650) | feat(artifact-links): add Textual-free derivation module behind a beta flag | [sase-tw.6](sase-tw.6.md) | 2026-08-25 18:28:07 EDT |
