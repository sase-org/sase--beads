# Bead: sase-4u.4 — Phase 4: Migrate the chezmoi repo + skill/docs + chezmoi apply --force

[Bead Pages](../README.md) / [sase-4u](README.md) / sase-4u.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4u.4`
**Created:** 2026-06-17 21:57:00 UTC · **Closed:** 2026-06-17 23:49:50 UTC
**Plan:** [202606/flatten\_memory\_nested\_long.md](https://github.com/sase-org/sase--plans/blob/main/202606/flatten_memory_nested_long.md)

## Notes

Completed Phase 4: migrated the chezmoi source memory root to flat notes with canonical frontmatter, refreshed home AGENTS/README, updated the sase_memory_read skill source/docs and regenerated provider skill files, ran chezmoi apply --force, and verified with SASE just check plus init/skill drift checks. Chezmoi just check is blocked only on missing busted for nvim tests; fmt/lint/python/bash checks passed.

## Dependencies

- **Depends on:** [sase-4u.3](sase-4u.3.md) ✓
- **Blocks:** [sase-4u.5](sase-4u.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4u.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4u.4/README.md) | [sase-4u.4](sase-4u.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`41bed16`](https://github.com/sase-org/sase/commit/41bed160a1fd26512650df835fd4f4f4d7db0165) | docs: update flat memory guidance (sase-4u.4) | [sase-4u.4](sase-4u.4.md) | 2026-06-17 23:55:56 |
