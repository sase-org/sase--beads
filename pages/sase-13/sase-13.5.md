# Bead: sase-13.5 — Phase 5: Sync Integration & CLI

[Bead Pages](../README.md) / [sase-13](README.md) / sase-13.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-13.5`
**Created:** 2026-04-29 00:30:26 UTC · **Closed:** 2026-04-29 01:12:05 UTC
**Plan:** [202604/deltas\_field.md](https://github.com/sase-org/sase--plans/blob/main/202604/deltas_field.md)

## Description

Wire update_changespec_deltas_field into all lifecycle hooks (commit entries, rewind, sync, accept-proposal, re-parent) and add sase changespec sync-deltas -c <cl_name> manual recompute CLI.

## Dependencies

- **Depends on:** [sase-13.3](sase-13.3.md) ✓
- **Depends on:** [sase-13.4](sase-13.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5336866`](https://github.com/sase-org/sase/commit/53368663b086f5e7d4e9f889465b40f07ada75e0) | feat(deltas): wire DELTAS sync into lifecycle hooks + sync-deltas CLI (sase-13.5) | [sase-13.5](sase-13.5.md) | 2026-04-29 01:16:31 |
