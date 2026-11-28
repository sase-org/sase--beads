# Bead: sase-1vy.2 — Federation cache-only reads must not report stale snapshots as ok (sase-1aw)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.2` · **Size:** medium
**Created:** 2026-11-28 03:14:45 EST · **Closed:** 2026-11-28 05:34:20 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

federation-freshness: fix sase-1aw. Read sase-1aw and all of its notes first. Cache-only federation reads ignore the last network failure and label the stale cache ok; the bug body carries the reproduction and proposed fix. Make cache-only reads surface the failure instead of a stale ok. Add or update a regression test for the stale-after-failure shape. Run sase tool run check, then close sase-1aw and the phase bead.

## Notes

[2026-11-28T10:34:20Z · sase-1vy.2] Fixed cache-only federation reads to return stale cached payloads with the last read error until a network read succeeds. Regression test covers failure, post-backoff cache-only reads, and recovery. Focused worker test passed; sase-core sase tool run check fed32e0746d90f2f4a5d31298c90e04b passed. Left related task bead sase-1aw unchanged per instruction to close only this phase bead.

## Dependencies

- **Depends on:** [sase-1vy.1](sase-1vy.1.md) ✓ · ⧖ 2026-11-28
- **Blocks:** [sase-1vy.3](sase-1vy.3.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vy.2/README.md) | [sase-1vy.2](sase-1vy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a1b9d8d`](https://github.com/sase-org/sase-core/commit/a1b9d8d14a7c71b8c8e4921ed414afe1f78f76e6) | fix(federation): preserve cache failures in cache-only reads | [sase-1vy.2](sase-1vy.2.md) | 2026-11-28 05:35:59 EST |
