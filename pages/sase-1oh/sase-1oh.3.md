# Bead: sase-1oh.3 — Make a crate-version mismatch converge in the bead read model (sase-1nw)

[Bead Pages](../README.md) / [sase-1oh](README.md) / sase-1oh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14m.md) · **Assignee:** `sase-1oh.3` · **Size:** large
**Created:** 2026-10-26 14:14:59 EDT · **Closed:** 2026-10-26 16:13:20 EDT
**Plan:** [202610/backlog\_epic\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_top_five_task_beads.md)

## Description

read-model: reproduce the stale crate_version read-model cache that every reader rebuilds and rolls back, fix the sase-core rebuild/commit path so it converges, move the sase core pin, and close sase-1nw.

## Notes

[2026-10-26T20:13:05Z · sase-1oh.3] PROPOSED FOLLOW-UP: lander owns a /sase_gate for an athena reinstall of sase once master contains this core fix and the sase-core-revision.txt pin. Do not reinstall globally or publish that gate before the host has landed the pin. global-install-is-human-only applies.

Fix/test evidence (local, not live): crate-version mismatch recovery is in sase-core store.rs/tail.rs plus tests_version.rs. just test -p sase_core bead::read_model: 34 passed, including 10 version-convergence tests (snapshot/indexed/mutation recovery; later hits with aged sweep and 0 table rewrites; invalidation-fault still publishes crate_version; stale rebuild vs invalidation is Fault::Cache with 0 table rewrites; stale rebuild vs winner does not overwrite; racing readers converge; held connection stays readable). sase-core sase tool run check c1bca66c2532bfc38d091a7ce3eab98d succeeded. sase sase tool run check ac24f5f87321c4dbe40e3fa23d7cc5c0 succeeded.

Acceptance procedure for the gate:
1. Confirm the installed core includes the fix and identify any parked runners still using an older loaded extension.
2. Read cache metadata with a normal read-only SQLite connection (WAL-aware, not immutable=1), trigger the first normal bead read, and verify the stored crate_version and replay parity become current.
3. Observe later reads and an existing parked runner across at least two 60s fallback intervals. Confirm rebuild/content generations stay stable without store changes and the reported full-cache WAL churn is gone; ordinary telemetry writes are not failures.

Record the gate identity when settling sase-1nw. Leave sase-1nw open until that live acceptance is done.

[2026-10-26T20:13:20Z · sase-1oh.3] Reproduced a crate_version=0.40.0 cache in sase-core tests: snapshot, indexed, and mutation-admission reads rebuilt forever via token fast-path after failed in-place invalidation, and CasLost open_and_serve treated invalidated leftover rows as a Hit. Fix: rebuild() cold-rebuilds on version mismatch; write_snapshot_in_txn CAS-checks generation before table rewrites and persists schema/reducer/crate versions with the snapshot; open_and_serve probes freshness so a CAS loser serves a winner only when it is still fresh. just test -p sase_core bead::read_model: 34 passed (10 new tests_version cases). sase-core check c1bca66c2532bfc38d091a7ce3eab98d succeeded. sase check ac24f5f87321c4dbe40e3fa23d7cc5c0 succeeded. Host must push linked sase-core then write sase-core-revision.txt. Live athena reinstall is a PROPOSED FOLLOW-UP on this phase for the lander /sase_gate after master contains the pin; sase-1nw stays open until that acceptance.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oh.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.3.md) | [sase-1oh.3](sase-1oh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7b88b98`](https://github.com/sase-org/sase-core/commit/7b88b98d40162590c4226192fa27993f08d024a5) | fix(bead-read-model): converge crate-version mismatch recovery | [sase-1oh.3](sase-1oh.3.md) | 2026-10-26 16:14:28 EDT |
