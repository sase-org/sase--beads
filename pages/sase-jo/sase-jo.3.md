# Bead: sase-jo.3 — Python wire and golden-contract parity

[Bead Pages](../README.md) / [sase-jo](README.md) / sase-jo.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xv](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xv/README.md) · **Assignee:** `sase-jo.3` · **Size:** small
**Created:** 2026-08-11 06:58:52 EDT · **Closed:** 2026-08-11 08:13:29 EDT
**Plan:** [202608/stitch\_origin\_badges.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_origin_badges.md)

## Description

wire: mirror the new `origin` field in the Python VCS-log wire records, teach the pure-Python golden-contract parser to compute the same value, and update the shared commit fixtures and core wire tests.

## Notes

[2026-08-11T12:13:29Z · sase-jo.3] Wired origin field through the Python VCS-log wire (schema v3->v4, CommitOrigin literal, presence-style _origin_from_dict decoder, exported CommitOrigin), added _classify_commit_origin_python to the pure-Python golden-contract parser (reuses parse_commit_footer's SASE_* tag detection), and updated shared commit fixtures (tests/_vcs_log_collect_helpers.py, tests/_vcs_log_render_helpers.py, tests/ace/tui/_commits_pane_helpers.py) plus tests/test_core_vcs_log.py (golden-parity + aggregated-dict origin coverage) and tests/test_validate_sase_core_rs_tool.py (schema version bump to 4). Verified with 'just check-full' (full lint gates + full pytest suite + flake baseline), exit 0, all green.

## Dependencies

- **Depends on:** [sase-jo.1](sase-jo.1.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-jo.4](sase-jo.4.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-jo.5](sase-jo.5.md) ✓ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jo.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jo.3/README.md) | [sase-jo.3](sase-jo.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2d40e92`](https://github.com/sase-org/sase/commit/2d40e929735428a5a14d7ceae4b1ddaf2e9ee839) | feat(core): wire commit origin through Python VCS-log wire and golden parser | [sase-jo.3](sase-jo.3.md) | 2026-08-11 08:14:09 EDT |
