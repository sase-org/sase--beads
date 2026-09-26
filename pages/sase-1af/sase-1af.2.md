# Bead: sase-1af.2 — Consume source metadata and expose it consistently

[Bead Pages](../README.md) / [sase-1af](README.md) / sase-1af.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1v](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1v.md) · **Assignee:** `sase-1af.2` · **Size:** medium
**Created:** 2026-09-26 07:23:43 EDT · **Closed:** 2026-09-26 08:47:41 EDT
**Plan:** [202609/routine\_source\_nav\_sections.md](https://github.com/sase-org/sase--plans/blob/main/202609/routine_source_nav_sections.md)

## Description

python_origin: ratchet the core revision and expose typed origin through cached config, CLI, and Services details.

## Notes

[2026-09-26T12:47:03Z · sase-1af.2--1] PROPOSED FOLLOW-UP: just check symvision fails on clean base tree with 5 stale --epic-symbol entries (sase-19x.4 phase_card_block/block_meta_for_session_shell/session_reply_heading closed; sase-19f format/resolve_queue_capacity_multiplier already properly used); Justfile untouched as foreign work

[2026-09-26T12:47:41Z · sase-1af.2--1] python_origin complete: core rev 3568b38d, typed source/declared_by via AxeInventoryEntry, cached config origin map with token invalidation and degraded-config fallback, CLI list/detail source display, Services collector atomic apply; verified 40 passed (test_axe_routine_origin, test_axe_cli_lumberjack, test_axe_config_actions); just check blocked only by 5 pre-existing stale --epic-symbol entries that reproduce identically on clean base tree (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1af.1](sase-1af.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1af.3](sase-1af.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1af.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1af.2.md) | [sase-1af.2](sase-1af.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f18d28`](https://github.com/sase-org/sase/commit/6f18d282928335b49ab9000a7fa38c2a4f62a927) | feat(axe): expose routine declaring source through config, CLI, and Services | [sase-1af.2](sase-1af.2.md) | 2026-09-26 08:50:24 EDT |
