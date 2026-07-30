# Bead: sase-b3.9 — Docs, core floor bump, and end-to-end verification

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.9

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.9` · **Size:** small
**Created:** 2026-07-30 08:18:46 UTC · **Closed:** 2026-07-30 10:32:25 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

land: update the editor and ace docs plus the sase-nvim completion table, raise the published sase-core-rs floor, and run the acceptance and performance verification listed for the epic.

## Notes

[2026-07-30T10:32:25Z · sase-b3.9] Docs, core floor bump, and end-to-end verification for the fuzzy artifact-reference epic.

Changes (sase): docs/editor.md rewrote the Artifact references feature row plus the local-only paragraph — added the fuzzy tier table, empty-query/exact-directory rules, the filterText=typed-text + isIncomplete client contract, and the labelDetails/documentation match-preview affordance (the stale 'editors filtering the typed word' prefix promise is gone). docs/ace.md documents the fuzzy @ menu, tier ranking, the Tab shared-prefix-only rule, path-first payload rows, gold matched runs, and the '~ fuzzy / N of M / warning K not scanned' subtitle. pyproject.toml floor raised sase-core-rs>=0.12.18 (release-plz-published tag containing phases fuzzy/docwalk/menu/lsp/binding); uv.lock relocked and the declared-minimum assertion in tests/test_sase_core_rs_telemetry_smoke_tool.py updated. Fixed the epic plan's missing SDD 'prompt' link, which was failing 'just validate'.

Changes (sase-nvim): README gained the '@ / @kind:query artifact reference' row in the <C-t> dispatcher table, an XPrompt-LSP paragraph on server-ranked fuzzy matching and the two contracts it depends on, and a manual smoke check. Added tests/lsp_artifact_ref_smoke.lua — the Rust LSP tests verify the response fields but cannot verify that Neovim's own filter keeps the rows, which is exactly what the filterText design exists for, so the test drives vim.lsp.completion._convert_results on the real response. Verified that seam is load-bearing: filterText=typed keeps the row, filterText=inserted-reference drops it.

Verification: just install built sase_core_rs 0.12.18 from the pushed linked checkout. just test = 24171 passed / 7 skipped. just test-visual = 392 passed / 1 skipped, goldens unchanged (finder and at_reference_fuzzy/truncated panels included). just check green on fmt (python+markdown), keep-sorted, ruff, mypy, pyscripts, changelog, toobig, SASE validation, committed plans. tests/lsp_artifact_ref_smoke.lua passes against a freshly built cargo LSP binary: @designs:site reaches a bundled document, isIncomplete true, filterText is the typed reference, documentation bolds the matched run, textEdit inserts the full reference, and the kind stage does the same for @dsgn.

Acceptance probe against the real research sidecar (305 rows, no truncation): @research:site surfaces 202607/sase_sites_hub_and_pages/sase_sites_hub_and_pages.md (180 matches); @research:shubp ranks it first; @rsch resolves the research kind; @c still lists commit and chat first; @research:202607/ still prefix-navigates; @pl narrows to one row so Tab accepts @plans:. Keystroke bench with @plans: open (3475 payloads): p50 1.99 ms / p95 2.40 ms browsing, p50 3.46 ms / p95 3.66 ms / max 6.16 ms fuzzy — inside the 16 ms key-to-paint budget. Catalog warm 1.36 s off-thread; @chat: honestly reports 'warning 6040 not scanned'.

Not done, deliberately: no CHANGELOG.md entry — CONTRIBUTING.md and the 'lint (changelog)' gate make it release-please-owned and never hand-edited, so the entry must come from the feat/docs commit subject. Two pre-existing failures on master, both unrelated to this epic (zero src/ changes in this phase, confirmed by stashing): 'lint (symvision)' reports 12 private-import violations under src/sase/ace/tui/actions/clipboard/ from df18f44f6 (refactor(ace): split clipboard palette module), so just check still exits non-zero; and sase-nvim tests/lsp_placeholder_smoke.lua asserts document order for placeholder rows while sase-core has ranked live-before-literal since 641ca36. Both need their own beads.

## Dependencies

- **Depends on:** [sase-b3.5](sase-b3.5.md) ✓
- **Depends on:** [sase-b3.8](sase-b3.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b3.9 | [sase-b3.9](sase-b3.9.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6c21bbb`](https://github.com/sase-org/sase--plans/commit/6c21bbb69813313c3f2106a008e3e35f86bd4398) | docs: add the missing prompt link to the fuzzy completion plan | [sase-b3.9](sase-b3.9.md) | 2026-07-30 10:36:36 |
