# Bead: sase-1m3.9 — Shared Rich and Markdown section renderers

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.9` · **Size:** medium
**Created:** 2026-10-16 22:05:24 EDT · **Closed:** 2026-10-19 08:48:34 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

render: add the shared report groupings and legends to the registry, and build pure section renderers (card, project, repo, model, and patch tables, legend, coverage) and the Markdown renderer over `ProjectStatsView` and a `RenderContext`, with width-pinned goldens.

## Notes

[2026-10-19T12:18:02Z · sase-1m3.9] PROPOSED FOLLOW-UP: skipped stats_decision_record — epic DECISIONS forbade editing the decisions web (stats count each fact at its durable source; footers stamp only underivable facts)

[2026-10-19T12:18:11Z · sase-1m3.9] PROPOSED FOLLOW-UP: pre-existing TUI hint/pin tests fail on clean HEAD — test_changed_reply_invalidates_hint_document_and_mappings, test_hint_mode_keeps_collapsed_header_unchanged, test_bottom_pinned_body_stays_pinned_across_row_count_change

[2026-10-19T12:48:34Z · sase-1m3.9--1] Verified shared Rich+Markdown section renderers: card/project/repo/model/patch tables, legend, coverage, and Markdown over ProjectStatsView + RenderContext. Renderer goldens under tests/stats/golden/render/ pass in serial and xdist via tests/stats/test_render_project.py. Compact legend is sourced from PROJECT_REPORT_LEGENDS (registry). Terminology allowlist covers legend.py agent_tagged_commits. Live Projects spec is unchanged. sase tool run check 41f780c4ac581c4fa8c85d4e55b45f37 passed (verdict pass, exit 0); no leftover --epic-symbol rows. Pre-existing TUI hint/pin NEW items reproduce on clean HEAD (already noted as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1m3.10](sase-1m3.10.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.11](sase-1m3.11.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.8](sase-1m3.8.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.9.md) | [sase-1m3.9](sase-1m3.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c4c262`](https://github.com/sase-org/sase/commit/9c4c262559b566309111ca8a37c18d83a62aff26) | feat(stats): add shared Rich and Markdown Projects section renderers | [sase-1m3.9](sase-1m3.9.md) | 2026-10-19 08:50:34 EDT |
