# Bead: sase-e8.5 — Pane-independent commit snapshots in the prompt bar

[Bead Pages](../README.md) / [sase-e8](README.md) / sase-e8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ry](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ry/README.md) · **Assignee:** `sase-e8.5` · **Size:** medium
**Created:** 2026-08-02 14:05:26 UTC · **Closed:** 2026-08-02 16:00:02 UTC
**Plan:** [202608/commit\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_ref_completion.md)

## Description

tui_commits: replace the mounted-Commits-pane projection with a TTL-revalidated background snapshot from the shared inventory, show a loading row while the first snapshot lands, and render commit rows with a dimmed repo segment and no duplicated detail.

## Notes

[2026-08-02T16:00:02Z · sase-e8.5] Verified pane-independent @commit: completion via project-scoped shared-core snapshots with 2s TTL revalidation, cold loading state, rank/scope/body and truncation passthrough, 12-character parse round-trip, and dimmed repo-segment rendering; focused completion tests and full just check (including PNG visual snapshots) pass.

[2026-08-02T16:01:18Z · sase-e8.5] Verified focused completion tests and full just check, including PNG visual snapshots and 12-character commit payload parser round-trip coverage.

## Dependencies

- **Depends on:** [sase-e8.3](sase-e8.3.md) ✓
- **Blocks:** [sase-e8.6](sase-e8.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e8.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e8.5/README.md) | [sase-e8.5](sase-e8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`6b7284c`](https://github.com/sase-org/sase/commit/6b7284ce4d21a62c274bf016c9c6ef9ca4ece0f2) | feat(ace-tui): load prompt commit snapshots independently | [sase-e8.5](sase-e8.5.md) | 2026-08-02 16:02:30 |
