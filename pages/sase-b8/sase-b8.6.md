# Bead: sase-b8.6 — Lane-based plan and bead agent associations

[Bead Pages](../README.md) / [sase-b8](README.md) / sase-b8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b8.6` · **Size:** medium
**Created:** 2026-07-30 14:32:52 UTC · **Closed:** 2026-07-30 16:06:06 UTC
**Plan:** [202607/family\_scoped\_agent\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202607/family_scoped_agent_provenance.md)

## Description

assoc: make plan-header and bead-page AGENTS rows label the lane once, resolve their link from the artifact member or the footer's recorded destination, and stop listing a member and its lane as two agents.

## Notes

[2026-07-30T16:06:06Z · sase-b8.6] Implemented lane-normalized plan-header and bead-page agent associations with member/footer/registry link precedence, lane-keyed bead commit counts, family-aware hosted lane URLs, and legacy member-tag compatibility. Verified: just install; focused association/link suite 57 passed; isolated suite-gate retry passed; formatting, Ruff, mypy, pyscripts, changelog, Symvision, and toobig checks passed; full suite 24,298 passed and 7 skipped, with only two unrelated linked sase-core artifact-query wire v3-vs-v2 failures plus the contended suite-gate timeout that passed alone. Full just check reaches SASE validation, which is independently blocked by six existing July plan/prompt reverse-link errors.

[2026-07-30T16:07:08Z · sase-b8.6] Finalizer verification: focused association/link suite passed 57 tests; isolated worker-gate retry passed; formatting, Ruff, mypy, Symvision, and size checks passed; full suite passed 24,298 tests with only two unrelated linked Rust-wire mismatches.

## Dependencies

- **Depends on:** [sase-b8.2](sase-b8.2.md) ✓
- **Blocks:** [sase-b8.8](sase-b8.8.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b8.6/README.md) | [sase-b8.6](sase-b8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`78522a3`](https://github.com/sase-org/sase/commit/78522a318c48a33c3622d05b1885a8d045cbbbe0) | fix: normalize agent associations by lane | [sase-b8.6](sase-b8.6.md) | 2026-07-30 16:07:56 |
