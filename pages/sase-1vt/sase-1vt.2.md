# Bead: sase-1vt.2 — Advance next\_counter past every relocation and stream ID

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.2` · **Size:** small
**Created:** 2026-11-27 15:24:25 EST · **Closed:** 2026-11-27 16:01:13 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

counter: make the bead conflict resolver write config.json next_counter past every relocation ID and every stream ID in the store, even when config.json itself merged cleanly, so a rollback-and-retry never re-mints a relocated ID.

## Notes

[2026-11-27T21:01:13Z · sase-1vt.2] Resolver now raises config.json next_counter past every stream/relocation ID even on clean config merges (floor from max_counter_in_ids over all store streams, never the relocation pool cursor); conflicted-config path takes max of floor and pool cursor; writes skipped when the counter would not rise. Reworded the false counter comment in cli_work_from_plan_launch.py. Added tests/test_bead/test_conflict_resolver_counter.py (3 tests: clean-merge relocation floor, fresh ID after remove+recreate, no-rewrite on high counter); verified the relocation test fails without the fix. just check (sase tool run check, escalated to full suite) passed.

## Dependencies

- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.2/README.md) | [sase-1vt.2](sase-1vt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`324d63e`](https://github.com/sase-org/sase/commit/324d63e8ef61980edc5d4e7e3dfd33c20042bf64) | fix(bead): advance next\_counter past every relocation and stream ID | [sase-1vt.2](sase-1vt.2.md) | 2026-11-27 16:03:09 EST |
