# Bead: sase-tw.10 — Finish the \`links:\` frontmatter inlet as an authoring path

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.10` · **Size:** medium
**Created:** 2026-08-25 15:34:42 EDT · **Closed:** 2026-08-25 19:20:46 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

frontmatter-inlet: give the orphaned Rust `links:` parser its production caller so an author can declare links in plan frontmatter, and make consumption remove the inlet so it never becomes a second editable copy of the row.

## Notes

[2026-08-25T23:18:09Z · sase-tw.10] PROPOSED FOLLOW-UP: Repair unrelated baseline tests surfaced by full just check - tests/test_keymaps_display_help.py::test_all_tab_help_guides_show_forward_jump_and_agents_metadata_sections, tests/test_agent_name_registry_rebuild.py::test_stale_proof_memo_invalidated_by_mutation, and tests/test_agent_names_auto_name.py::TestGetNextAutoName::test_dotted_suffix_reserves_prefix reproduce individually outside files changed for this phase.

[2026-08-25T23:20:46Z · sase-tw.10] Verified links frontmatter ingestion with pytest tests/test_plan_command_handler_metadata.py -q, pytest tests/sdd/test_referenced_by_refresh.py -q, pytest tests/test_plan_validate.py::test_facade_rehydrates_valid_tale_and_ordered_schema -q, cargo test -p sase_core links_frontmatter_is_accepted_as_a_transient_authoring_inlet, cargo test -p sase_core schema_is_ordered_and_contains_exact_phase_guidance, just _lint-symvision, and empty sase bead epic-symbols sase-tw.10. Ran just check; its full scoped suite still reports unrelated keymap/agent-name baseline failures, recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Blocks:** [sase-tw.14](sase-tw.14.md) ◐ · ⧖ 2026-08-25
- **Depends on:** [sase-tw.6](sase-tw.6.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.10/README.md) | [sase-tw.10](sase-tw.10.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b250011`](https://github.com/sase-org/sase/commit/b25001124a8bf49f2f0011cecdb417350a720436) | feat(artifact-links): consume plan links frontmatter | [sase-tw.10](sase-tw.10.md) | 2026-08-25 19:22:22 EDT |
| sase-core | [`sase-core@2664e20`](https://github.com/sase-org/sase-core/commit/2664e20e94979e81ec729f620e500f8fea07a9cb) | feat(plan): allow transient links frontmatter | [sase-tw.10](sase-tw.10.md) | 2026-08-25 19:23:13 EDT |
