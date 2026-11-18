# Bead: sase-1t3.11.1.4 — Reuse targeted audit queries for artifact-read history

[Bead Pages](../README.md) / [sase-1t3.11.1](sase-1t3.11.1.md) / sase-1t3.11.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.11.md) · **Assignee:** `sase-1t3.11.1.4` · **Size:** medium
**Created:** 2026-11-17 12:30:56 EST · **Closed:** 2026-11-17 22:10:59 EST
**Plan:** [202611/bounded\_log\_queries.md](https://github.com/sase-org/sase--plans/blob/main/202611/bounded_log_queries.md)

## Description

artifact_reads: extend the audit-query contract to artifact events, remove the full artifact-read snapshot, and prove event, ordering, and context parity.

## Notes

[2026-11-18T03:10:41Z · sase-1t3.11.1.4] PROPOSED FOLLOW-UP: Reconcile the stale TUI import-footprint budget — tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget caps the closure at 11,924,777 bytes, while clean HEAD 4894d4199101 measures 11,930,555 (+5,778); this phase leaves it at 11,929,953 (602 bytes lower than HEAD), so the same cap assertion still fails on the clean base. The failure was recorded by check witness 065f0c1540c74cda711a7a8ec22d0edf.

[2026-11-18T03:10:59Z · sase-1t3.11.1.4] Implemented the Rust-backed targeted artifact-read query, removed the full-log snapshot cache, and preserved selection, order, dedupe, cap, and freshness behavior. Rust fast/full checks and artifact query tests passed; focused Python tests passed; final SASE check run a2e4239876e9b24514083d6c71dc4322 passed. Recorded the clean-base TUI import-footprint cap failure as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-1t3.11.1.3](sase-1t3.11.1.3.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1t3.11.1.5](sase-1t3.11.1.5.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.11.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t3.11.1.4/README.md) | [sase-1t3.11.1.4](sase-1t3.11.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3992fce`](https://github.com/sase-org/sase-core/commit/3992fce8871f13adaac332e66c791cf9a91df47c) | feat(audit-query): query artifact-read audit logs | [sase-1t3.11.1.4](sase-1t3.11.1.4.md) | 2026-11-17 22:13:55 EST |
