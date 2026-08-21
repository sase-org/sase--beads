# Bead: sase-rm.12 — Make cache, snapshot, and fixed-flake accounting deterministic

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.12` · **Size:** medium
**Created:** 2026-08-20 14:47:58 EDT · **Closed:** 2026-08-21 05:25:15 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

test_isolation: replace process-wide read counting, isolate the agent-page cache, exclude dirty structural snapshot drift, and retire the committed Projects navigation fix correctly.

## Notes

[2026-08-20T20:06:24Z · sase-rm.12] CLOSE-READY sase-o1: Replaced process-wide builtins.open counting with module-owned sase.agent.artifact_files_cache._open_text. test_repeat_select_caches_content_read now patches that hook and still asserts repeat get_prompt_content() does not re-read the prompt body (baseline == 1). Added tests/agent/test_artifact_files_cache.py::test_read_text_uses_module_owned_open_hook. Verified: pytest tests/ace/tui/widgets/test_prompt_artifact_file_cache.py tests/agent/test_artifact_files_cache.py passed; just check green (scoped 633 files, 4 workers).

[2026-08-20T20:06:52Z · sase-rm.12] CLOSE-READY sase-nl: Isolated the agent-page URL TTL cache around the refresh node. Added module-owned _registry_snapshot_now (tests patch this instead of time.monotonic side_effect lists), pinned freshness_token, used a unique project/root, and routed hosted_link_resolver so concurrent resolves cannot increment this node's snapshot count. The refresh test now proves reuse until TTL and a snapshot at exactly TTL without weakening expiry. Autouse still clears _AGENT_PAGE_REGISTRY_SNAPSHOTS. Verified: tests/ace/tui/widgets/test_agent_page_url.py passed including test_resolve_agent_page_url_refreshes_after_snapshot_ttl; just check green.

[2026-08-20T20:07:20Z · sase-rm.12] CLOSE-READY sase-pr: Registered tests/completion/test_snapshot.py in _SOURCE_AUDIT_SCAN_ROOTS with roots src/sase/ and tests/completion/snapshots/ so dirty-tree argparse/snapshot failures are attributable_dirty_failures and no longer enter reproducible-flake accounting. Clean-tree snapshot failures still fail the owning pytest run and still meet the ordinary flake bar (regression tests in test_test_selection_health_dirty_audits.py). Both snapshot nodes pass on this tree (no live drift). Live baseline rows kept because the store still has 3 clean-tree failure records. Verified: tests/completion/test_snapshot.py (4 passed) and tests/test_test_selection_health_dirty_audits.py (11 passed); just check green.

[2026-08-20T20:07:47Z · sase-rm.12] CLOSE-READY sase-qo: Product fix b6779c4d6 (2026-08-19T01:29:14Z) is an ancestor of HEAD and _repaint_for_current_project is live. Replaced the live baseline row with `# fixed-at: 2026-08-19T01:29:14Z tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces`. Cross-navigation node and test_resolve_repaint_keeps_a_row_the_bookmark_has_not_caught_up_to both pass. Selection-store audit: 3 failure records; 2 before the fix instant; 1 after (2026-08-19T02:06:05Z) on de06c55ca which does not contain the fix — the known stale-tree limitation already documented in the baseline header. No unaccounted post-fix record on a tree that contains b6779c4d6.

[2026-08-21T09:16:17Z · sase-rm.12] PROPOSED FOLLOW-UP: Closed flag bead sase-rk still has live admin_center_config_hub definition — just check fails at tools/check_feature_flags because registry/schema/tests still reference the flag after sase-rk was closed.

[2026-08-21T09:24:24Z · sase-rm.12] PROPOSED FOLLOW-UP: Current master has unrelated finalizer contract/telemetry drift — just test-scoped escalated to the full suite and failed tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection plus telemetry finalizer catalog/count nodes; this phase diff does not touch those surfaces.

[2026-08-21T09:25:15Z · sase-rm.12] Implemented test_isolation fixes: module-owned artifact read hook, agent-page TTL clock/cache isolation, dirty completion snapshot attribution, and sase-qo fixed-at retirement. Verified: just install succeeded; focused pytest for the four task conditions passed (50 passed); just check reached the feature-flag gate and failed on unrelated closed flag bead sase-rk/admin_center_config_hub (follow-up noted); direct just test-scoped escalated to the full suite and failed unrelated contract manifest/finalizer telemetry nodes (follow-up noted); sase bead epic-symbols sase-rm.12 reported no entries.

[2026-08-21T09:26:45Z · sase-rm.12] Verified focused tests passed for artifact file cache seam, agent page TTL clock seam, selection-health dirty audit roots, and reproducible flake baseline retirement; epic-symbols reported no entries; unrelated red gates were recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Blocks:** [sase-rm.13](sase-rm.13.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rm.12/README.md) | [sase-rm.12](sase-rm.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96257e1`](https://github.com/sase-org/sase/commit/96257e1fb34f28f3f28e5b42ce815b056211f92a) | fix(test): make cache and flake accounting deterministic | [sase-rm.12](sase-rm.12.md) | 2026-08-21 05:27:46 EDT |
