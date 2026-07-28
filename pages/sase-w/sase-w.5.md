# Bead: sase-w.5 — Phase 5 — Incremental Agent Loading + Deferred Heavy Detail

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.5`
**Created:** 2026-04-27 16:17:08 UTC · **Closed:** 2026-04-27 18:00:25 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add AgentSnapshotCache in src/sase/ace/tui/actions/agents/_snapshot_cache.py (or near existing loader) keyed by signatures of project files, agent artifact dirs, attempt metadata files, retry_state.json, dismissed bundles, tag file. Expose load_agents(*, changespec_snapshot, force=False). Pass cached ChangeSpec snapshot through (no re-call of find_all_changespecs() inside loader). Cache load_attempt_history(artifacts_dir) by attempt-dir/file mtimes. Cache retry state by (path, mtime_ns, size). Defer dismissed-bundle expansion until panel visible. Use existing fs_watcher to invalidate affected agents instead of dropping whole snapshot. Add agent-detail two-phase update in widgets/agent_detail.py + actions/agents/_display.py: immediate (title/status + cached prompt summary); idle/debounced (file/thinking/diff workers fire only after detail debouncer settles, gated by monotonic _agent_detail_generation token; stale results dropped). Acceptance: idle auto-refresh shows ~0 work; 50-agent j/k burst spawns workers only for final selection; attempt history not re-read for every agent.

## Notes

COMMIT: 38194722

## Dependencies

- **Depends on:** [sase-w.4](sase-w.4.md) ✓
- **Blocks:** [sase-w.6](sase-w.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6ed849a`](https://github.com/sase-org/sase/commit/6ed849a8a850587b4e9d5394f34ab1c344292694) | feat(ace/tui/perf): AgentSnapshotCache + two-phase agent detail (sase-w.5) | [sase-w.5](sase-w.5.md) | 2026-04-27 18:00:28 |
