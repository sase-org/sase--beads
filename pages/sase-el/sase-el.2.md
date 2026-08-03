# Bead: sase-el.2 — Pane load path, config, and session state

[Bead Pages](../README.md) / [sase-el](README.md) / sase-el.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sk/README.md) · **Assignee:** `sase-el.2` · **Size:** small
**Created:** 2026-08-03 06:53:07 EDT · **Closed:** 2026-08-03 08:04:56 EDT
**Plan:** [202608/agent\_cli\_update\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_cli_update_history.md)

## Description

plumbing: read a bounded tail of the journal inside the existing off-thread Updates load worker, carry it on PluginsLoadResult into pane state, add the two ace.updates config keys and the session-scoped history-scope flag, and mount the history Static with its TCSS so the render phase has a surface to paint into.

## Notes

[2026-08-03T12:04:36Z · sase-el.2] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is flaky under `just check`/`just test` full-suite load (fails consistently when many sibling sase agent workspaces run pytest concurrently, e.g. contended lock-timeout assertions get thrown off by system load) but passes reliably in isolation (`just test tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout`). Not caused by this phase's change (agent-CLI history plumbing touches unrelated files). Consider raising its lock-timeout margin or marking it to skip/retry under heavy parallel CI load.

[2026-08-03T12:04:56Z · sase-el.2] Implemented the plumbing phase: PluginsLoadResult gained agent_cli_history/agent_cli_history_error, read via a best-effort try/except in load_plugins_catalog_for_pane (limit=200), routed through a deferred pane_module._read_agent_cli_update_runs alias (mirrors the _execute_agent_cli_updates convention) so it can be stubbed/disabled independently. Added ace.updates.agent_cli_history / agent_cli_history_max_rows to default_config.yml + sase.schema.json, loaded via a new AgentCliHistoryConfig/load_agent_cli_history_config in plugins_browser_agent_clis.py (coercing bad values to defaults, mirroring IncomingCommitsConfig). Added UpdatesSessionState.agent_cli_history_all session flag. Pane __init__/on_worker_state_changed adopt the new fields via getattr like agent_cli_statuses; compose() mounts an empty '#agent-clis-history' Static after '#agent-clis-detail'; styles.tcss has its rule. Verified: just lint (ruff, mypy, symvision, toobig) clean; new/extended tests in tests/ace/tui/test_plugins_browser_pane_agent_clis.py (history populates pane state, defaults when a stubbed loader omits the fields, read failure sets agent_cli_history_error while preserving agent_cli_statuses, disabled config skips the journal read entirely, config coercion for bad enabled/max_rows values) all pass; full 'just test' passes except one pre-existing flaky lock-contention test unrelated to this change (noted as PROPOSED FOLLOW-UP, confirmed passing in isolation).

## Dependencies

- **Depends on:** [sase-el.1](sase-el.1.md) ✓
- **Blocks:** [sase-el.3](sase-el.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-el.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-el.2/README.md) | [sase-el.2](sase-el.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4ad939`](https://github.com/sase-org/sase/commit/e4ad939168acf54a963c5a404a39cbd059ef969e) | feat(agent-clis): wire update history into pane load, config, and session state | [sase-el.2](sase-el.2.md) | 2026-08-03 08:06:12 EDT |
