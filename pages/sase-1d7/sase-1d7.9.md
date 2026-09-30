# Bead: sase-1d7.9 — Cheap unread jumps and footer probe

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.9` · **Size:** medium
**Created:** 2026-09-30 07:18:18 EDT · **Closed:** 2026-09-30 14:52:49 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

unread-jump-fast-path: drop the unconditional trailing tab refresh from the unread jump keys, keep detail behind the debounce, reveal only the target panel, make the footer probe O(1), and key the jump-candidate cache by generations with remove-on-ack.

## Notes

[2026-09-30T18:52:25Z · sase-1d7.9--1] PROPOSED FOLLOW-UP: just check fails identically on clean base (git stash) — 14 scoped failures incl. test_app_import_budget (3493 vs 3485 cap, tracked by sase-13p/sase-18s), test_agents_node_rail_wiring::test_runtime_tick_skipped_in_rail, force_reuse launch-seam origin typed-vs-generated (tracked by sase-18s), plus artifact/config/completion contract nodes (tracked by sase-1de); symvision private-import errors in bead/attachments audience+doctor from e1f10caa (untouched by this phase)

[2026-09-30T18:52:49Z · sase-1d7.9--1] Phase unread-jump-fast-path done: trailing tab refresh dropped from ,j/,J, target-panel-only rebuild, O(1) footer probe, generation-keyed jump cache with remove-on-ack. Verified: 89 focused tests pass (jump_fast_path, unread_done_navigation*, stopped_navigation, leader_keymap_dispatch); ruff check+format clean; epic-symbols empty; full just check 14 scoped + symvision failures reproduce identically on clean base (stash) and triage no_new_failures — recorded as PROPOSED FOLLOW-UP citing sase-1de/sase-18s/sase-13p.

## Dependencies

- **Blocks:** [sase-1d7.12](sase-1d7.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.8](sase-1d7.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.9.md) | [sase-1d7.9](sase-1d7.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f98939`](https://github.com/sase-org/sase/commit/9f989395b5f158a1a0b11dddfde36c3a7dedca58) | feat(agents): cheap unread jumps and footer probe (sase-1d7.9) | [sase-1d7.9](sase-1d7.9.md) | 2026-09-30 14:54:35 EDT |
