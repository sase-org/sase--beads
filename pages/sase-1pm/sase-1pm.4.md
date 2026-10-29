# Bead: sase-1pm.4 — Stop the TUI import-budget guard from re-breaking weekly (sase-1ic)

[Bead Pages](../README.md) / [sase-1pm](README.md) / sase-1pm.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15r.md) · **Assignee:** `sase-1pm.4` · **Size:** medium
**Created:** 2026-10-29 01:44:36 EDT · **Closed:** 2026-10-29 02:04:20 EDT
**Plan:** [202610/task\_backlog\_epic\_1.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_1.md)

## Description

import-budget: change what the module-count guard measures per the import_budget decision, align tools/tui_import_closure and the perf runbook, and keep the deferred probe intact.

## Notes

[2026-10-29T06:02:49Z · sase-1pm.4] TASK RESOLVED: sase-1ic — Guard now counts first-party modules (sase and sase.*) after import sase.ace.tui.app. Measured 2839 on 2026-10-29; cap is 2844 (measured plus 5, strict <). Loose total bound is 3904 (measured 3549 plus 10%). tools/tui_import_closure bare form and --diff report first-party counts. Deferred-module probe and CPU budget unchanged. tests/ace/tui/test_app_import_budget.py plus tests/test_tui_import_closure.py: 10 passed, including synthetic eager sase.* failure and third-party growth ignored.

[2026-10-29T06:04:20Z · sase-1pm.4] First-party import-budget guard: measured 2839 sase.* modules vs cap 2844 (measured plus 5, strict <); loose total cap 3904 (3549 plus 10%). tools/tui_import_closure reports first-party counts on bare and --diff. Deferred-module probe and CPU budget unchanged. tests/ace/tui/test_app_import_budget.py and tests/test_tui_import_closure.py: 10 passed, including synthetic eager sase.* failure and third-party growth ignored. No --epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pm.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.4.md) | [sase-1pm.4](sase-1pm.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2456160`](https://github.com/sase-org/sase/commit/24561602cc26a699f7994496006e7fefa4fbf176) | fix(tui): ratchet first-party TUI import budget instead of total modules | [sase-1pm.4](sase-1pm.4.md) | 2026-10-29 02:51:48 EDT |
