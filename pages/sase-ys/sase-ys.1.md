# Bead: sase-ys.1 — Share the star alias contract with the xprompt LSP

[Bead Pages](../README.md) / [sase-ys](README.md) / sase-ys.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yf.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yf.land.w3.md) · **Assignee:** `sase-ys.1` · **Size:** medium
**Created:** 2026-09-09 06:57:14 EDT · **Closed:** 2026-09-09 07:29:43 EDT
**Plan:** [202609/lsp\_star\_model\_alias\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/lsp_star_model_alias_completion.md)

## Description

core_lsp_star_alias: make the Rust shortcut filter and edit plan directly consumable by LSP completion, then add the trigger, response projection, and core protocol coverage.

## Notes

[2026-09-09T11:29:43Z · sase-ys.1] Implemented in sase-core (crates/sase_core/src/editor/model_alias_shortcut.rs, sase_core/src/lib.rs+editor/mod.rs, sase_core_py/src/lib.rs, sase_xprompt_lsp/src/{server.rs,lsp_convert.rs}, + new tests/jsonrpc_stdio_model_alias_shortcut.rs): added filter_model_alias_shortcut_entries (alias-only catalog filter, reused by both the edit planner and the new PyO3 binding filter_model_alias_shortcut_entries); normalized ModelAliasShortcutEditWire.edit to extend one char into a following ASCII space and reinsert it in new_text so caret == end-of-edit always (new invariant test); wired '*' as an LSP completion trigger with detection before the generic classifier (document-local, before any catalog refresh); built the shortcut CompletionList/response reusing %model: candidate/detail/documentation formatting plus a star-specific textEdit (via plan_model_alias_shortcut_edit), filterText='*'+query, first-row preselect, isIncomplete=true, and an always-returned (possibly empty) response so a valid star context never falls through. Verified via ./scripts/check.sh (fmt-check, clippy -D warnings, full cargo test --workspace incl. sase_core_py's abi3-py312 binding tests) from the sase-core root: all green (sase_core 2306 tests, sase_core_py 133, sase_xprompt_lsp 132 unit + 8 jsonrpc_stdio incl. new stdio_jsonrpc_model_alias_shortcut_completion). sase bead epic-symbols sase-ys.1 reported no entries.

## Dependencies

- **Blocks:** [sase-ys.2](sase-ys.2.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ys.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ys.1/README.md) | [sase-ys.1](sase-ys.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cb669ec`](https://github.com/sase-org/sase-core/commit/cb669ec96526294cb14b07cd936c28b8b39be9bc) | feat(editor): share the star model-alias shortcut contract with the xprompt LSP | [sase-ys.1](sase-ys.1.md) | 2026-09-09 07:30:41 EDT |
