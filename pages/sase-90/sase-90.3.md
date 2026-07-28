# Bead: sase-90.3 — Headless chat catalog with sync provenance

[Bead Pages](../README.md) / [sase-90](README.md) / sase-90.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-90.3` · **Size:** medium
**Created:** 2026-07-24 23:29:43 UTC
**Plan:** [sase/repos/plans/202607/artifacts\_chats\_subtab.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/artifacts_chats_subtab.md)

## Description

"Phase 3 — Headless provenance catalog" section: build a TUI-independent chat catalog that resolves each transcript's owning agent, classifies it as local / shared / remote / unknown against the agents sidecar checkout, and caches the expensive scans keyed by mtime and sidecar HEAD.

## Notes

COMMIT: ec79f1bc2

## Dependencies

- **Depends on:** [sase-90.1](sase-90.1.md) ✓
- **Blocks:** [sase-90.4](sase-90.4.md) ✓
- **Blocks:** [sase-90.5](sase-90.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-90.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-90.3/README.md) | [sase-90.3](sase-90.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7bb87b1`](https://github.com/sase-org/sase/commit/7bb87b1f54e9ed4da661fe169e11948740dfa595) | feat(history): add provenance-aware chat catalog (sase-90.3) | [sase-90.3](sase-90.3.md) | 2026-07-25 00:09:15 |
