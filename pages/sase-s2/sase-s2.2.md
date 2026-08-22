# Bead: sase-s2.2 — Hold approved epic launches through developer source swaps

[Bead Pages](../README.md) / [sase-s2](README.md) / sase-s2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0an](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0an.md) · **Assignee:** `sase-s2.2` · **Size:** medium
**Created:** 2026-08-22 12:48:39 UTC · **Closed:** 2026-08-22 13:48:26 UTC
**Plan:** [202608/plan\_approval\_launch\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_approval_launch_reliability.md)

## Description

swap-safe-epic-launch: keep direct bead work fail-fast while making the detached host-owned epic launcher wait outside the editable SASE import boundary, then execute exactly once from a fresh process under the existing code-swap reader protection.

## Notes

[2026-08-22T13:47:37Z · sase-s2.2] PROPOSED FOLLOW-UP: just check SASE validation still fails at init memory --check (chezmoi home shim drift, same 7 files already tracked on sase-n0) — this phase did not regenerate memory.

[2026-08-22T13:47:53Z · sase-s2.2] PROPOSED FOLLOW-UP: tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift fails under xdist (already tracked on sase-rv) — unrelated to swap-safe epic launch.

[2026-08-22T13:48:26Z · sase-s2.2] Host-owned epic launches wait in a stdlib bootstrap (no sase import) for the code-swap shared lock, then exec sase bead work once while the lock is held. Direct sase bead work still fail-fast (test_cli_work_code_swap_lock). Monitor and fallback-proc paths share guarded execution argv while labels/fingerprints/resume commands stay logical sase bead work; sidecar persists execution argv for restart. 62 focused tests passed; lint (fmt/ruff/mypy/symvision/toobig) passed; no --epic-symbol leftovers. just check validate is blocked by pre-existing sase-n0 chezmoi memory drift; test-scoped 4954 passed with one pre-existing sase-rv failure.

## Dependencies

- **Blocks:** [sase-s2.3](sase-s2.3.md) ✓ · ⧖ 2026-08-22

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f8a0dd8`](https://github.com/sase-org/sase/commit/f8a0dd8585d364db9c0f92fcb676f4f6c951c367) | feat: Hold approved epic launches through developer source swaps (sase-s2.2) | [sase-s2.2](sase-s2.2.md) | 2026-08-22 13:51:00 UTC |
