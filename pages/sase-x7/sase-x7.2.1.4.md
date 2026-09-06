# Bead: sase-x7.2.1.4 — Rehearse the kit on real data across Linux and macOS

[Bead Pages](../README.md) / [sase-x7.2.1](sase-x7.2.1.md) / sase-x7.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) · **Assignee:** `sase-x7.2.1.4` · **Size:** medium
**Created:** 2026-09-05 19:32:06 EDT
**Plan:** [202609/migration\_kit.md](https://github.com/sase-org/sase--plans/blob/main/202609/migration_kit.md)

## Description

kit-rehearsal: Run the synthetic edge-case matrix and protected real-data rehearsals on athena and mac from isolated checkouts, prove restoration and interrupted-run resume, and publish the per-host operation manifests plus the acceptance receipt that later cutover phases consume.

## Notes

[2026-09-06T03:51:39Z · sase-x7.2.1.4] Athena leg of kit-rehearsal complete; mac leg blocked on reachability (SSH to kellys-macbook-pro.tail297af1.ts.net timed out on every attempt this phase, matches tailnet note that it is offline unless the lid is open). Not closing per the plan's explicit stop condition against Linux-only evidence.

Synthetic matrix: added the remaining required cases as tests -- tests/migration_kit/test_synthetic_matrix.py (mixed matched/unmatched proc rows, symlink escape, archive destination conflict, concurrent lock holder via a real TimeoutError from migration_acquire_bounded_lock, disk-full via an injected OSError(ENOSPC) writer seam proven recoverable via resume_run, and an additional real-tmpfs ENOSPC variant mounted in an unprivileged user+mount namespace) plus tests/migration_kit/test_backup.py::test_apply_reports_corrupted_sqlite_source. Canonical no-op, exact conversion, and interrupted-write/resume were already covered by test_driver.py. just check is clean.

Real-data rehearsal on athena: snapshotted live ~/.sase's residue and import-leg roots (cp -a, moved off tmpfs to disk-backed /var/tmp to avoid RAM pressure) into an isolated scratch root, then ran the full sase migrate CLI against the copy only (no production data mutated; scratch and its rehearsal backups deleted after measurement, small JSON evidence logs kept). backup --apply: ok, 498,529 members, 10.55GB, 1 sqlite store integrity-checked ok, 2m23s. import-purge plan/run --apply/verify: ok end to end on real import-leg residue (79 artifacts/809 bundles/3 journals/2 receipts/2 caches purged and verified empty). procs-residue: correctly refused -- all 22 real tasks.jsonl rows (2026-08-14) are unmatched against the current procs.jsonl (101 rows, all >=2026-08-29), proving the marker-is-not-proof defense on real data; see PROPOSED FOLLOW-UP note. state-residue: correctly refused at the whole-manifest level (plan-approval and user-question both have live notification references; agent-tags alone would be archivable but the gate is all-or-nothing by design). lock-residue: resolves census F3 definitively -- code-swap.lock is classify_only (not written by current code), code-swap-v2.lock is refuse_archive_current_writer (src/sase/dev_update/code_swap_lock.py). restore dry-run verified all 498,529 checksums with 0 failures and correctly reported the diff introduced by the import-purge apply; restore --apply performed the staged swap cleanly and the purged residue came back. Two real SIGKILL attempts against a live import-purge apply both raced to completion (operation too fast past its digest-recompute step to catch mid-flight); interrupted-write/resume mechanics are proved instead by the synthetic matrix (both the pre-existing abort-seam test and the new genuine-ENOSPC test drive the same resume_run/journal-replay path a real kill would hit).

sase bead epic-symbols sase-x7.2.1.4 is clean (no --epic-symbol entries).

Draft per-host manifests (athena, apollo) and the rehearsal receipt are written locally at /var/tmp/sase-x7-2-1-4-rehearsal/evidence/{athena_manifest,apollo_manifest,rehearsal_receipt}.md, held back from `sase artifact create` until the mac leg is folded in, per the plan's explicit "no Linux-only close" rule. Once mac is reachable: rehearse the same matrix there (clone off-worktree, build sase_core_rs from source into a throwaway uv venv, confirm the backup root is outside iCloud sync), complete its deferred G3 probe (distributions/entry points/completions/launchd/cron -- kit-backup explicitly deferred this to this phase's reachability window), fold the results into the receipt and manifest, publish all three as artifacts, then close.

[2026-09-06T03:52:07Z · sase-x7.2.1.4] PROPOSED FOLLOW-UP: procs-residue can never archive athena's real tasks.jsonl residue as scoped -- all 22 real legacy rows (created 2026-08-14) are unmatched against the current procs.jsonl (101 rows, all created 2026-08-29 or later), because the canonical proc store only retains a rolling recent window rather than every historical record. local-state-cutover needs either a human-verified manual archive path for residue whose canonical siblings have already rotated out, or a widened reconciliation rule (e.g. accept a legacy row as safe when no live proc record of any kind references its id and it predates the canonical store's oldest retained row). Filing as a note per phase-worker rules rather than a bead; the epic's land agent should triage this into a task bead for local-state-cutover.

## Dependencies

- **Depends on:** [sase-x7.2.1.3](sase-x7.2.1.3.md) ✓ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.4/README.md) | [sase-x7.2.1.4](sase-x7.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`16153bf`](https://github.com/sase-org/sase/commit/16153bf5606f085fcd1b13b58b188cb7eb4af954) | test(migration-kit): rehearse remaining synthetic edge-case matrix | [sase-x7.2.1.4](sase-x7.2.1.4.md) | 2026-09-05 23:53:32 EDT |
