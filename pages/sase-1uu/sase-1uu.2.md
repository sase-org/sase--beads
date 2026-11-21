# Bead: sase-1uu.2 — Gate aggregate write retries and publish rebuilds on the caller deadline

[Bead Pages](../README.md) / [sase-1uu](README.md) / sase-1uu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ew](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ew.md) · **Assignee:** `sase-1uu.2` · **Size:** medium
**Created:** 2026-11-21 10:59:30 EST · **Closed:** 2026-11-21 12:26:47 EST
**Plan:** [202611/artifact\_link\_aggregate\_timeouts.md](https://github.com/sase-org/sase--plans/blob/main/202611/artifact_link_aggregate_timeouts.md)

## Description

Make _write_merged_aggregate stop retrying after a lost CAS race when the next preview cannot finish before the caller's deadline. Thread the deadline through rebuild_aggregate, reconcile_aggregate, and the publish-path apply_events_to_aggregate, with typed deferral handling in both chops. Add per-sub-phase publish timings.

## Notes

[2026-11-21T17:26:21Z · sase-1uu.2] PROPOSED FOLLOW-UP: tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe fails on the clean base tree (selected set includes the 20260501 run it expects protected) — likely a date-relative fixture; confirmed identical with this phase stashed.

[2026-11-21T17:26:26Z · sase-1uu.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails on the clean base tree under host load — confirmed identical with this phase stashed; budget or measurement needs review.

[2026-11-21T17:26:32Z · sase-1uu.2] PROPOSED FOLLOW-UP: docs/reference/automation/notification-gates.md is 6,009 words (cap 6,000) so `lint (docs contract)` fails just check on the clean base; already recorded under sase-1uu.1 (related sase-1sr tracks a separate schema correction on that page).

[2026-11-21T17:26:37Z · sase-1uu.2] Implemented publish_deferral = retain. _write_merged_aggregate(deadline=) raises ArtifactLinkAggregateWriteDeferred (attempts, last_compute_seconds) after a lost CAS when now+last_compute >= deadline, or before the first compute when already expired; deadline=None keeps 5 attempts with a forced last. Threaded through rebuild_aggregate, reconcile_aggregate (returns on-disk aggregate + "reconcile deadline expired; aggregate write deferred after a concurrent writer"), reconcile_and_repair (skips dangling_scan/repair), apply_events_to_aggregate and _publish_event_objects_locked (aggregate_ready=False, deferred=True, diagnostic "artifact-link aggregate projection deferred past deadline"). Report.phase_seconds lists admission/states/roots/local_receipts/beads/aggregate; drain appends publish.<name> after publish; backfill drain-phases line prints them after publish. Behavior change worth knowing: an already-expired deadline now defers the publish aggregate rebuild too, so test_outbox_deadline_retains_operations_then_retry_acks_once now expects all 3 rows retained, then 3 drained on retry (uses==1).

[2026-11-21T17:26:47Z · sase-1uu.2] Verified: new tests for deadline-gated _write_merged_aggregate (defer / retry / expired / deadline=None), reconcile deferral + repair skip, backfill deferral without record_reconcile, publish retain outcome + six phase_seconds, drain publish.* keys, and backfill log line all pass; tests/sdd (560) and agents_sync + backfill suites pass; ruff and mypy clean. sase tool run check passed every lint gate except docs contract (notification-gates.md 6,009/6,000 words, fails identically on the clean base). just test-scoped escalated to the full lane: 62720 passed, 4 failed — one was mine (monkeypatch.undo in a publisher test, fixed); the other two real failures (test_continuation_retention, test_app_import_budget) reproduce on the clean base and are recorded as PROPOSED FOLLOW-UPs. Epic-symbols clear.

## Dependencies

- **Depends on:** [sase-1uu.1](sase-1uu.1.md) ✓ · ⧖ 2026-11-21
- **Blocks:** [sase-1uu.3](sase-1uu.3.md) ◐ · ⧖ 2026-11-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1uu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uu.2/README.md) | [sase-1uu.2](sase-1uu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`555e30d`](https://github.com/sase-org/sase/commit/555e30d83289d6a669210704c272884596aa8c09) | feat(artifact-links): gate aggregate write retries and publish rebuilds on the caller deadline | [sase-1uu.2](sase-1uu.2.md) | 2026-11-21 12:28:05 EST |
