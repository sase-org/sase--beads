# Bead: sase-j7.3 — Stop the flake gate from flagging node IDs that no longer exist

[Bead Pages](../README.md) / [sase-j7](README.md) / sase-j7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-j0.w1.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j0.w1.f0/README.md) · **Assignee:** `sase-j7.3` · **Size:** medium
**Created:** 2026-08-10 15:44:44 EDT · **Closed:** 2026-08-10 16:16:24 EDT
**Plan:** [202608/fix\_sase\_ct\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)

## Description

stale-nodes - bead sase-j5. Make the reproducible-flake gate skip or separately report recorded node IDs absent from the collected suite, so a renamed test stops manufacturing pressure to bump the baseline cutoff.

## Notes

[2026-08-10T20:16:24Z · sase-j7.3] Added collectible_nodeid_oracle (AST-based, per-file memoised) to tests/_test_selection_health.py; reproducible_flake_nodeids now excludes stale (uncollectable) node IDs and the new stale_flake_nodeids reports them separately. Added unresolved_commit_order_count to surface heads git_commit_order_oracle cannot resolve. Wired both into tools/selection_health's --explain/gate output. New unit tests (tests/test_test_selection_health_correlation.py) and CLI tests (tests/test_selection_health_tool.py) cover: a recorded-but-uncollectable node is reported as stale, not a live flake; unresolved commit-order heads are counted. Verified: just check green (all lint gates + scoped test lane); targeted pytest run of the 3 touched test files all pass (65 tests); just selection-health --fail-on-new-flake still non-vacuously flags a live reproducible flake (tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree, the sase-j6 node) - confirmed via git stash that this same flake and exit code reproduce identically on unmodified master, so it is pre-existing debt explicitly scoped to the epic's later fix-leaks phase, not introduced or masked by this change.

## Dependencies

- **Blocks:** [sase-j7.5](sase-j7.5.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j7.3/README.md) | [sase-j7.3](sase-j7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1b47ea7`](https://github.com/sase-org/sase/commit/1b47ea712ad1e75cbde27ea6aacb32b39daa429c) | feat(selection-health): skip stale node IDs in the reproducible-flake gate | [sase-j7.3](sase-j7.3.md) | 2026-08-10 16:17:14 EDT |
