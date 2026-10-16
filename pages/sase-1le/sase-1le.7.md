# Bead: sase-1le.7 — Page-move machinery, docs map, and llms.txt

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.7` · **Size:** medium
**Created:** 2026-10-15 18:11:11 EDT · **Closed:** 2026-10-15 21:30:46 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

moves: add docs/_meta/moves.yml as the single source for redirects and anchor stubs, the tools/render_docs framework, tools/docs_split, and a generated docs map plus llms.txt; pilot by taking Instruction Inventory off the site.

## Notes

[2026-10-16T01:30:34Z · sase-1le.7] PROPOSED FOLLOW-UP: Reconcile the clean-base docs check failures: test_pdf_check_recipe_keeps_strict_mkdocs_export and test_rss_plugin_images_use_the_default_social_image both fail at fd8adfbe9b (also recorded in sase-1lc.4 note #1); test_tui_app_import_stays_under_startup_budget loads 3523 modules against the 3520 cap at fd8adfbe9b and is already tracked by sase-1ic.

[2026-10-16T01:30:46Z · sase-1le.7] Implemented the moves registry/rendering framework, section splitter, generated docs map and llms.txt; moved Instruction Inventory off-site with redirect compatibility. just fix passed; focused docs move/URL tests and just docs-check passed; just check static/docs gates passed but three test failures were reproduced on clean base fd8adfbe9b and recorded as PROPOSED FOLLOW-UP. epic-symbols reported none.

## Dependencies

- **Depends on:** [sase-1le.2](sase-1le.2.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.5](sase-1le.5.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.8](sase-1le.8.md) ◐ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.9](sase-1le.9.md) ◐ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.7/README.md) | [sase-1le.7](sase-1le.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a619baa`](https://github.com/sase-org/sase/commit/a619baa9106f878a3532236d0aeee11ab9208f18) | feat(docs): add page move and reference map generators | [sase-1le.7](sase-1le.7.md) | 2026-10-15 21:31:49 EDT |
