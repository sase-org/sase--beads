# Bead: sase-13.3 — Phase 3: VCS Computation

[Bead Pages](../README.md) / [sase-13](README.md) / sase-13.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-13.3`
**Created:** 2026-04-29 00:30:19 UTC · **Closed:** 2026-04-29 01:00:30 UTC
**Plan:** [202604/deltas\_field.md](https://github.com/sase-org/sase--plans/blob/main/202604/deltas_field.md)

## Description

Implement compute_deltas(changespec, vcs_provider) with parent/head ref resolution and a new abstract diff_name_status() VCS method. Implementations for each VCS provider (bare git, GitHub PR, Mercurial).

## Notes

COMMIT: 8a5a6805

## Dependencies

- **Depends on:** [sase-13.2](sase-13.2.md) ✓
- **Blocks:** [sase-13.5](sase-13.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`858fa7e`](https://github.com/sase-org/sase/commit/858fa7e1a99b7f431eacec8d90acb87b1d9591ce) | feat(deltas): compute DELTAS from VCS state (sase-13.3) | [sase-13.3](sase-13.3.md) | 2026-04-29 01:00:34 |
