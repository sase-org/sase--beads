# Bead: sase-1oh.4.1.3 — Verify reopened work blocks progress and appears in stranded surfaces

[Bead Pages](../README.md) / [sase-1oh.4.1](sase-1oh.4.1.md) / sase-1oh.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.4.md) · **Assignee:** `sase-1oh.4.1.3` · **Size:** medium
**Created:** 2026-10-26 14:34:47 EDT · **Closed:** 2026-10-26 22:30:12 EDT
**Plan:** [202610/failed\_stitch\_bead\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/failed_stitch_bead_recovery.md)

## Description

recovery-surfaces: feed reopened completion failures into the stranded-work collector, verify doctor and ACE plus epic dependency blocking with integration tests, and update the bead lifecycle reference. Record full acceptance evidence for the child land agent; do not close ancestor or source-task beads.

## Notes

[2026-10-27T02:29:42Z · sase-1oh.4.1.3] PROPOSED FOLLOW-UP: capacity scan tests assume fixture pid 11111 is alive — test_capacity_only_skips_done_dirs_and_keeps_active_ones plus two runner-slot capacity tests fail wherever pid 11111 is absent (sase-1oj.1 never-live prune); identical on the clean stashed tree; already recorded on sase-1ok.1

[2026-10-27T02:30:12Z · sase-1oh.4.1.3] recovery-surfaces done. Collector selects OPEN beads with an active completion_failure in addition to in_progress; failure.agent_name loads the origin run without changing the assignee; members merge once per artifact_dir. Reducer facts round-trip completion_failure; recovered OPEN unassigned work is stranded with reason=failed after settle grace; ordinary drafts stay out. Live claim_for_agent_launch successor owns; a new verified close drops the bead from the collector. In-progress parent with a live lander is blocked. Waiters using wait_for_beads stay parked until closed_bead_ids_for_waits sees the close (agent-only release still fires). Doctor project.beads WARNING uses the existing failed-cause sentence and %id(bead=…) #fork:… ACE Beads pane ⚐ is no longer gated on IN_PROGRESS. Docs: automatic reopen, one STITCH FAILED note, structured facts, waiter park. Facade completion_failure decode is a use-site import so TUI first-paint stays under the 3539 cap.

Verified: tests/test_stranded_collector_recovery.py (6), tests/test_stranded_recovery_surfaces.py (5: report after grace + one note on retry, live successor owns, new close clears, parent blocked, waiter parked), tests/test_stranded_work_facade.py::test_reduce_stranded_work_round_trips_open_recovery_facts, tests/doctor/_checks_beads_agents.py::test_project_beads_warns_about_recovered_unassigned_task, tests/ace/tui/test_artifacts_beads_stranded.py::test_open_unassigned_recovered_task_keeps_stranded_flag, tests/test_bead/test_close_provenance.py::TestCompletionFailureCodec::test_to_dict_round_trips. Host-recovery lander names: tests/test_finalizers_failed_close_recovery.py::TestFailedCloseRecovery::{test_recovery_reopens_close,test_recovery_names_missing_stitch,test_success_leaves_close_alone,test_successful_retry_leaves_close_alone}. sase tool run check 4809e2e7228d54c95e7afe944f6b3818: lint/mypy/symvision/docs green; 57802 passed; 1 NEW + 3 KNOWN are the pid-11111 capacity-scan env failures identical on the clean stashed tree (sase-1ok.1). epic-symbols clean. Did not close sase-1oh.4.1 / sase-1oh.4 / sase-1oh / sase-yo.

## Dependencies

- **Depends on:** [sase-1oh.4.1.1](sase-1oh.4.1.1.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oh.4.1.2](sase-1oh.4.1.2.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oh.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.3/README.md) | [sase-1oh.4.1.3](sase-1oh.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13abbfb`](https://github.com/sase-org/sase/commit/13abbfb01ed4df28e9330ce07b70c2c3d03ecae0) | feat(beads): surface recovered open work as stranded | [sase-1oh.4.1.3](sase-1oh.4.1.3.md) | 2026-10-26 22:59:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oh.4.1.3][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.3/README.md

<!-- sase:referenced-by:end -->
