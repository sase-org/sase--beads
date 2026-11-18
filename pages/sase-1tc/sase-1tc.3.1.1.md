# Bead: sase-1tc.3.1.1 — Define and persist the crash-safe chop batch contract

[Bead Pages](../README.md) / [sase-1tc.3.1](sase-1tc.3.1.md) / sase-1tc.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) · **Assignee:** `sase-1tc.3.1.1` · **Size:** medium
**Created:** 2026-11-17 19:16:08 EST · **Closed:** 2026-11-17 21:15:48 EST
**Plan:** [202611/chop\_launch\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_launch_recovery.md)

## Description

journal: implement Rust batch wire types and reconciliation rules, registered PyO3 bindings, and a thin atomic Python store with process-safe ownership. See Phase journal.

## Notes

[2026-11-18T02:15:19Z · sase-1tc.3.1.1] Journal phase API record: Rust sase_core::axe_chop::batch (CHOP_BATCH_SCHEMA_VERSION=1) owns validate_chop_batch_manifest, apply_chop_batch_transition (begin_dispatch/acknowledge_launch/record_skip/mark_blocked/request_pause/resume/cancel_clan_generation), reconcile_chop_batch, summarize_chop_batch; PyO3 bindings chop_batch_wire_schema_version/validate_chop_batch_manifest/apply_chop_batch_transition/reconcile_chop_batch/summarize_chop_batch; sase facade in src/sase/core/axe_chop_facade.py (CHOP_BATCH_SCHEMA_VERSION + 4 functions); store src/sase/axe/chop_batch_store.py (pending_batches/ dir beside runs/, atomic temp+fsync+replace+dir-fsync writes, in-process mutex + flock mutation lock, separate ownership lock). Lock order for later phases: admission lock -> agent-name lock -> batch mutation lock -> batch ownership lock. Symvision whitelist rows keyed to sase-1tc.3.1 in Justfile _lint-symvision.

[2026-11-18T02:15:30Z · sase-1tc.3.1.1] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails identically on the clean base tree (measured 11,928,378 base footprint vs 11,924,777 hardcoded cap; journal phase adds only +665 bytes via sase.core.axe_chop_facade, inside the 4,096 allowance). The checked-in footprint cap is stale on master; needs a re-baseline by its owner, not by a launch-recovery phase.

[2026-11-18T02:15:36Z · sase-1tc.3.1.1] PROPOSED FOLLOW-UP: sase-core just check clippy fails on pre-existing manual_range_patterns lint in crates/sase_core/src/audit_query.rs:257 (file untouched at pinned HEAD c5e60d78; newer clippy than the code). Blocks the sase-core gate until its owner collapses the pattern; journal phase files are clippy-clean.

[2026-11-18T02:15:48Z · sase-1tc.3.1.1] Journal contract done and verified: Rust axe_chop::batch wire + transitions + reconcile + counts (12 lib tests pass), 5 additive PyO3 bindings (422 sase_core_py tests pass), sase facade + atomic store with separate mutation/ownership locks (27 store/facade tests pass). sase check: all lint stages pass including symvision (19 whitelist rows keyed to sase-1tc.3.1); 61832 tests pass with 1 failure proven identical on the clean tree (stale TUI import cap, recorded as follow-up). sase-core full lib suite 6124 pass; its gate clippy has 1 pre-existing audit_query lint (recorded as follow-up). Pin left untouched for host-completion landing.

## Dependencies

- **Blocks:** [sase-1tc.3.1.2](sase-1tc.3.1.2.md) ✓ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.1/README.md) | [sase-1tc.3.1.1](sase-1tc.3.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6cd9a0c`](https://github.com/sase-org/sase-core/commit/6cd9a0c2898850c8a81e90a23aca489cd742ba26) | feat(axe-chop): versioned crash-safe chop batch contract | [sase-1tc.3.1.1](sase-1tc.3.1.1.md) | 2026-11-17 21:17:51 EST |
| sase | [`c6b6da1`](https://github.com/sase-org/sase/commit/c6b6da1d2ca5dcbeebae8fab0beacb4f180ca345) | feat(axe): crash-safe chop batch store and facade | [sase-1tc.3.1.1](sase-1tc.3.1.1.md) | 2026-11-17 21:19:41 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.1/README.md

<!-- sase:referenced-by:end -->
