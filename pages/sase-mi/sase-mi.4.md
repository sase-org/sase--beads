# Bead: sase-mi.4 — Bound agent page-link resolution latency

[Bead Pages](../README.md) / [sase-mi](README.md) / sase-mi.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02y.md) · **Assignee:** `sase-mi.4` · **Size:** medium
**Created:** 2026-08-15 20:02:04 EDT · **Closed:** 2026-08-15 20:52:17 EDT
**Plan:** [202608/high\_impact\_task\_bead\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/high_impact_task_bead_sweep.md)

## Description

cache_agent_page_links: Fix sase-lw with a correctly invalidated registry snapshot so TUI selections do not repeat a 400-800ms scan.

## Notes

[2026-08-16T00:46:06Z · sase-mi.4] PROPOSED FOLLOW-UP: Existing symvision private-import debt blocks just check — final just check failed in lint (symvision) on pre-existing private imports in models_panel_provider_* plus _now helpers, while this phase’s touched-file lint, focused URL/header-summary tests, and benchmark passed.

[2026-08-16T00:52:17Z · sase-mi.4] Implemented agent page URL registry snapshot cache keyed by SDD store root, project, primary root, registry freshness token, plus 30s TTL; registry writes/rebuilds bump the token. Verified focused URL/header-summary tests (31 passed), detail-header benchmark agent_page_url cold/warm p50/max 0.0ms, and just check through fmt/ruff/mypy/pyscripts/test-waits/changelog/terminology; final just check still fails unrelated symvision private-import debt already noted as PROPOSED FOLLOW-UP.

[2026-08-16T00:57:48Z · sase-mi.4] Verified focused ruff, URL/header-summary tests, registry reservation tests, and detail-header benchmark with agent_page_url at 0.0ms p50/max; just check remains blocked by unrelated existing symvision private-import failures already recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-mi.1](sase-mi.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mi.7](sase-mi.7.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mi.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mi.4/README.md) | [sase-mi.4](sase-mi.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`517d09b`](https://github.com/sase-org/sase/commit/517d09b7107277354852b907f5b85ddcd11cb732) | perf(tui): cache agent page registry snapshots | [sase-mi.4](sase-mi.4.md) | 2026-08-15 20:59:21 EDT |
