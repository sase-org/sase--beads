# Bead: sase-fa.2 — Remove the sidecar\_publication chop and publications lumberjack

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.2` · **Size:** medium
**Created:** 2026-08-05 14:26:32 EDT · **Closed:** 2026-08-05 16:15:26 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

chop: delete the builtin chop, its console script, the `publications` axe lane, its tests, and the lock-deadline plumbing that existed only to bound that chop.

## Notes

[2026-08-05T20:13:31Z · sase-fa.2] PROPOSED FOLLOW-UP: axe residue left for phase repair — ~/.sase/axe/lumberjacks/publications/ (including sidecar_publication_backoff.json and chops/sidecar_publication/) is now dead state and should be removed in the repair phase residue cleanup.

[2026-08-05T20:13:48Z · sase-fa.2] PROPOSED FOLLOW-UP: src/sase/doctor/checks_agent_publication.py::_publication_drain_issue and src/sase/agents_sync/publication_outbox_diagnostics.py still name the removed `publications` lane / `sidecar_publication` chop, so they now emit an always-false "not draining" diagnostic and recommend an unknown chop; phase queue (sase-fa.3) owns reverting both per the plan — confirm it lands.

[2026-08-05T20:14:10Z · sase-fa.2] PROPOSED FOLLOW-UP: docs/beads.md, docs/agents_sidecar.md, docs/sdd.md, and docs/commit_workflows.md still describe commit-time publication as queued for the `publications` lane (agents_sidecar.md:360 even recommends `sase axe chop run sidecar_publication -L publications`, now an unknown chop); phase land owns this prose sweep.

[2026-08-05T20:14:28Z · sase-fa.2] PROPOSED FOLLOW-UP: two tests are flaky under the parallel `just test` run but pass in isolation — tests/notification_store/test_mute_snooze.py::TestMarkMuted::test_unmute_clears_snooze and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout (41s under load vs 3.9s alone); both are timing-sensitive and unrelated to this phase.

[2026-08-05T20:15:26Z · sase-fa.2] Deleted the sidecar_publication chop (src/sase/scripts/sase_chop_sidecar_publication.py, 546 lines) and its test (tests/test_axe_chop_sidecar_publication.py, 310 lines), removed the sase_chop_sidecar_publication console script from pyproject.toml [project.scripts] (block stays sorted), and removed the publications lane from axe.lumberjacks in src/sase/default_config.yml.

Reverted the 0d6ed1a19 lock-deadline plumbing only where it became unused: dropped lock_timeout_seconds from bead_pages/publication.py::_publish_bead_lineage and sdd/plan_header_refresh.py::_refresh_committed_plan_header (both now call store_git_write_lock without a timeout again), dropped the timeout branch from sdd/_git_contention.py::store_git_write_lock_factory, and unthreaded lock_timeout from bead/sync.py, bead/_sync_publication.py, and bead/sync_worker.py (run_managed_sync_worker/_run_locked_sync/_integrate_with_transient_dirty_retry restored to their pre-epic shapes). store_git_write_lock(timeout=...) and its other production callers are untouched.

Deleted the now-unreachable drain entry points the chop was the only caller of: drain_bead_pages_publication, drain_plan_header_publication, drain_sidecar_push_publication (plus the TYPE_CHECKING SidecarPublicationRequest imports they needed). Per symvision, privatized drain_agent_publications to _drain_agent_publications and dropped its and publish_committed_agent_hood's unused lock_timeout_seconds parameter, restoring the pre-epic publish_committed_agent_hood signature. Deleted rather than whitelisted, as the plan directs.

Docs: docs/axe.md restored to the pre-epic five-lane diagram and 'Axe ships with five default lumberjacks', deleted the '### publications (30-second interval)' section and the 'sase axe chop run sidecar_publication -L publications' examples; docs/configuration.md dropped the publications lane from the axe.lumberjacks example and restored the pre-epic 'Successful agent commit/PR workflows publish the committing hood' prose.

Verified: 'sase axe lumberjack list' shows five default lanes with no publications; 'sase axe chop list' shows no sidecar_publication; 'sase axe chop run sidecar_publication' fails with "Error: unknown chop 'sidecar_publication'". 'just lint' is fully green including symvision and toobig; 'just fmt' is a no-op on the result. Full 'just test' ran 25790 passed / 7 skipped with 2 failures (tests/notification_store/test_mute_snooze.py::TestMarkMuted::test_unmute_clears_snooze and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout) that both pass in isolation and are load-timing flakes unrelated to this phase; noted as a follow-up. Targeted suites all green: tests/agents_sync (264), bead sync/worker/conflict + sdd git-contention + sdd commit-store (61), and the 1432-test axe/lumberjack/chop/config selection.

Left to sibling phases and recorded as PROPOSED FOLLOW-UP notes: the doctor '_publication_drain_issue' and publication_outbox_diagnostics lane/chop references (phase queue owns them per the plan), the docs/beads.md + agents_sidecar.md + sdd.md + commit_workflows.md prose sweep (phase land), and the dead axe state at ~/.sase/axe/lumberjacks/publications/ including sidecar_publication_backoff.json (phase repair residue cleanup).

## Dependencies

- **Depends on:** [sase-fa.1](sase-fa.1.md) ✓
- **Blocks:** [sase-fa.3](sase-fa.3.md) ◐
- **Blocks:** [sase-fa.5](sase-fa.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.2/README.md) | [sase-fa.2](sase-fa.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e99f501`](https://github.com/sase-org/sase/commit/e99f5017d39fc15f6a8f5082fbd82ed2d768a2db) | feat!: remove the sidecar\_publication chop and publications lumberjack | [sase-fa.2](sase-fa.2.md) | 2026-08-05 16:17:49 EDT |
