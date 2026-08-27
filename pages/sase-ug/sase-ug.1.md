# Bead: sase-ug.1 — One projection for the machine-local read model

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.1` · **Size:** medium
**Created:** 2026-08-26 14:48:24 EDT · **Closed:** 2026-08-26 15:14:23 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

converge: make every writer of `artifact-links.json` produce the same row set, so the read model stops flapping by 233 rows an hour and `cites`/`read` stop vanishing.

## Notes

[2026-08-26T19:13:48Z · sase-ug.1] PROPOSED FOLLOW-UP: just check / just check-full fail repo-wide (pre-existing, unrelated to this phase) at gate 'lint (test waits)': tools/check_test_wait_helpers flags tests/test_notification_gate_durability.py:69 as fixed-sleep-missing-pragma. Reproduces identically on clean master@0f51e8b77 before any of this phase's changes. Needs a '# sase-test-wait: <reason>' pragma (or a helper-based wait) on that sleep; task_type=ci.

[2026-08-26T19:14:23Z · sase-ug.1] Implemented phase converge per plan:202608/link_rail_every_tab.md. Extracted project_aggregate_rows() (sase/sdd/_artifact_link_store_support.py) as the single keep/drop rule shared by preview_aggregate() and preview_reconciled_aggregate(); the two now differ only in which stores they scan. Removed _row_is_publishable from both local-read-model preview paths -- durable_sidecar_rows() keeps that filter, docstring now states it serves publication only. Added a monotonic generation to the aggregate document (empty doc, load/read, all writers); rebuild_aggregate()/reconcile_aggregate() now go through a bounded CAS retry (_write_merged_aggregate/_write_aggregate_if_current) that recomputes and merges instead of clobbering when a concurrent writer (chop vs workspace) advanced the generation first. _upsert_aggregate_row/_remove_aggregate_rows/_write_aggregate bump generation on every write; load_aggregate/these helpers read via one read_aggregate_document() to avoid re-entering the flock (which would deadlock).

Added tests/sdd/test_artifact_link_store_aggregate.py::test_every_aggregate_writer_converges_regardless_of_publish_status (rebuild_aggregate and reconcile_aggregate, both orders, land on the same row set with an unresolvable agent endpoint -- the regression test for the live defect) and ::test_stale_preview_is_rejected_and_retried_rather_than_clobbering (CAS rejection + retry-merge). Rewrote tests/sdd/test_artifact_link_store_reconcile.py's tests that had asserted the old (buggy) publishability-drops-rows behavior on reconcile_aggregate/preview_reconciled_aggregate; that coverage now lives on durable_sidecar_rows, which still filters.

Verified: full tests/sdd, tests/doctor, tests/main/test_artifact_cli_link_health.py green (525 passed, 1 pre-existing unrelated failure in test_checks_beads.py deselected -- reproduces on clean master). just check gates run individually: fmt, keep-sorted, ruff, mypy, feature-flags, pyscripts, changelog, patch/stitch terminology, symvision, toobig, validate, validate-committed-plans all pass; test-scoped (4080 passed, 5 skipped, 0 failed). just check's 'lint (test waits)' gate fails but reproduces identically on clean master (tests/test_notification_gate_durability.py:69, unrelated file) -- filed as a PROPOSED FOLLOW-UP note on this bead rather than blocking. Live re-measurement against the real gh_sase-org__sase project (read-only preview, no aggregate write): preview_reconciled_aggregate() now returns 1321 rows; replaying the old chop-context publishability filter against those same rows shows it would still drop 17 read rows today (the mechanism is time-varying -- fewer than the original 233 since more agents have since published). Also recorded the corrected diagnosis as a note on bead:sase-ua per the plan (left its status/scope for the owner).

## Dependencies

- **Blocks:** [sase-ug.2](sase-ug.2.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ug.3](sase-ug.3.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ug.4](sase-ug.4.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.1/README.md) | [sase-ug.1](sase-ug.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`452ac54`](https://github.com/sase-org/sase/commit/452ac54cf967dae7f8974eec522dd564007d6545) | fix(sdd): converge artifact-link aggregate projections on one read model | [sase-ug.1](sase-ug.1.md) | 2026-08-26 15:15:17 EDT |
