# Bead: sase-12.2 — Phase 2 — Route kill-all through \_do\_bulk\_kill\_agents

[Bead Pages](../README.md) / [sase-12](README.md) / sase-12.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-12.2`
**Created:** 2026-04-28 22:45:14 UTC · **Closed:** 2026-04-28 23:12:03 UTC
**Plan:** [202604/tui\_perf\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_v2.md)

## Description

Replace the per-agent loop in _kill_and_dismiss_all_agents with a single _do_bulk_kill_agents(killable, dismissable) call so kill-all becomes one optimistic UI transaction with one persistence worker. See plans/202604/tui_perf_v2.md (Phase 2).

## Notes

COMMIT: 465236f8

## Dependencies

- **Depends on:** [sase-12.1](sase-12.1.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`70d6438`](https://github.com/sase-org/sase/commit/70d64381bc23af079c3fc6e31ec8f651b2a670f2) | feat(ace/tui): route kill-all through \`\_do\_bulk\_kill\_agents\` (sase-12.2) | [sase-12.2](sase-12.2.md) | 2026-04-28 23:12:07 |
