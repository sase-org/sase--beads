# Bead: sase-js.2 — Retire the ref xprompt surface

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.2` · **Size:** medium
**Created:** 2026-08-11 13:21:13 EDT · **Closed:** 2026-08-11 15:30:20 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

retire: delete the `#ref/<kind>` xprompt adapter, its packaged renderer bodies, the synthetic source schemes, the precedence table, and the catalog, completion, LSP, and docs surfaces built on it, falling builtins back to hardcoded rendering.

## Notes

[2026-08-11T19:29:30Z · sase-js.2] PROPOSED FOLLOW-UP: just check-full flagged 6 pre-existing reproducible flakes unrelated to this phase (verified they pass cleanly in isolation, and none touch xprompt/artifact-ref code): tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection, tests/test_core_vcs_log.py::test_classify_origin_matches_python_golden[three params], tests/test_core_vcs_log.py::test_parse_computes_auto_origin_from_footer, tests/test_core_vcs_log.py::test_parse_computes_origin_from_footer. These exceed tests/reproducible_flake_baseline.txt and block just check-full (just check itself is clean). File beads to investigate timing/concurrency flakiness or add to the baseline with owners.

[2026-08-11T19:30:20Z · sase-js.2] Retired the #ref/<kind> xprompt adapter end to end, on its own so it reviews and ships independently of the sibling phases.

sase repo (56 files, -1521 net lines): deleted src/sase/xprompts/refs/*.md, xprompt/loader_refs.py, the ref/ref_kind/ref_sidecar_role/ref_path_globs/ref_shadowed_sources fields on XPrompt/Workflow and every catalog wire that carried them (ACE completion, mobile helper catalog, CLI show/list, xprompt LSP launcher env), the #ref/ rewriting in artifact_ref_prompt_parsing.py, the sase/refs/ source enumeration in content_layout.py/resolve_ref_file_sources, #ref/ completion across prompt_catalog.py and a dozen ACE widget files, the xprompt_browser_helpers.py synthetic-source cases, reject_misplaced_ref(), the sidecar_ref_config:/generated_sidecar_ref: source schemes, and the seven-level renderer precedence table. Builtins now fall back to the pre-sase-ho hardcoded _legacy_replacement_text path in artifact_ref_prompt_rendering.py (byte-identical output for agent/bead/chat/file/commit/bug; document-kind refs like @plans:/@research: now render as @<resolved_path> instead of the old 'the X file in the Y sidecar repo' sentence — an explicit, plan-sanctioned temporary regression until the registry/builtins phases land the new provider projection). Kept and left unchanged exactly per the design doc: artifact_ref/filter.rs equivalents, ArtifactRefDocumentRootWire/ArtifactRefContextWire, and effective_sidecar_ref_policies's shape (including its still-tested .xprompt field, since dropping it is explicitly phase-4.3 registry work). Updated docs/xprompt.md, docs/content_layout.md, docs/plugins.md (the three the plan named); docs/editor.md, getting_started.md, llms.md, configuration.md are explicitly phase-4.9 adopt-phase work and left untouched. Retired test_xprompt_ref_sources.py, test_artifact_ref_xprompt_integration.py, tests/artifact_refs/test_preprocessing_rendering.py wholesale; surgically updated ~15 other test files (content_layout, mobile helpers, cli_show_resolve, ACE completion widgets, LSP env) to match.

sase-core repo (17 files, -1053 net lines): removed the #ref/<kind> catalog loading (CatalogXprompt/StructuredSource.ref_kind, CatalogLoader's ref dirs/plugin dirs/ref_issues, load_refs_from_dir, load_plugin_refs, ref_directory_sources, canonical_ref_input), the RefSourceWire/ref_sources content-layout source enumeration and RefPlacementRuleWire/RefPlacementIssueWire namespace-policing types (kept the refs: LayoutPath directory-location field and REF_DIRECTORY_SEGMENT, out of scope), the MobileXpromptCatalogEntryWire/XpromptAssistEntry.ref_kind wire fields and editor::completion's build_xprompt_ref_arg_completion_candidates seam, and the mirrored LSP dispatch/tests in sase_xprompt_lsp. Regenerated the checked-in sase_gateway contract snapshot. No wire-schema version bump: field removal is a backward-compatible shrink, not a breaking add.

Verified: cargo check/test --workspace on sase-core is 100% green (1500+ tests, 0 failed). just check on sase (fmt/lint/symvision/mypy/scoped-tests) is 100% green after a fresh just install rebuilt sase_core_rs from the edited linked checkout. just check-full's broader run also passed the full test suite; its one failure (the flake-baseline gate) is 6 pre-existing reproducible flakes in unrelated VCS-log/contract-manifest tests, confirmed to pass cleanly in isolation and noted as a PROPOSED FOLLOW-UP, not a regression from this change.

[2026-08-11T19:31:19Z · sase-js.2] Retired the #ref/<kind> xprompt adapter (sase-ho design). sase repo: 56 files changed — deleted loader_refs.py, packaged refs/*.md renderers, and the ref_kind/ref_sidecar_role/ref_path_globs/ref_shadowed_sources fields threaded through ACE completion widgets, mobile helper bridge, CLI show/list, and the #ref/ rewriting machinery; builtins fall back to the pre-sase-ho hardcoded rendering path. sase-core repo: 17 files changed — removed matching Rust catalog-loading, content-layout ref-source enumeration, and namespace-policing types while preserving ArtifactRefDocumentRootWire/ArtifactRefContextWire/effective_sidecar_ref_policies shapes. Verified: cargo test --workspace 100% green; just check 100% green; just check-full's only failure was 6 pre-existing unrelated flaky tests (confirmed passing in isolation) — recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-js.3](sase-js.3.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-js.2/README.md) | [sase-js.2](sase-js.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e2cacbe`](https://github.com/sase-org/sase/commit/e2cacbe34ce16e3df92dc390ea11376972da5c77) | refactor(xprompt)!: retire the #ref/\<kind\> contextual renderer adapter | [sase-js.2](sase-js.2.md) | 2026-08-11 15:33:12 EDT |
