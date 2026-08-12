# Bead: sase-k2.3 — Dedicated external\_mirror lumberjack and lane-independent state

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.3` · **Size:** medium
**Created:** 2026-08-12 11:29:35 EDT · **Closed:** 2026-08-12 12:07:03 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

lane: move both mirror chops out of the 300-second checks lane into a new external_mirror lumberjack with a 15-minute interval and 5-minute chop timeout, and relocate the PR mirror's cursor and backoff state out of the lane directory so no consumer hardcodes a lane name again.

## Notes

[2026-08-12T16:07:03Z · sase-k2.3] Moved external_issue_mirror and external_pr_mirror into a new external_mirror lumberjack (interval 900s, chop_timeout 5m; dropped the now-redundant per-chop run_every: 10m and kept an explicit 5m timeout on the PR mirror). Relocated the PR mirror's cursor/backoff state from lumberjack_state_dir(checks) to the lane-independent sase_subdir(external_mirror) via a new pr_mirror_state_dir() helper that migrates legacy files on first read; removed the ensure_lumberjack_dirs_fn/runtime.context.state_dir threading from sync_external_pull_requests, the sync-external CLI, and the doctor check. Added external_mirror/budget.py's LANE_CHOP_TIMEOUT_SECONDS so both mirrors derive their internal work-budget constants from one source instead of hand-copied magic numbers. Routed the PR mirror chop's check-error and backoff summaries through MirrorReport so they carry the same counter set (including unmirrored) as a successful run. Updated docs/axe.md, docs/beads.md, and docs/configuration.md, plus all directly affected tests (doctor, chop, CLI, and two new pr_mirror_state_dir migration tests in test_external_mirror_state.py). Verified: schema validation and axe config loading confirm the new lane expands both chops correctly (external_issue_mirror[<project>], external_pr_mirror[<project>]); just check passed clean (fmt/lint/mypy/symvision/keep-sorted) and its scoped test lane self-escalated to the full suite because default_config.yml changed, which also passed.

[2026-08-12T16:08:52Z · sase-k2.3] Added external_mirror lumberjack lane (900s interval, 5m chop timeout) hosting external_issue_mirror and external_pr_mirror, removed from checks lane. Added lane-independent pr_mirror_state_dir() with migration from legacy checks-lane state files. Added shared LANE_CHOP_TIMEOUT_SECONDS budget constant. PR mirror chop error/backoff paths now use MirrorReport.summary_fields() for consistent counters. Updated docs/axe.md, docs/beads.md, docs/configuration.md. Verified: schema validation, AXE config loading, and just check (full lint gates + scoped test lane self-escalated to full suite due to default_config.yml change) all passed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k2.3/README.md) | [sase-k2.3](sase-k2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb33e3c`](https://github.com/sase-org/sase/commit/fb33e3c1f9ba8122392eeec67aee1b05874c0e88) | feat(external-mirror): dedicated lumberjack lane with lane-independent state | [sase-k2.3](sase-k2.3.md) | 2026-08-12 12:09:53 EDT |
