# Bead: sase-1jm.3.1.8.2 — Controller robustness, parent seams, and project display names

[Bead Pages](../README.md) / [sase-1jm.3.1.8](sase-1jm.3.1.8.md) / sase-1jm.3.1.8.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) · **Assignee:** `sase-1jm.3.1.8.2` · **Size:** medium
**Created:** 2026-10-11 19:18:51 EDT
**Plan:** [202610/agents\_archive\_view\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_landing_fixes.md)

## Description

controller-seams: stop off-thread probe errors from wedging the Archive controller. Drain a queued explicit open on idle, and coalesce overlapping idle rebuilds. Publish a typed found/owner/missing arrival outcome and clear unmatched exact names. Add the restored-row overlay seam with invalidation, and keep list option IDs unique. Show PROJECT_NAME on project banners through the project display snapshot.

## Dependencies

- **Depends on:** [sase-1jm.3.1.8.1](sase-1jm.3.1.8.1.md) ✓ · ⧖ 2026-10-11
- **Blocks:** [sase-1jm.3.1.8.3](sase-1jm.3.1.8.3.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.8.2/README.md) | [sase-1jm.3.1.8.2](sase-1jm.3.1.8.2.md) | 0 |
