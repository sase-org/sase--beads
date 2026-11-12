# Bead: sase-1se.3 — Healer relaunches launcher rows that died before naming

[Bead Pages](../README.md) / [sase-1se](README.md) / sase-1se.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bq.md) · **Assignee:** `sase-1se.3` · **Size:** medium
**Created:** 2026-11-12 06:15:58 EST · **Closed:** 2026-11-12 08:30:39 EST
**Plan:** [202611/auto\_restart\_update\_skew\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/auto_restart_update_skew_fixes.md)

## Description

launcher-relaunch: the healer detects failed rows whose runner died before assigning a name (ace-run bootstrap deaths), and relaunches them by resubmitting the row's raw_prompt.md through the existing launch machinery instead of deferring forever on `plan_agent_restart` name lookup.

## Notes

[2026-11-12T13:29:20Z · sase-1se.3] PROPOSED FOLLOW-UP: Investigate flaky tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_done_row_dismissed_without_signal_and_stays_hidden — failed in the full check at disk_rows(full_history=True), then passed unchanged in isolated ToolRun 08449bb057071dbd1e4a8e664506642d; full check ToolRun 3ef55fe2698bda9fc9d5baea5015ebaf.

[2026-11-12T13:30:39Z · sase-1se.3] Implemented raw_prompt.md resubmission for unnamed launcher rows through the normal project launch path, preserving the failed artifacts/workspace hold and carrying ledger, evidence, provenance, notification, and replacement-directory state. Formatting, Ruff, and mypy passed. Guarded just check ran the full suite: 60,871 passed, 17 skipped, 2 failed; one failure was KNOWN, and the unrelated Agents-tab failure passed its isolated unchanged rerun and is recorded as a proposed follow-up. Core-floor probe remains blocked_unpublished for 8 linked sase-core capabilities at pinned 0.44.2; phase sase-1se.4 owns the pin ratchet. No epic-symbol entries remained.

## Dependencies

- **Depends on:** [sase-1se.2](sase-1se.2.md) ✓ · ⧖ 2026-11-12
- **Blocks:** [sase-1se.4](sase-1se.4.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1se.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.3/README.md) | [sase-1se.3](sase-1se.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7665654`](https://github.com/sase-org/sase/commit/7665654aaaa8987a92f485991bb3b30af7c4717e) | fix(agent\_auto\_restart): resubmit unnamed launcher prompts | [sase-1se.3](sase-1se.3.md) | 2026-11-12 08:33:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1se.3][1] | Need prior phase notes and remaining work before continuing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1se.3/README.md

<!-- sase:referenced-by:end -->
