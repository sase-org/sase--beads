# Bead: sase-l6.3 — Per-lane resolution, caching, and freshness

[Bead Pages](../README.md) / [sase-l6](README.md) / sase-l6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zw](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zw.md) · **Assignee:** `sase-l6.3` · **Size:** medium
**Created:** 2026-08-13 15:24:22 EDT · **Closed:** 2026-08-13 16:54:27 EDT
**Plan:** [202608/sase\_context\_incremental.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_context_incremental.md)

## Description

lanes: split the monolithic detail-header summary into independently resolved and independently cached lanes with per-lane freshness policies, replacing the blanket 1 s whole-summary TTL, with no user-visible change yet.

## Notes

[2026-08-13T20:54:00Z · sase-l6.3] PROPOSED FOLLOW-UP: symvision reports stream_and_parse_messages_json_output in src/sase/llm_provider/_subprocess_claude.py as an unused public function, failing `just check`. Confirmed pre-existing on master (unaffected by this phase's diff, which never touches that file) via git stash + rerun.

[2026-08-13T20:54:27Z · sase-l6.3] Split build_detail_header_summary into 9 named DetailContextLane values (plan-bead, artifacts, memory, skills, workspaces, slow-tools, xprompts, page-url, wait-beads); resolution is now lane-selective via a `lanes: frozenset[DetailContextLane] | None` param, defaulting to all. DetailHeaderSummary gained `ready_lanes` so a resolved-empty lane is distinguishable from an unrequested one. should_refresh_detail_header_summary now returns the frozenset of stale lanes instead of one bool, with per-lane cadences replacing the blanket 1s DIFF_CACHE_TTL_SECONDS: wait-beads has no TTL, slow-tools matches its 5s render tick, the rest use a 10s cadence, and an active hint session widens every lane to the existing 30s hint interval. cache_detail_header_summary now merges newly resolved lanes into the cached summary instead of replacing it wholesale, so a partial rebuild can't blank an already-fresh lane. Updated the clan-aggregation caller (_agent_clan_member_content.py) and one test to the new lanes= API; removed the old include_slow_tools/include_agent_page_url flags entirely (no remaining references).

Verification: mypy clean on all 7 changed/added files. ruff check + ruff format clean. New tests/ace/tui/widgets/test_agent_display_header_summary_lanes.py (partial-lane resolution, merge-does-not-blank, resolved-empty-vs-unresolved, per-lane staleness incl. stationary-selection settling into revalidation, hint-session widening) plus the phase's named regression surface (test_agent_page_url.py, test_agent_display_header_enrichment_async.py, test_agent_context.py, test_agent_display_bead_section.py, test_agent_display_plan_section.py, test_agent_display_commit_metadata.py): 138 passed. Full tests/ace/tui/widgets/: 3553 passed. just test-scoped: 2826 passed. just test-visual: 11 pre-existing failures (frontmatter_panel/artifacts_beads/artifacts_plans/preview_panel), confirmed byte-identical failures with the same pixel-diff signature on unmodified master via git stash -- no new visual regressions, rendered output stays byte-identical for every lane. just check's only failure is a pre-existing, unrelated symvision finding in _subprocess_claude.py, also confirmed present on master and recorded as a PROPOSED FOLLOW-UP note on this bead.

## Dependencies

- **Depends on:** [sase-l6.1](sase-l6.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.4](sase-l6.4.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l6.6](sase-l6.6.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l6.3/README.md) | [sase-l6.3](sase-l6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`932277b`](https://github.com/sase-org/sase/commit/932277b2691a35c3f2a5dee2257b205679585d13) | refactor(ace): split detail-header summary into per-lane resolution and caching | [sase-l6.3](sase-l6.3.md) | 2026-08-13 16:55:01 EDT |
