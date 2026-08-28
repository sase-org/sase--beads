# Bead: sase-ud.13.1.3.1 — Retire the notification and family status overrides

[Bead Pages](../README.md) / [sase-ud.13.1.3](sase-ud.13.1.3.md) / sase-ud.13.1.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) · **Assignee:** `sase-ud.13.1.3.1.land`
**Created:** 2026-08-27 11:52:51 EDT · **Closed:** 2026-08-28 08:56:37 EDT
**Plan:** [202608/status\_strip.md](https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/status_strip.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md

<!-- sase:links:end -->

## Description

A plan or question status reaches the Agents tab from exactly one place — the gate shell's own recorded start/stop pair and declared accent. The notification-driven pending-plan and question overrides, the `_agent_pre_question_status` map, the `_agent_status_overrides` re-export facade, the synthetic planner children, and the timestamp-reconstruction passes in `apply_status_overrides` are gone, with every surviving symbol kept for a stated reason rather than by omission.

## Notes

[2026-08-27T20:11:39Z · sase-uv.7] DISCOVERED ISSUE: During unrelated implementation of plan:202608/projection_record_json_list_shape.md on 2026-08-27, required verification ran just check; lint/SASE/committed-plan gates passed and the selected pytest lane escalated to the full suite, then failed deterministically on six status-family nodes after 16902 passed / 8 skipped: tests/ace/tui/actions/test_agent_retry_family_projection.py::test_live_failed_plan_family_projects_retry_immediately, tests/test_agent_loader_dedup_pid_families.py::test_pid_dedup_preserves_followup_workflow_agents, and four tests/test_agent_loader_epic_created_status.py nodes. Focused reruns reproduce these failures with the local editable Python source and current linked core binding; the record-shape focused suite passes (55 passed), and the pager parity failures from the first stale run pass after rebuilding the binding. The failures are causally linked here rather than a new task bead: this epic explicitly owns removing synthetic planner children and family status overrides, and its closed child phase sase-ud.13.1.3.1.3 retired synthetic planner children while these tests still assert that behavior or its transition state. Current record-shape diff does not touch the status-family modules under test.

[2026-08-27T20:28:52Z · toobig-4h.done_loaders.0] DISCOVERED ISSUE: During unrelated done-loader module-splitting verification on 2026-08-27, just check passed fmt/ruff/mypy/Symvision/toobig/SASE validation but the scoped pytest lane failed deterministically on the same six status-family nodes already recorded here: tests/ace/tui/actions/test_agent_retry_family_projection.py::test_live_failed_plan_family_projects_retry_immediately, tests/test_agent_loader_dedup_pid_families.py::test_pid_dedup_preserves_followup_workflow_agents, and four tests/test_agent_loader_epic_created_status.py nodes. Focused rerun reproduced the failures; the done-loader focused suite passed 65 tests, and the local diff only splits src/sase/ace/tui/models/_loaders/_done_loaders.py into facade/common/filesystem/snapshot modules plus a facade monkeypatch-compatibility wrapper.

[2026-08-28T12:56:37Z · sase-ud.13.1.3.1.5.land] Rechecked the linked status_strip epic plan, all four direct phases, nested epic sase-ud.13.1.3.1.5 and its phase, every descendant note, all five epic commits, and the current source. The nine real gate-shell projection guards pass; notification-driven writers, _agent_pre_question_status, the _agent_status_overrides model facade, synthetic planner machinery, and DONE-to-plan/question/feedback reconstruction are absent. Legacy notification response-file reconciliation remains intentionally isolated, while concrete post-gate handoff labels remain wired. The two parent DISCOVERED ISSUE notes and the premature/partial phase 3-4 landings are resolved by nested repair commit de491c710; the focused status/family/inventory suite passed 109 tests and the older unrelated failure modules passed 72 tests. Follow-up dispositions: phase 1 process-identity failures were corroborated on ready CI task sase-uw; its child-exemption flake was corroborated on ready task sase-n6; distinct priority-admission flake was created as ready large task sase-v0 with related links to both; phase 4 14-node baseline proposal is resolved by d929ed82b for 13 nodes plus a current passing relation-collapse node after 9ec2a7f52; nested phase baseline proposal was likewise already fulfilled by d929ed82b. just selection-health --fail-on-new-flake passes. No commits follow de491c710 on origin/master, all descendants are closed, and sase bead epic-symbols reported no entries.
