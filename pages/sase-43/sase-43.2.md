# Bead: sase-43.2 — Phase 2: Sender API, CLI, Catalog, and \`done\`

[Bead Pages](../README.md) / [sase-43](README.md) / sase-43.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-43.2`
**Created:** 2026-05-24 00:11:49 UTC · **Closed:** 2026-05-24 00:46:50 UTC
**Plan:** [202605/notification\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202605/notification_tags.md)

## Notes

COMMIT: 601f2eeb5

[2026-07-27T19:06:10Z · sase-a1.6] [2026-05-24T00:45:09Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented Phase 2 notification tags: notify_workflow_complete accepts normalized tags; successful user-agent JumpToAgent completions are tagged done while failures are not; sase notify create/list/show and catalog JSON expose tags with CLI tag creation, tag query matching, and --tag filtering; docs and focused tests updated. Verification: SASE_CORE_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase-core/sase-core_10 just check; .venv/bin/python -m pytest tests/notification_store/test_senders.py tests/test_run_agent_runner_notifications.py tests/test_notification_catalog.py tests/main/test_notify_handler.py.

## Dependencies

- **Depends on:** [sase-43.1](sase-43.1.md) ✓
- **Blocks:** [sase-43.3](sase-43.3.md) ✓
- **Blocks:** [sase-43.4](sase-43.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`59aea97`](https://github.com/sase-org/sase/commit/59aea97573129b94f251e332d83d5a7b294d2e2b) | feat: add notification tag CLI support (sase-43.2) | [sase-43.2](sase-43.2.md) | 2026-05-24 00:47:37 |
