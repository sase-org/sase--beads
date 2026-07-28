# Bead: sase-6v.3 — Structured chop results and runner-executed launches

[Bead Pages](../README.md) / [sase-6v](README.md) / sase-6v.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6v.3`
**Created:** 2026-07-18 19:41:48 UTC
**Plan:** [202607/chops\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/chops_redesign.md)

## Description

'Structured chop results and runner-executed launches' section: introduce the versioned chop result document, parse proposed agent launches from it, execute launches in the runner with scaffold injection and workflow-reference rejection, extend the run-history lifecycle beyond launch, and add verbose/dry-run manual-run debugging.

## Notes

Implemented versioned structured chop results, per-run result/context files, fail-closed parsing and workflow-reference rejection, sequential runner-owned proposal launches with scaffold/env/wait linkage, launched-to-action lifecycle finalization, persisted/list/dashboard/TUI statuses, and -n/--dry-run plus -V/--chop-verbose CLI UX. Verification: just lint passes; 36 focused tests pass; SASE_PYTEST_EXCLUDE_VISUAL=1 just test passes (18,474 passed, 7 skipped); all 8 AXE PNG snapshots pass. Required just check was run; after fixing its one relevant artifact-audit failure, the only residual failures are 34 unrelated Agents-tab PNG goldens with tiny renderer pixel drift. No goldens were rewritten.

## Dependencies

- **Depends on:** [sase-6v.2](sase-6v.2.md) ✓
- **Blocks:** [sase-6v.4](sase-6v.4.md) ✓
