# Bead: sase-fr.1 — Durable close history in the bead event reducer

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.1` · **Size:** medium
**Created:** 2026-08-05 21:18:21 EDT · **Closed:** 2026-08-05 21:47:23 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

core-model: add BeadCloseRecordWire and IssueWire.close_history to sase-core, archive close metadata instead of discarding it on every reopen path, unify the mutation and reducer paths on one helper, and release.

## Dependencies

- **Blocks:** [sase-fr.2](sase-fr.2.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.1/README.md) | [sase-fr.1](sase-fr.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@66011f5`](https://github.com/sase-org/sase-core/commit/66011f590d27b4727fb045246e1700c202b1789b) | feat(bead): archive close metadata instead of destroying it on reopen | [sase-fr.1](sase-fr.1.md) | 2026-08-05 21:47:35 EDT |
