# Bead: sase-w.6 — Phase 6 — Artifact + Render Caching: Large Prompts/Replies/Diffs/Logs

[Bead Pages](../README.md) / [sase-w](README.md) / sase-w.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-w.6`
**Created:** 2026-04-27 16:17:23 UTC · **Closed:** 2026-04-27 18:17:38 UTC
**Plan:** [202604/tui\_perf\_overhaul\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/tui_perf_overhaul_1.md)

## Description

Add AgentArtifactCache in src/sase/agent/agent_artifacts_cache.py keyed by (agent identity, artifacts_dir, file path, mtime_ns, size, attempt, view mode, terminal width). Caches: prompt-file selection, prompt content, raw xprompt, response content, chat response, timestamped reply chunks, live-reply tail, prebuilt Rich renderables where safe. Live-reply uses TailCache(path, size, offset, text) reading only appended bytes when size grows; resets on shrink. Lazy/capped Rich Syntax: SYNTAX_HIGHLIGHT_MAX_BYTES=64_000, SYNTAX_HIGHLIGHT_MAX_LINES=1_500; above cap render plain Text with notice; optionally schedule highlight after idle if selection stable. Diffs: highlight only visible/trimmed range first. Apply in widgets/prompt_panel/_agent_display.py, widgets/file_panel/_display.py, widgets/axe_dashboard.py. Diff worker dedupe + cache in widgets/file_panel/_diff.py: DiffCacheKey = (agent_identity, workspace_path, vcs_provider_name, worktree_fingerprint) (workspace + .git/index mtime/size + 2s TTL fallback for active agents). _inflight_diff_tasks: dict[DiffCacheKey, Worker]. Acceptance: re-select same agent doesn't re-glob prompts; 5MB response paints immediately as plain text; re-select active agent with unchanged worktree doesn't call diff_with_untracked() again.

## Notes

COMMIT: c56c53ea

## Dependencies

- **Depends on:** [sase-w.5](sase-w.5.md) ✓
- **Blocks:** [sase-w.7](sase-w.7.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`a4f97a7`](https://github.com/sase-org/sase/commit/a4f97a7fb1d564f28cc856a6f787f12688ec1db8) | feat(ace/tui/perf): artifact + render caching (sase-w.6) | [sase-w.6](sase-w.6.md) | 2026-04-27 18:17:42 |
