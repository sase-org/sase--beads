# Bead: sase-b3.10.4 — Docs, release, and epic landing

[Bead Pages](../README.md) / [sase-b3.10](sase-b3.10.md) / sase-b3.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.10.4` · **Size:** small
**Created:** 2026-07-30 10:57:17 UTC · **Closed:** 2026-07-30 11:58:58 UTC
**Plan:** [202607/editor\_artifact\_ref\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202607/editor_artifact_ref_parity.md)

## Description

land: correct the docs/editor.md reachability claims, publish the sase-core release, run the editor acceptance checks, then close epic sase-b3, run just symvision, and mark both plan files done.

## Notes

[2026-07-30T11:58:58Z · sase-b3.10.4] Corrected docs/editor.md: replaced the unqualified 'any memorable fragment of its path or title' claim with the five enumerated kinds matched on payload AND title, added a paragraph naming both remaining bounds (5000-row per-root scan, 200 rows per group) and how they are disclosed ('at least N additional payloads not shown' in item detail plus isIncomplete), documented the per-project/per-catalog-signature 2s-TTL inventory cache and its refreshCatalog invalidation, corrected the stale 'completion re-reads its catalog on each request' sentence, and rewrote the labelDetails.detail sentence to list the real per-kind titles. Published sase-core v0.12.19 (release-plz PR #56 merged, tag 493a632, crates.io publish job green) containing rank/titles/reach; no pyproject sase-core-rs floor bump needed since none of the three phases touched crates/sase_core_py. Extended sase-nvim tests/lsp_artifact_ref_smoke.lua with the @agent: mid-name-fragment case (agent_roots fixture, two published pages, asserts the row, filterText as typed, full-reference textEdit, labelDetails.detail == ' · 5' short-name title, and survival of Neovim's own completion filter) - passes against the freshly built binary. Acceptance against the real launcher catalog with the research sidecar via SASE_XPROMPT_LSP_CMD: @research:site reaches 202607/sase_sites_hub_and_pages/sase_sites_hub_and_pages.md (200 rows, 'at least 29 additional payloads not shown', 1848ms cold then 3ms warm from the cache); @research:202607/ prefix still returns 89 rows (no regression); @agent:sase-b3 returns 25 rows; @file:panel reaches an id by basename (1036 disclosed as omitted); @file:default:290765b3 digest prefix still returns its row; @rsch still resolves the research kind; every hit carries a non-echoing labelDetails title. Gates: sase-core cargo fmt --check, clippy --workspace --all-targets -D warnings, and cargo test --workspace all green (PYO3_PYTHON=python3.12, LD_LIBRARY_PATH for libpython3.12); sase just install, just test-visual (392 passed / 1 skipped), and just symvision ('All public/private classes/functions are used properly!' - no stale sase-b3 epic whitelist entries) all green. Also fixed the missing PROMPT link in plans:202607/editor_artifact_ref_parity.md that sase validate flagged, and set its frontmatter status: done. NOT done, deferred deliberately: (1) closing epic sase-b3 and marking plans:202607/fuzzy_artifact_ref_completion.md done - my launch instruction explicitly forbids closing the parent epic, and sase-b3 is assigned to agent sase-b3.land; (2) two pre-existing sase test failures in tests/ace/tui/widgets/test_artifact_ref_completion.py (test_bare_at_opens_artifacts_then_files, test_kind_menu_filters_artifacts_and_files_through_shared_policy) caused by sase-core 4e61ad0 (bead sase-b4.1) gating file rows behind an include_files opt-in without updating sase's Python callers - now shipped in v0.12.19, which sase's >=0.12.18 floor will resolve, so sase-b4.1's Python-side work is urgent; (3) four pre-existing sase validate plan-link errors in at_reference_file_row_gate.md and bead_page_association_anchors.md, owned by other beads.

## Dependencies

- **Depends on:** [sase-b3.10.3](sase-b3.10.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b3.10.4 | [sase-b3.10.4](sase-b3.10.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`898f0fb`](https://github.com/sase-org/sase--plans/commit/898f0fb6a43a150f8d80c489ae2f22d55602d846) | docs: mark the editor artifact-ref parity plan done | [sase-b3.10.4](sase-b3.10.4.md) | 2026-07-30 12:01:56 |
