# Bead: sase-fq.2 — Give progress\_fingerprint an import symvision can see

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.2` · **Size:** small
**Created:** 2026-08-05 21:05:44 EDT · **Closed:** 2026-08-05 21:42:02 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

symvision-import: make commit_finalizer.py import progress_fingerprint explicitly instead of reaching it through a module alias, so the symvision lint stage stops reporting it as an unused public symbol.

## Notes

[2026-08-06T01:41:34Z · sase-fq.2] PROPOSED FOLLOW-UP: two tests are flaky under full `just check` parallel load but pass in isolation — tests/ace/tui/test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout. Neither touches commit_finalizer.py; likely timing sensitivity under worker contention. Worth investigating test isolation/timeouts.

[2026-08-06T01:42:02Z · sase-fq.2] Added progress_fingerprint to the explicit commit_finalizer_git import block in commit_finalizer.py (sorted alphabetically) and switched both call sites (lines 258, 300) from finalizer_git.progress_fingerprint(...) to the direct import. Verified: just _lint-symvision prints nothing and exits 0 (previously reported progress_fingerprint as an unused public symbol). just check: full suite ran 25551 passed, 7 skipped, 2 failed (test_loader_cleanup_decoupling.py::test_rows_apply_and_loading_clears_while_cleanup_is_blocked, test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout); both re-ran green in isolation and are unrelated to this change (no reference to commit_finalizer.py, unrelated commit history) — flaky under parallel load, logged as a proposed follow-up note on this bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.2/README.md) | [sase-fq.2](sase-fq.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a4a2c1a`](https://github.com/sase-org/sase/commit/a4a2c1a6004016667c71b50522be8807bb8368da) | fix(commit-finalizer): import progress\_fingerprint directly so symvision can see it | [sase-fq.2](sase-fq.2.md) | 2026-08-05 21:42:46 EDT |
