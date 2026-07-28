# Bead: sase-96.8.7 — Reap the managed SASE temp root

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.8.7` · **Size:** medium
**Created:** 2026-07-25 18:16:19 UTC · **Closed:** 2026-07-25 20:36:25 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Reap the managed SASE temp root' section: add a bounded reaper for the root get_sase_managed_tmpdir returns, with per-subdirectory horizons that respect how long the ACE Agents tab reads artifacts back, and wire it to a path that actually runs without blocking an interactive command. Nothing reaps that root today despite the helper documenting it as reapable.

## Dependencies

- **Depends on:** [sase-96.8.2](sase-96.8.2.md) ✓
- **Depends on:** [sase-96.8.3](sase-96.8.3.md) ✓
- **Blocks:** [sase-96.8.8](sase-96.8.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.8.7/README.md) | [sase-96.8.7](sase-96.8.7.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`15a5a0e`](https://github.com/sase-org/sase/commit/15a5a0e67ad521644e7b85063aaefba5798b2adf) | feat(axe): reap the managed SASE temp root (sase-96.8.7) | [sase-96.8.7](sase-96.8.7.md) | 2026-07-25 20:37:45 |
