# Bead: sase-n7.3 — Stop the O(archive) index query

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.3` · **Size:** medium
**Created:** 2026-08-16 11:17:11 EDT · **Closed:** 2026-08-16 11:48:04 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

bounded-query: give reconciliation its own bounded artifact-index query instead of the unbounded full-history `include_hidden` scan of the 115 MB index, leave the `list_monitors` listing path unchanged, and pin the new bounds with a test. Escalate to the Rust core if the predicate is not expressible in the existing wire query.

## Notes

[2026-08-16T15:47:05Z · sase-n7.3] PROPOSED FOLLOW-UP: investigate full-suite flake in config/xprompt tests - first just check full-suite escalation failed tests/test_config.py::test_load_merged_config_invalid_yaml_skipped and tests/ace/tui/test_xprompt_browser_load_keymap.py::test_enter_returns_while_xprompt_file_read_is_blocked; both passed isolated and the second just check passed.

[2026-08-16T15:48:04Z · sase-n7.3] Verified bounded reconciliation query, bounded fallback scan, and unchanged list_monitors listing query; tests/monitor/test_monitor_store_reconcile.py passed; just check passed on rerun; disk-load profile reported 1.068s, 1.176s, 1.224s for 236 agents.

[2026-08-16T15:49:33Z · sase-n7.3] Verified bounded monitor reconciliation query and unchanged listing behavior with pytest tests/monitor/test_monitor_store_reconcile.py, just check on rerun, and disk-load profile around 1.1-1.2s for 236 agents.

## Dependencies

- **Blocks:** [sase-n7.4](sase-n7.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.3/README.md) | [sase-n7.3](sase-n7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9fe8204`](https://github.com/sase-org/sase/commit/9fe82045d1948f20209b9b4d89a32a39fee0a2aa) | perf(monitor): bound reconciliation artifact-index query | [sase-n7.3](sase-n7.3.md) | 2026-08-16 11:51:21 EDT |
