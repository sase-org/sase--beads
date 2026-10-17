# Bead: sase-1lh.7.5.2 — Reconcile current release-blocking tests, docs anchors, and four visual diffs

[Bead Pages](../README.md) / [sase-1lh.7.5](sase-1lh.7.5.md) / sase-1lh.7.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.land.md) · **Assignee:** `sase-1lh.7.5.2` · **Size:** medium
**Created:** 2026-10-16 20:23:09 EDT
**Plan:** [202610/finish\_recapture\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_recapture_release.md)

## Description

release-integration: integrate the launch submission timestamp and logical-plan repair changes with their audits, reconcile docs-owned gate drift, inspect and repair the four persistent visual differences, and verify the release floor contract.

## Notes

[2026-10-17T00:27:45Z · toobig-82.test_agent_display_clan_hints.0] DISCOVERED ISSUE: Independent scoped-check reproduction of the launch-approval extra_env stub gap already tracked as sase-1lw. sase tool run 32d89874e9bc6457ec121619049299f8 failed tests/test_launch_approval_tui.py::test_tui_launch_approval_dispatch_failure_records_failed_response (NEW) and tests/test_launch_approval.py::test_approve_launch_response_dispatches_stored_request because fake_launch does not accept extra_env now passed by launch_request_response.py. This phase already owns integrating the launch submission timestamp with its audits; corroborated sase-1lw rather than filing a new task.

## Dependencies

- **Depends on:** [sase-1lh.7.5.1](sase-1lh.7.5.1.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1lh.7.5.3](sase-1lh.7.5.3.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.2/README.md) | [sase-1lh.7.5.2](sase-1lh.7.5.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:toobig-82.test_agent_display_clan_hints.0][1] | Need phase scope before recording extra_env launch-approval evidence on the active epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-82.test_agent_display_clan_hints.0/README.md

<!-- sase:referenced-by:end -->
