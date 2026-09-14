# Bead: sase-xe.16.11.7.16.3 — Invalid or stale host feeds render loudly in the viewer

[Bead Pages](../README.md) / [sase-xe.16.11.7.16](sase-xe.16.11.7.16.md) / sase-xe.16.11.7.16.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.01](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.01.md) · **Assignee:** `sase-xe.16.11.7.16.3` · **Size:** medium
**Created:** 2026-09-14 16:25:32 EDT · **Closed:** 2026-09-14 18:02:23 EDT
**Plan:** [202609/fleet\_ghost\_rows\_readcompat.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_readcompat.md)

## Description

invalid-feed-honesty: when a remote host's snapshot is status "invalid" or served from cache beyond freshness thresholds, the ACE Agents tab must surface the feed error at the host/machine level (banner or host row with error state and cache age) and stamp honest staleness chrome on every cached row — no plain RUNNING rows frozen from an hours-old cache — with the fleet_envelope_invalid diagnostic reachable from the detail panel; regression tests cover the invalid-host and stale-cache render paths.

## Notes

[2026-09-14T22:02:23Z · sase-xe.16.11.7.16.3--2] Threaded remote-host feed status (status=invalid, freshness.error, cache age) through TUI viewer: _fleet_agents_rows.py, fleet_agents.py (FleetRowsProjection.host_feed_issues), _fleet_common.py (host_feed_issue_text), _fleet_header.py, agent_groups/_tree.py (banner status_label), _agent_list_render_agent.py (row chrome 'feed invalid'), _agent_display_header_metadata.py (detail panel Feed error line), _agent_list_render_cache.py (cache keys). Added tests/ace/tui/test_fleet_agents_feed_honesty.py, tests/ace/tui/widgets/test_agent_display_fleet_fields.py, plus additions to test_agent_groups_folds.py and test_agent_list_status_indicators.py, and fleet_invalid_host_response fixture. Verified: targeted pytest suite (59 passed) and full 'just check' gate both green; sase bead epic-symbols reported no remaining --epic-symbol entries for this phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.3.md) | [sase-xe.16.11.7.16.3](sase-xe.16.11.7.16.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0b1a480`](https://github.com/sase-org/sase/commit/0b1a4806d6b7568a61d67be4f203819b85ef775e) | fix(tui): render invalid or stale remote-host feed status loudly | [sase-xe.16.11.7.16.3](sase-xe.16.11.7.16.3.md) | 2026-09-14 18:04:15 EDT |
