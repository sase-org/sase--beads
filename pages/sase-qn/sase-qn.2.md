# Bead: sase-qn.2 — Latest-version enrichment that scales with installed count, not catalog size

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.2` · **Size:** medium
**Created:** 2026-08-18 20:12:39 EDT · **Closed:** 2026-08-18 21:50:19 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

enrich: remove the quadratic installed-version lookup, scope eager PyPI enrichment to installed entries, add a lazy per-entry latest fetch for the highlighted row, bound the fetch budget, and prune the unbounded latest cache.

## Notes

[2026-08-19T01:50:03Z · sase-qn.2] Feature flag plugin_catalog_scoped_latest (removal bead sase-qq, beta, default off) gates scoped eager enrichment and the TUI lazy highlighted-row fetch. sase plugin list stays installed-only unless -A|--all-latest; sase plugin show always fetches the requested plugin. Guard/land should flip the flag on or record why it stays off.

[2026-08-19T01:50:19Z · sase-qn.2] Removed the per-miss catalog scan (installed versions indexed once), scoped eager PyPI enrichment to installed entries behind plugin_catalog_scoped_latest (sase-qq), added a debounced lazy latest fetch for the highlighted Updates > Plugins row, bounded the miss batch with an 8s deadline, stopped discarding latest_cache.json on refresh, and prune entries older than 4*TTL on write. Verified: unit tests for scope/flag/refresh/deadline/prune; TUI both-states lazy fetch; CLI --all-latest; just check lint green (ruff/mypy/symvision/feature-flags); escalated full suite 33860 passed; remaining two failures (test_ace_page_fast_startup_is_structurally_quiet, test_logs_tab_g_and_shift_g_scroll_detail_extremes) are known flakes sase-oz/sase-jb and passed on isolated rerun. No leftover --epic-symbol entries.

[2026-08-19T01:51:40Z · sase-qn.2] Removed quadratic installed-version lookup, scoped eager PyPI enrichment behind plugin_catalog_scoped_latest (sase-qq), added lazy highlighted-row fetch, 8s miss deadline, cache prune at 4*TTL, and refresh that force-expires in-scope keys only. Verified: latest/CLI/TUI tests; just check lint green; escalated suite 33860 passed; flakes sase-oz/sase-jb passed isolated. No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.2/README.md) | [sase-qn.2](sase-qn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6641805`](https://github.com/sase-org/sase/commit/66418053282c2937c4ca79a179e5c9a21bea02a8) | feat(plugins): scale latest-version enrichment to installed count | [sase-qn.2](sase-qn.2.md) | 2026-08-18 21:53:45 EDT |
