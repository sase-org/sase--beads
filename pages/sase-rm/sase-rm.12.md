# Bead: sase-rm.12 — Make cache, snapshot, and fixed-flake accounting deterministic

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.12` · **Size:** medium
**Created:** 2026-08-20 14:47:58 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

test_isolation: replace process-wide read counting, isolate the agent-page cache, exclude dirty structural snapshot drift, and retire the committed Projects navigation fix correctly.

## Notes

[2026-08-20T20:06:24Z · sase-rm.12] CLOSE-READY sase-o1: Replaced process-wide builtins.open counting with module-owned sase.agent.artifact_files_cache._open_text. test_repeat_select_caches_content_read now patches that hook and still asserts repeat get_prompt_content() does not re-read the prompt body (baseline == 1). Added tests/agent/test_artifact_files_cache.py::test_read_text_uses_module_owned_open_hook. Verified: pytest tests/ace/tui/widgets/test_prompt_artifact_file_cache.py tests/agent/test_artifact_files_cache.py passed; just check green (scoped 633 files, 4 workers).

[2026-08-20T20:06:52Z · sase-rm.12] CLOSE-READY sase-nl: Isolated the agent-page URL TTL cache around the refresh node. Added module-owned _registry_snapshot_now (tests patch this instead of time.monotonic side_effect lists), pinned freshness_token, used a unique project/root, and routed hosted_link_resolver so concurrent resolves cannot increment this node's snapshot count. The refresh test now proves reuse until TTL and a snapshot at exactly TTL without weakening expiry. Autouse still clears _AGENT_PAGE_REGISTRY_SNAPSHOTS. Verified: tests/ace/tui/widgets/test_agent_page_url.py passed including test_resolve_agent_page_url_refreshes_after_snapshot_ttl; just check green.

[2026-08-20T20:07:20Z · sase-rm.12] CLOSE-READY sase-pr: Registered tests/completion/test_snapshot.py in _SOURCE_AUDIT_SCAN_ROOTS with roots src/sase/ and tests/completion/snapshots/ so dirty-tree argparse/snapshot failures are attributable_dirty_failures and no longer enter reproducible-flake accounting. Clean-tree snapshot failures still fail the owning pytest run and still meet the ordinary flake bar (regression tests in test_test_selection_health_dirty_audits.py). Both snapshot nodes pass on this tree (no live drift). Live baseline rows kept because the store still has 3 clean-tree failure records. Verified: tests/completion/test_snapshot.py (4 passed) and tests/test_test_selection_health_dirty_audits.py (11 passed); just check green.

[2026-08-20T20:07:47Z · sase-rm.12] CLOSE-READY sase-qo: Product fix b6779c4d6 (2026-08-19T01:29:14Z) is an ancestor of HEAD and _repaint_for_current_project is live. Replaced the live baseline row with `# fixed-at: 2026-08-19T01:29:14Z tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces`. Cross-navigation node and test_resolve_repaint_keeps_a_row_the_bookmark_has_not_caught_up_to both pass. Selection-store audit: 3 failure records; 2 before the fix instant; 1 after (2026-08-19T02:06:05Z) on de06c55ca which does not contain the fix — the known stale-tree limitation already documented in the baseline header. No unaccounted post-fix record on a tree that contains b6779c4d6.

## Dependencies

- **Blocks:** [sase-rm.13](sase-rm.13.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rm.12/README.md) | [sase-rm.12](sase-rm.12.md) | 0 |
