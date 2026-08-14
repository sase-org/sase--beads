# Bead: sase-lz.4 — Documentation sync for selector authoring

[Bead Pages](../README.md) / [sase-lz](README.md) / sase-lz.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.4` · **Size:** small
**Created:** 2026-08-14 10:49:45 EDT · **Closed:** 2026-08-14 12:42:39 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

selector-docs: correct the ACE Models panel documentation that claims the custom input only accepts concrete model strings, document the builder row and its keys, state that temporary overrides refuse selectors, and cross-check the selector semantics and configuration references.

## Notes

[2026-08-14T16:42:20Z · sase-lz.4] PROPOSED FOLLOW-UP: `sase monitor start --command "just check" ...` failed with FamilyAttachError: Cannot create agent family 'sase-lz': resolved parent is named 'sase-lz.4' (src/sase/agent/_family_promotion.py:131 via monitor/start.py _resolve_lane_start). Reproduced while working phase bead sase-lz.4 in workspace sase_10; worked around by running just install/just check inline instead. Investigate promote_agent_to_family's parent-name resolution for phase-bead lanes named like sase-lz.4.

[2026-08-14T16:42:39Z · sase-lz.4] Corrected docs/ace.md (Temporary overrides: Custom... claim was wrong — Edit's Custom... also accepts typed selectors and now opens prefilled, plus documents the new 'Pool / fallback...' guided builder row and its keys a/d/J/K/E/t/enter/esc, seeding, two-member minimum, and live validation; Override refuses selectors with a message pointing at e; updated the e row of the key table) and docs/llms.md (selector semantics: Edit authors selectors directly, Override refuses outright rather than corrupting). Checked docs/configuration.md:1398-1420 — still accurate, left unchanged. Verified against the shipped code: models_panel_selector_builder.py, model_picker_rows.py (SELECTOR_SENTINEL/Pool / fallback... row), models_panel_alias_edit.py, models_panel_override.py's rejection message. just install && just check: prettier initially flagged the two edited docs, fixed with prettier --write; full check reran clean except tests/llm_provider/test_commit_finalizer_baseline.py::test_pre_existing_sibling_file_is_excluded_and_reported_separately, confirmed pre-existing/unrelated by reproducing the same failure on a clean git stash of master. Filed a PROPOSED FOLLOW-UP note on this bead for an unrelated sase monitor start FamilyAttachError bug hit while trying to run just check through /sase_monitor.

## Dependencies

- **Depends on:** [sase-lz.3](sase-lz.3.md) ✓ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.4/README.md) | [sase-lz.4](sase-lz.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d5598e`](https://github.com/sase-org/sase/commit/4d5598eaf4fffd6ba3c4f5904e95f7dbec4a9749) | docs(ace): correct selector authoring docs for Edit/Override and builder | [sase-lz.4](sase-lz.4.md) | 2026-08-14 12:43:46 EDT |
