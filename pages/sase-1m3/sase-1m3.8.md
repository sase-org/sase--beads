# Bead: sase-1m3.8 — Python project-stats loader, facade, and view model

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.8` · **Size:** medium
**Created:** 2026-10-16 22:05:24 EDT · **Closed:** 2026-10-17 11:59:04 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

loader: add `sase.stats.project.load_project_stats`, which resolves projects, tiers their repos, builds the request, calls the binding, and returns a frozen `ProjectStatsView`, plus the facade, pin bump, and the `sase disk` cache row.

## Notes

[2026-10-17T13:33:59Z · 8k] PROPOSED FOLLOW-UP: Stats attribution decision record remains deferred because the parent plan selected stats_decision_record=no; no memory or decision record was edited.

[2026-10-17T13:34:39Z · 8k] Implemented the missing Python loader phase in the current workspace: sase.core.project_stats_facade, sase.stats.project query/request/view/loader modules, typed frozen response records, cache/project_stats disk inventory row, contributor documentation, and pin ratchet to landed core 7a46109f. Focused Python tests: 36 passed; mypy passes for all 7 new source modules; ruff passes. Integration found two core plan-reader gaps, fixed locally with Rust regressions: root sidecar plans_dir="." must count plans, and an unresolved separate repo must not fall back to primary code plans; plans cache schema bumped to invalidate old root-store results. Rust binding rebuild, binding smoke, and required checks in both repos remain before closure. No epic-symbol row is needed for load_project_stats because its package facade already re-exports it; Symvision rejected that redundant row, which was removed.

[2026-10-17T14:28:33Z · 8k--1] Resolved the 13 Symvision findings by privatizing module-local response helper records and the request wrapper; no exemptions added. Verification after the fixes: just fix passed, just _lint-symvision passed, mypy passed for all 7 new source modules, and all 38 focused loader/request/real-binding/disk tests passed. The rebuilt binding includes both core plan-store regressions. Full sase-core check is running as 5f673d7c1a79f61a0092bce3e7e3f568; the final sase check and closure remain.

[2026-10-17T15:59:04Z · 8k--1] Completed the shared project-stats facade, query/request builder, loader, frozen view records, cache disk inventory, documentation, and core plan-store fixes. Verification: 38 focused tests passed; just fix, standalone Symvision, mypy, all main lint/validation/docs gates passed; full sase-core check 5f673d7c1a79f61a0092bce3e7e3f568 passed. Main check 96055bc147dee311f42f3b0cf94b4346 ran the full suite: 56,326 passed, 25 failed, 31 skipped. Its 13 KNOWN signatures have independent witnesses; all eight NEW signatures reproduce on clean HEAD c68a30365f616b8096e5e7ff02cd5e0b43cbca20 without these changes and were corroborated on existing sase-1hy, sase-1l3, sase-1ia, and sase-1ma reports. Evidence: file:explicit:8d7a5979cc12fda81813545a. No memory edits; decision-record deferral remains recorded. Parent sase-1m3 remains open. Host finalization must commit both repos and advance the core revision pin past the plan-store fixes.

[2026-10-17T19:19:08Z · 8k--1] Conflict repair verification: file:explicit:815b1938887e431dcbb99ce1. Retained core pin 3b3b7401 (direct child of upstream bbef21d0), preserving both sides. Reviewed all integrated statistics paths and added test-only finalizer environment isolation plus the commit-provenance terminology exception. Focused verification: 53 passed. Mandatory main check d5e65fc9304d6e2e1d904031506c4f1c FAILED: 27 failed, 56340 passed, 31 skipped; all lint/docs stages passed. Clean upstream snapshot independently reproduced 20 failures, and two timing tests passed unchanged reruns. Four remaining prompt/session failures overlap sase-1ia/sase-1l3 coverage; no blanket KNOWN verdict claimed. Macro resource failure is an existing globally ignored plan exposed by sandbox HOME. PROPOSED FOLLOW-UP: preserve the global-ignore boundary in repository terminology scans and investigate the remaining gate failures using the attached evidence; do not treat this gate as green.

[2026-10-17T20:24:49Z · 8k--1] Second conflict repair: publication encountered incoming mobile-pairing commit 667a5a83c0. Resolved the core pin to 916d5e3a, which includes both 3b3b7401 statistics fixes and the mobile API. All 16 replayed paths retain the prior reviewed repair. Updated evidence: file:explicit:b86b2d80eafbf649cd5961e2. Matching binding validation and 93 focused tests passed. Mandatory main check 48cec9b93899864ca76f9ae4fd6e13b0 FAILED: 23 failed, 56365 passed, 31 skipped; all format/lint/validation/docs stages passed. Thirteen final failed nodes have independent upstream-baseline witnesses. Six newly appearing failures reran as four prompt/header/session failures and two passes (archive navigation and process reaping flakes). PROPOSED FOLLOW-UP: use the exact evidence to reconcile remaining prompt/hint failures with sase-1hy, sase-1ia, and sase-1l3; investigate unmatched failures without treating the gate as green. The generated baseline snapshot was removed after script lint scanned it; logs are preserved.

[2026-10-19T10:11:11Z · sase-1m3.8] CLOSED-BEAD LAUNCH: agent sase-1m3.8 launched against this closed bead; status left closed.
Launch submitted 2026-10-19T10:09:21.015891Z; run 20261019060923.
Prior close: 2026-10-17T15:59:04Z · done.

[2026-10-19T10:13:20Z · sase-1m3.8] Closed-phase verification: implementation commit 2cae86a1aa (feat(stats): add shared project statistics loader) is an ancestor of current HEAD. Reviewed the loader phase design and landed facade, request builder, frozen view records, disk cache inventory, and documentation. Re-ran tests/stats/test_project_request.py, tests/stats/test_project_loader.py, tests/stats/test_project_binding.py, and tests/core/test_disk_footprint_inventory.py: 38 passed in 10.01s, including the real Rust binding cold/warm-cache smoke test. sase bead epic-symbols sase-1m3.8 reports no entries. No implementation or memory edits were needed; the phase remains closed and no ancestor was closed.

[2026-10-19T10:13:29Z · sase-1m3.8] Verified landed commit 2cae86a1aa, all 38 focused tests passed, and no epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1m3.2](sase-1m3.2.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.3](sase-1m3.3.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.4](sase-1m3.4.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1m3.9](sase-1m3.9.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.8.md) | [sase-1m3.8](sase-1m3.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:8k--1][1] | Check phase scope and outstanding acceptance before finishing verification and closing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.8k.md

<!-- sase:referenced-by:end -->
