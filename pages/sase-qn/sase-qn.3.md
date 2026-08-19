# Bead: sase-qn.3 — Catalog fetch past GitHub search's 1000-result cap

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.3` · **Size:** medium
**Created:** 2026-08-18 20:12:39 EDT · **Closed:** 2026-08-18 21:30:31 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

fetch: shard the topic search so results above GitHub's hard 1000-item search cap are still returned, surface truncation and incomplete_results as catalog warnings, and make the gh timeout scale with page count instead of a flat 20 s.

## Notes

[2026-08-19T01:30:03Z · sase-qn.3] PROPOSED FOLLOW-UP: flake in tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes — wait_for() timed out after 5s under the escalated 14-worker full suite; serial rerun passed in 16.75s. Unrelated to catalog fetch; catalog is stubbed via _patch_catalog_recording.

[2026-08-19T01:30:31Z · sase-qn.3] Sharded GitHub topic search past the 1000-result cap (stable stars: buckets, then created: date bisection), surfaced incomplete_results and unsplittable-cap truncation as PluginCatalog.warnings, replaced gh --paginate with explicit per-page requests at GH_TIMEOUT_SECONDS each, and dropped catalog_cache.json indent. Verified paging/shard/dedupe/truncation/incomplete/partial-failure tests, warning threading through load_plugin_catalog, compact cache round-trip, and measure_fetch_pages n=2000 returning 2000 entries. just check lint passed; escalated full suite 33859 passed / 1 unrelated flake (serial rerun passed).

[2026-08-19T01:31:54Z · sase-qn.3] Sharded GitHub topic search past the 1000-result cap (stable stars: buckets, then created: date bisection), surfaced incomplete_results and unsplittable-cap truncation as PluginCatalog.warnings, replaced gh --paginate with explicit per-page requests at GH_TIMEOUT_SECONDS each, and dropped catalog_cache.json indent. Verified paging/shard/dedupe/truncation/incomplete/partial-failure tests, warning threading through load_plugin_catalog, compact cache round-trip, and measure_fetch_pages n=2000 returning 2000 entries. just check lint passed; escalated full suite 33859 passed / 1 unrelated flake (serial rerun passed).

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.3/README.md) | [sase-qn.3](sase-qn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ea95b16`](https://github.com/sase-org/sase/commit/ea95b16ce2ba58101b805f65cd6f628577696517) | feat(plugins): shard GitHub catalog search past the 1000-result cap | [sase-qn.3](sase-qn.3.md) | 2026-08-18 21:32:42 EDT |
