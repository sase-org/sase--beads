# Bead: sase-ns.6.2 — Deflake the config-center atomic-save node

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.land.md) · **Assignee:** `sase-ns.6.2` · **Size:** large
**Created:** 2026-08-16 21:02:34 EDT · **Closed:** 2026-08-16 21:42:47 EDT
**Plan:** [202608/task\_backlog\_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)

## Description

config_center_state_flake: task bead sase-md. Make test_save_atomically_replaces_existing_state deterministic under the full parallel lane without weakening its atomic-replace assertion.

## Notes

[2026-08-17T01:42:47Z · sase-ns.6.2] Root cause fixed: the atomic-save tests patched config_center_state.os.replace, which is the shared Python os module and therefore replaced os.replace process-wide on the pytest worker. The save path now calls a module-local _replace_state_file wrapper, and the atomic success/failure tests patch only that local seam while asserting os.replace remains untouched. Verification: .venv/bin/python -m pytest tests/ace/tui/test_config_center_state.py passed 23/23; SASE_CONTENTION_REPEAT=10 SASE_CONTENTION_WORKERS=8 just test-contention -- tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state passed 10/10 repeats with 0 failed nodes; the first just check escalated to the full non-visual suite and the target node passed there (the only test failure was unrelated tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error, which passed immediately in isolation). A rerun of just check is currently blocked before tests by unrelated init memory --check drift; evidence was recorded on task sase-n0 and active epic sase-nb.11. just check-full was not run inline because repo rules require sase_monitor, and sase monitor start failed for this phase identity with: no agent artifacts found for agent 'sase-ns.6.2'.

[2026-08-17T01:43:59Z · sase-ns.6.2] Implemented Config Center atomic save deflake: save path now calls module-local _replace_state_file wrapper, atomic-save tests patch that wrapper and assert process-wide os.replace remains intact, and the obsolete reproducible flake baseline node was removed. Verified just install, focused Config Center state pytest 23/23, and 10-repeat contention run for test_save_atomically_replaces_existing_state. just check escalated to full suite; first run had an unrelated fakey usage-limit flake that passed in isolation, rerun was blocked before tests by unrelated memory generation drift recorded on sase-n0 and sase-nb.11.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.2.md) | [sase-ns.6.2](sase-ns.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9b2984`](https://github.com/sase-org/sase/commit/d9b2984a7b54e5c0788513755a2cf165ea673919) | fix(tui): isolate config center state replacement | [sase-ns.6.2](sase-ns.6.2.md) | 2026-08-16 21:44:57 EDT |
