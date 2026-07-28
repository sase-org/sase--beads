# Bead: sase-w.7 — Phase 7 — Event-Driven Auto-Refresh + Small Wins

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.7`
**Created:** 2026-04-27 16:17:46 UTC · **Closed:** 2026-04-27 18:37:27 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Event-driven auto-refresh in actions/event_handlers.py + util/fs_watcher.py: track _dirty_changespecs, _dirty_agents, _dirty_axe, _last_full_sanity_refresh; watcher events flip dirty flags; auto-refresh only does refreshes whose flag is set + slow FULL_SANITY_REFRESH_SECONDS=60 floor. Falls back to existing polling on non-Linux. AXE list rendering disk-free: widgets/bgcmd_list.py + actions/axe_loaders.py — parent option formatting uses precomputed counts (len(lumberjack_names)), no load_axe_config() during row render. ANSI parse cache for AXE output keyed by (source_id, mtime_ns, size, tail_hash) in widgets/axe_dashboard.py — append-only logs parse only new tail; 500-line tails reuse cached parse on hash match. Saved-query cache: SearchQueryPanel.render no longer calls load_saved_queries(); actions/startup.py loads once into self._saved_queries; invalidated only on save/delete. Idempotent footer: widgets/keybinding_footer.py stores _last_bindings_signature, _last_status_signature; skips on match; caches child widget refs in on_mount. Lazy startup data: defer xprompt snippet loading and custom keymap resolution until first use. Acceptance: watcher-active + no FS changes → no full load_agents_from_disk; BgCmdList.update_list() no disk reads; unchanged AXE refresh never calls Text.from_ansi; cold startup first paint independent of snippet loading.

## Notes

COMMIT: 2befd98d

## Dependencies

- **Depends on:** [sase-w.6](sase-w.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0c8d55f`](https://github.com/sase-org/sase/commit/0c8d55f6413de8d90d49272e3d3a0bd05fd49d8d) | feat(ace/tui/perf): event-driven auto-refresh + small wins (sase-w.7) | [sase-w.7](sase-w.7.md) | 2026-04-27 18:37:31 |
