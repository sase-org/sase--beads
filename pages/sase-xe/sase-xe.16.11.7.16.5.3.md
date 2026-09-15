# Bead: sase-xe.16.11.7.16.5.3 — Complete viewer version and feed diagnostics

[Bead Pages](../README.md) / [sase-xe.16.11.7.16.5](sase-xe.16.11.7.16.5.md) / sase-xe.16.11.7.16.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.land.md) · **Assignee:** `sase-xe.16.11.7.16.5.3` · **Size:** medium
**Created:** 2026-09-15 08:35:20 EDT · **Closed:** 2026-09-15 13:05:23 EDT
**Plan:** [202609/fleet\_ghost\_rows\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_remaining.md)

## Description

viewer-feed-honesty: consume the real gateway version and preserve reachable invalid/stale-host diagnostics through every projection path.

## Notes

[2026-09-15T17:03:50Z · sase-xe.16.11.7.16.5.3] PROPOSED FOLLOW-UP: core floor is stale for artifact-ref document-scan schema 2 — just check-full reported sase-core-rs==0.34.28 missing the published capability; ratchet pyproject/uv lock when the release window catches up.

[2026-09-15T17:03:54Z · sase-xe.16.11.7.16.5.3] PROPOSED FOLLOW-UP: test-cost hard budgets exceeded after all non-visual tests passed — investigate repo-wide cost regression from run 20260915T170253Z (total_file_cpu_seconds 6703s > 3250s tolerated, multiple Ace/Textual/parser/YAML buckets over budget).

[2026-09-15T17:05:23Z · sase-xe.16.11.7.16.5.3] Verified gateway_version parsing/status skew and old-gateway unknown reporting; host_feed_issues survives config-diagnostic projection copy; invalid zero-row feed detail includes diagnostic/cache age; artifact document-scan schema 2/xprompt_skill compatibility added for current core. epic-symbols clean. Ruff check/format passed on touched files; focused .venv pytest/validator passed (12 tests); check-full ran full non-visual suite with 41756 passed, 21 skipped, then failed test-cost hard budgets, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-xe.16.11.7.16.5.2](sase-xe.16.11.7.16.5.2.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-xe.16.11.7.16.5.4](sase-xe.16.11.7.16.5.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.5.3/README.md) | [sase-xe.16.11.7.16.5.3](sase-xe.16.11.7.16.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0975c7`](https://github.com/sase-org/sase/commit/d0975c7198d098a3f9b4abbe0f4f5124b7625972) | fix: consume gateway version in fleet status | [sase-xe.16.11.7.16.5.3](sase-xe.16.11.7.16.5.3.md) | 2026-09-15 13:59:53 EDT |
