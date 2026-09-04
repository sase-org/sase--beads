# Bead: sase-w0.4 — One mark set, global clear, and the marked-work aggregate

[Bead Pages](../README.md) / [sase-w0](README.md) / sase-w0.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.5.md) · **Assignee:** `sase-w0.4` · **Size:** small
**Created:** 2026-09-03 06:53:45 EDT · **Closed:** 2026-09-03 19:18:04 EDT
**Plan:** [202609/unified\_updates\_tab\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_updates_tab_1.md)

## Description

marks: collapse the two disjoint mark sets into one keyed by row identity with the verb derived from the row, make Escape clear every mark including filter-hidden ones, let A consume CLI marks from anywhere, and show a marked-work aggregate that a filter cannot hide.

## Notes

[2026-09-03T23:18:04Z · sase-w0.4] Unified Updates marks onto one _marked set of row keys. Verified: plugin marks survive Installed-scope hide and are consumed by i; CLI marks are consumed by A after a filter hides every CLI row; Esc clears mixed plugin+CLI marks in one press and reports the total; filter-hidden marks stay in the aggregate with the hidden count; prune drops marks whose rows lost install/mark_update; I marks CLI rows; jump-filter reuse no longer keeps stale [hint] prefixes. Lint (ruff/mypy/symvision) green; marks/jump/install/scopes tests pass; rebaselined marked-install and CLI-highlight PNG goldens (just test-visual 22 passed).

## Dependencies

- **Depends on:** [sase-w0.2](sase-w0.2.md) ✓ · ⧖ 2026-09-03
- **Blocks:** [sase-w0.5](sase-w0.5.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w0.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w0.4/README.md) | [sase-w0.4](sase-w0.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b558cc3`](https://github.com/sase-org/sase/commit/b558cc379c0295e5d132efe7b2e7341bfa36b849) | feat(ace): unify Updates tab marks into one row-key set | [sase-w0.4](sase-w0.4.md) | 2026-09-03 19:20:30 EDT |
