# Bead: sase-um.9.3 — Bring the Master Gate to a durable green inside its 8-minute p50 budget

[Bead Pages](../README.md) / [sase-um.9](sase-um.9.md) / sase-um.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.land.md) · **Assignee:** `sase-um.9.3` · **Size:** medium
**Created:** 2026-08-28 15:49:00 EDT · **Closed:** 2026-08-28 16:56:41 EDT
**Plan:** [202608/release\_gate\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_completion.md)

## Description

gatewall: attribute and fix the intermittent Master Gate shard failures, cut the gate's p50 wall from 10.3 to 8 minutes, and give tests/shard_timings.json a freshness path so the shard split cannot silently decay.

## Notes

[2026-08-28T20:55:41Z · sase-um.9.3] PROPOSED FOLLOW-UP: Make the fast suite Pillow-free so Master Gate can drop install-visual — just test still depends on _setup-visual because tests/ace/tui/visual/conftest.py imports Pillow at collection and a few non-visual tests import PIL; switching the gate recipe without that would just reinstall the extra during _setup-visual.

[2026-08-28T20:56:00Z · sase-um.9.3] PROPOSED FOLLOW-UP: flake tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes — wait_for 5s timeout on test (2) of Master Gate runs 33196582795 and 33170058797; later SHAs passed. Do not mute.

[2026-08-28T20:56:20Z · sase-um.9.3] Attribution (newest-first): lint red on 33199036212/33198651770 was stale --epic-symbol sase-ud(question_next_action), already retired by 22f722168. test (5) sase_monitor skill phrase was SHA-specific (skill lagged the expected_phrases until later commits). test (3) 33184415582 was test_ace_page_group_rejects_overlapping_checkouts (also in Full CI / sase-um.9.2). Tip 52327ed78 and the two prior SHAs were green.

[2026-08-28T20:56:41Z · sase-um.9.3] Raised Master Gate SHARD_COUNT 6→8 (matrix 1..8, ~25% less estimated serial per shard, still under the 60 job-min ceiling). Kept install-visual because just test still requires _setup-visual. Added a CI freshness path: Full CI 3.14 just test publishes shard-timings; weekly shard-timings-ratchet.yml copies it when --check --assignment would change the split or generated_at is older than 14 days. Refreshed tests/shard_timings.json from host recordings (800/3466 files). just check passed (full-suite escalate via core-identity-changed). Contract tests for 8-shard matrix, publish steps, and ratchet plus tools/refresh_shard_timings unit tests passed. Trailing-50 p50 is still ~10.3 min until new 8-shard runs replace the history; ship phase remeasures. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-um.9.4](sase-um.9.4.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.3/README.md) | [sase-um.9.3](sase-um.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69d3d71`](https://github.com/sase-org/sase/commit/69d3d71902aec6cbde1dd6d44054d5a1ab166e75) | perf(ci): raise Master Gate to eight shards and refresh timings from CI | [sase-um.9.3](sase-um.9.3.md) | 2026-08-28 16:58:05 EDT |
