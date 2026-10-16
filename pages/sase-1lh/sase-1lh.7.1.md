# Bead: sase-1lh.7.1 — Refresh stale release-PR heads instead of declaring CORE\_FLOOR\_BLOCKED

[Bead Pages](../README.md) / [sase-1lh.7](sase-1lh.7.md) / sase-1lh.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.land.md) · **Assignee:** `sase-1lh.7.1` · **Size:** medium
**Created:** 2026-10-16 16:46:19 EDT · **Closed:** 2026-10-16 17:05:56 EDT
**Plan:** [202610/sase\_1lh\_landing\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_1lh_landing_repair.md)

## Description

watcher-repair: make tools/release_watch tell a stale release-PR head from a real core-floor block, refresh the stale head through one Publish dispatch per master HEAD, and fix the dispatch red-budget and close-during-signal gaps.

## Notes

[2026-10-16T21:05:28Z · sase-1lh.7.1] PROPOSED FOLLOW-UP: just docs-gen-check fails on clean base too — committed docs/reference/cli/*.md wrap sase tool usage as [-q] [-T N] [-v] but the local sase binary prints [-q | -v]; regenerate CLI refs

[2026-10-16T21:05:56Z · sase-1lh.7.1] watcher-repair done: stale-head refresh (pr_refresh 1/SHA, 30m cooldown, no-op guard), fresh red budget in dispatch_due, signal-during-close goes detached. Verified: 86 release-watch pytest pass (10 new), live preflight exit 0 with release_pr=#299:open:stale and no CORE_FLOOR_BLOCKED, ruff/mypy/fmt/symvision/docs-lint green. sase tool run check fails only on pre-existing docs-gen-check CLI-ref drift, reproduced on clean base (see PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1lh.7.4](sase-1lh.7.4.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.1/README.md) | [sase-1lh.7.1](sase-1lh.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec7e86e`](https://github.com/sase-org/sase/commit/ec7e86e6907be34bb44252694ba5b0a147ffec6c) | fix(release-watch): refresh stale release-PR heads instead of declaring CORE\_FLOOR\_BLOCKED | [sase-1lh.7.1](sase-1lh.7.1.md) | 2026-10-16 17:07:54 EDT |
