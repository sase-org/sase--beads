# Bead: sase-rp.2 — Integrate and route the guarded Config Launch sub-tab

[Bead Pages](../README.md) / [sase-rp](README.md) / sase-rp.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ri.land.w2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ri.land.w2.md) · **Assignee:** `sase-rp.2` · **Size:** medium
**Created:** 2026-08-21 06:23:57 EDT · **Closed:** 2026-08-21 07:44:58 EDT
**Plan:** [202608/admin\_center\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_launch.md)

## Description

launch_integration: add the lazy Launch child behind a temporary beta flag and route every Launch Control opener through the Admin Center Config host.

## Notes

[2026-08-21T11:44:27Z · sase-rp.2] PROPOSED FOLLOW-UP: Fix baseline Symvision private-import failures — just check fails in the symvision lane on private imports in src/sase/ace/tui/_proc_producer_site.py, src/sase/llm_provider/commit_finalizer.py, src/sase/finalizers/declaration.py, and src/sase/llm_provider/commit_finalizer_prompting.py; these files are unrelated to the Admin Center Launch phase changes.

[2026-08-21T11:44:58Z · sase-rp.2] Implemented guarded Config Launch sub-tab behind admin_center_launch_subtab; verified focused pytest for feature flags, config hub/pane, leader routing, indicators, notifications, launch guard, and commits pane wait cleanup; git diff --check clean; epic-symbols reports no entries; just check reached symvision and failed on unrelated baseline private-import findings, with PROPOSED FOLLOW-UP noted on this bead.

[2026-08-21T11:46:15Z · sase-rp.2] Verified focused pytest set passed, commits pane test passed, feature flag check passed under the venv, wait-helper lint passed, git diff --check passed, and epic-symbols had no entries; just check reached an unrelated baseline Symvision private-import failure recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-rp.1](sase-rp.1.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-rp.3](sase-rp.3.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rp.2/README.md) | [sase-rp.2](sase-rp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4421c90`](https://github.com/sase-org/sase/commit/4421c90bf1e582270386a9d2f4c781f8fddcb32b) | feat(tui): route launch settings through admin center | [sase-rp.2](sase-rp.2.md) | 2026-08-21 07:48:23 EDT |
