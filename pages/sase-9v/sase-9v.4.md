# Bead: sase-9v.4 — Git probe failures must never read as clean

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.4` · **Size:** small
**Created:** 2026-07-26 15:32:15 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

probe_fail_closed: make bead_state_is_clean fail closed on probe errors, treat unexpected `git diff --cached` exit codes as errors in commit_sdd_files, and include unmerged_error in repository blockers and rollback-mismatch verification, finishing the sase-9r.3 sweep.

## Notes

Implemented fail-closed git probe handling for bead_state_is_clean, unexpected cached-diff exits in commit_sdd_files, and unmerged_error blockers/rollback verification. Focused regressions and affected test files pass. just check lint/validation stages passed, but full parallel pytest still failed in unrelated llm_provider alias tests that passed when rerun directly.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9v.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9v.4/README.md) | [sase-9v.4](sase-9v.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f3680c3`](https://github.com/sase-org/sase/commit/f3680c3c9d0a8a1680887a8754abbf288e4392bb) | fix: fail closed on sdd git probe errors (sase-9v.4) | [sase-9v.4](sase-9v.4.md) | 2026-07-26 16:47:40 |
