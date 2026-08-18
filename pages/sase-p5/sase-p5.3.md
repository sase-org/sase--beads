# Bead: sase-p5.3 — Decide attribution from run-owned evidence

[Bead Pages](../README.md) / [sase-p5](README.md) / sase-p5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05d](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05d.md) · **Assignee:** `sase-p5.3` · **Size:** medium
**Created:** 2026-08-17 18:55:31 EDT · **Closed:** 2026-08-17 21:22:30 EDT
**Plan:** [202608/commit\_finalizer\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_attribution.md)

## Description

guard: teach the discarded-work guard to consult the run-owned commit ledger before declaring a discard, so a commit the run provably created counts as attributable even when its footer is missing.

## Notes

[2026-08-18T01:22:05Z · sase-p5.3] PROPOSED FOLLOW-UP: just check fails at lint (symvision) on master (pre-existing, unrelated to this phase) — the Justfile epic-symbol whitelist has stale entries for sase-p1.6(GlossaryConflictError, GlossaryMutationError, GlossaryMutationOutcome, GlossaryValidationError, add_glossary_term, delete_glossary_term): symvision reports each as already properly used and asks for the --epic-symbol entry to be removed. Confirmed via git stash that this reproduces on master without any of this phase's changes.

[2026-08-18T01:22:30Z · sase-p5.3] Reworked discarded_dirty_work_evidence in commit_finalizer_git_progress.py to consult the run-owned commit ledger (commit_results.json, written by the ledger phase) as a third attribution signal alongside the SASE_AGENT footer and agents-sync auto-commit TYPE: a newly reachable commit now counts as attributable when its SHA (or, if a rebase moved it, its tree) matches a ledger entry recorded for that repo. Ledger reads degrade to empty (footer-only behavior) on any missing/malformed file, never raise. Added git_log_commit_records (sha+tree+message) alongside the existing message-only helper, and threaded artifacts_dir through commit_finalizer.py's one call site. Added two tests to tests/llm_provider/test_commit_finalizer_no_progress.py: a footer-less but ledger-recorded commit now finalizes cleanly, and an unrelated ledger entry does not exempt a genuine footer-less foreign-agent discard. Verified: just fmt, just lint (ruff/mypy/keep-sorted/feature-flags/pyscripts/test-waits/changelog/patch-stitch-terminology) all green; tests/llm_provider/test_commit_finalizer_no_progress.py + sibling exemption tests (18 tests) pass; full just test-scoped diff-closure run (1709 tests) passes. just check's lint (symvision) step fails, but confirmed via git stash that this is a pre-existing, unrelated stale-whitelist issue present on master before this phase's changes; recorded as a PROPOSED FOLLOW-UP note on this bead. No --epic-symbol entries for sase-p5.3 per 'sase bead epic-symbols'.

[2026-08-18T01:23:13Z · sase-p5.3] Added run-owned commit ledger lookup to discarded_dirty_work_evidence (SHA/tree match against commit_results.json) so ledger-recorded commits without VCS footers finalize cleanly; threaded artifacts_dir through commit_finalizer.py; added git_log_commit_records. Verified: just fmt, full just check lint gates except symvision (pre-existing unrelated stale --epic-symbol whitelist failure confirmed on master via git stash), finalizer test suite (18 tests) and full scoped test-closure run (1709 tests) all pass. No --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-p5.2](sase-p5.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p5.4](sase-p5.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p5.3/README.md) | [sase-p5.3](sase-p5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0d36217`](https://github.com/sase-org/sase/commit/0d36217142f100ab232b5567d0ad5e0c6fcc2706) | feat(commit): attribute discarded commits via run-owned ledger | [sase-p5.3](sase-p5.3.md) | 2026-08-17 21:24:04 EDT |
