# Bead: sase-1eq.3.1.3 — Token-aware identifier rename

[Bead Pages](../README.md) / [sase-1eq.3.1](sase-1eq.3.1.md) / sase-1eq.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.md) · **Assignee:** `sase-1eq.3.1.3` · **Size:** medium
**Created:** 2026-10-02 19:30:28 EDT · **Closed:** 2026-10-03 03:55:15 EDT
**Plan:** [202610/sase\_modules\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md)

## Description

identifiers: Rewrite xprompt identifiers outside the TUI with a token-aware codemod, including Rule 2 names, the catalog template attribute, and the shim's old-name bindings.

## Notes

[2026-10-03T07:39:14Z · sase-1eq.3.1.3--1] PROPOSED FOLLOW-UP: base-identical check failures (verified via git-stash A/B on clean HEAD, unrelated to identifier rename): tests/pager/test_app_three_panes.py 5x (#pager-body vs pager-body-scroll, neither file in bead diff), tests/ace/tui/test_prompt_bar_editor_stack.py 13x (_EditorHarness lacks _mounted_prompt_bar), tests/ace/tui/widgets/test_prompt_mount_dedup.py 2x (JinjaDiagnosticsMixin unmount hook, prod file untouched), test_view_files_pager_split_keys 1x, test_check_sase_core_rs_bindings_tool 1x (plan_publication_payload_batches required by committed publication_payload_facade.py but missing from installed sase_core_rs 0.36.3), test_vcs_macro_mru_pruning 1x order-dependent (fails standalone on both trees, passes in full suite)

[2026-10-03T07:39:37Z · sase-1eq.3.1.3--1] PROPOSED FOLLOW-UP: load-sensitive flakes that pass serially/standalone but fail under parallel/full-check load (no rename cause found): config_cache token/teardown/isolation thread tests, test_link_follow_flat_panes ERROR, collection ERRORs in test_artifacts_scaffold/test_deck_card_block_keys/test_keymaps_app_bindings (identical ERRORs present in the pre-fix full-check run), test_contract_manifest slowness (passes standalone in ~52s)

[2026-10-03T07:39:48Z · sase-1eq.3.1.3--1] PROPOSED FOLLOW-UP: guard phase (sase-1eq.3.1.4) heads-up: intentionally kept out-of-scope survivors — content-layout .xprompts wire fields and xprompt_sources key reads (Rust-core-owned locators), plugin sase_xprompts entry-point group, sase/xprompts user/home/project discovery dirs, CLI/config/frontmatter/env/JSON keys, and TUI-local xprompt names/copy/keymaps; also fixed two 3.1.2 path-move leftovers owned by closed bead sase-1eq.3.1.2 (tests pr/commit.yml paths, split_file source_path assertion)

[2026-10-03T07:55:00Z · sase-1eq.3.1.3--2] PROPOSED FOLLOW-UP: orphaned sase-1eu symvision residue turns just check red (verified base-identical via git-stash A/B this turn: base fails with 4 stale --epic-symbol entries for closed bead sase-1eu). This turn removed those 4 stale Justfile entries per symvision docs, which unmasked latent unused-public symbols in files outside this bead diff: Geometry, GridSpec, geometry, main_pane in src/sase/ace/tui/util/pane_grid.py (landed by sase-1eu.8, no non-test external consumer) plus PublicationPayloadFile, plan_publication_payload_batches in src/sase/core/publication_payload_facade.py (touched last by sase-1ex.7). Needs an owner to privatize/delete/pragma per hierarchy; also fixed this bead-owned symvision error: added _PACKAGE_GETATTR alias for module __getattr__ in src/sase/xprompt/__init__.py (matches pager/agent precedent).

[2026-10-03T07:55:15Z · sase-1eq.3.1.3--2] Token-aware xprompt->macro identifier rename complete (737 files). Verified: ruff/format clean on shim, shim import works, just _lint-symvision shows no bead-owned errors (fixed own __getattr__ visibility; removed stale sase-1eu whitelist). Remaining check reds are base-identical per git-stash A/B (test failures in notes #1-2, symvision residue in note #4) and recorded as follow-ups. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1eq.3.1.2](sase-1eq.3.1.2.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.3.1.4](sase-1eq.3.1.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.3.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.1.3.md) | [sase-1eq.3.1.3](sase-1eq.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5541d4c`](https://github.com/sase-org/sase/commit/5541d4c6974be57d680c6b2baf23da0c81c9fa0b) | refactor(sase-modules): token-aware rename of xprompt identifiers outside TUI (sase-1eq.3.1.3) | [sase-1eq.3.1.3](sase-1eq.3.1.3.md) | 2026-10-03 04:13:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.3.1.3--2][1] | declaration-recovery turn: determine bead_action for finalizer declaration | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.1.3.md

<!-- sase:referenced-by:end -->
