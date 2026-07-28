# Bead: sase-90.1 — Chat file discovery covers imported remote transcripts

[Bead Pages](../README.md) / [sase-90](README.md) / sase-90.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-90.1` · **Size:** small
**Created:** 2026-07-24 23:29:37 UTC
**Plan:** [sase/repos/plans/202607/artifacts\_chats\_subtab.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/artifacts_chats_subtab.md)

## Description

"Phase 1 — Chat file discovery" section: add a chats-specific file walker that yields YYYYMM shards, legacy top-level files, and the imported `v2-*` shard directories, then route the existing chat storage/catalog/resume helpers through it so imported remote transcripts stop being invisible.

## Notes

COMMIT: 62faa5f51

## Dependencies

- **Blocks:** [sase-90.3](sase-90.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-90.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-90.1/README.md) | [sase-90.1](sase-90.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e7da5cd`](https://github.com/sase-org/sase/commit/e7da5cd18d378bf10a0289e849f028816e2b813f) | fix(history): discover imported chat transcripts (sase-90.1) | [sase-90.1](sase-90.1.md) | 2026-07-24 23:45:46 |
