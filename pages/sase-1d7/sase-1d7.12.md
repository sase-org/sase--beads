# Bead: sase-1d7.12 — Rust ack API, lean unread index, and store generations

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.12` · **Size:** large
**Created:** 2026-09-30 07:18:22 EDT · **Closed:** 2026-09-30 16:58:42 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

core-unread-ack-index: move completion acks and the unread completion index into sase_core as lean GIL-released calls that return dismissed ids and a store generation, then replace the Python read-sequence fence with store generations.

## Notes

[2026-09-30T20:57:31Z · sase-1d7.12] PROPOSED FOLLOW-UP: just check stays red on unrelated pre-existing gates, all reproduced on the clean base tree with this phase stashed: (1) lint feature-flags rule 7, closed flag bead sase-1dg still has a surviving public_bead_attachments definition; (2) test_tui_app_import_stays_under_startup_budget, 3499 modules vs 3485 budget on base (this phase adds 0 net modules after deferring the wire import); (3) test_runtime_tick_skipped_in_rail; (4) ImportError collecting widgets/test_agent_header_panel.py (test_hint_document_forces_expansion missing from sibling module); (5) test_empty_panel_semicolon pilot timeout, passes in isolation (parallel flake). sase-core sase tool run check is green; sase lint gates through mypy are green.

## Dependencies

- **Blocks:** [sase-1d7.13](sase-1d7.13.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.2](sase-1d7.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.8](sase-1d7.8.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.9](sase-1d7.9.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.12.md) | [sase-1d7.12](sase-1d7.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@28befcb`](https://github.com/sase-org/sase-core/commit/28befcb9e411d2e5f8a8fd2405186cd3b393631d) | feat(notifications): store generations, ack API, and lean unread index | [sase-1d7.12](sase-1d7.12.md) | 2026-09-30 17:01:15 EDT |
