# Bead: sase-n4.3 — Rich usage-limit notification

[Bead Pages](../README.md) / [sase-n4](README.md) / sase-n4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03j.md) · **Assignee:** `sase-n4.3` · **Size:** small
**Created:** 2026-08-16 10:34:26 EDT · **Closed:** 2026-08-16 13:05:38 EDT
**Plan:** [202608/llm\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/llm_usage_limit_auto_disable.md)

## Description

notify: add a notification sender that reports which provider was disabled, for how long and until when, what the provider actually said, and which agent tripped it, with once-per-disable-window dedup.

## Notes

[2026-08-16T17:00:54Z · sase-n4.3] PROPOSED FOLLOW-UP: Wire a real notification action for llm.usage_limit — the notify_provider_usage_limit_disabled notification (src/sase/notifications/senders.py) currently ships with no action per the phase plans explicit fallback, since wiring a new "JumpToModelsPanel"-style action through the NotificationModal dispatcher (src/sase/ace/tui/actions/agents/_notification_modal_flow.py) and a handler module was judged out of scope for this small phase; a future phase (likely alongside surface, sase-n4.4) should add that action.

[2026-08-16T17:04:02Z · sase-n4.3] PROPOSED FOLLOW-UP: tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs fails on master (unrelated to this bead) — it asserts AGENT_ARTIFACT_INDEX_SCHEMA_VERSION == "21" but the constant is now 22, so the schema-version upgrade assertion fails; confirmed via git stash that this predates this phases changes.

[2026-08-16T17:05:38Z · sase-n4.3] Added notify_provider_usage_limit_disabled() in src/sase/notifications/senders.py, composing provider display name, disable duration, re-enable time (with reset-hint provenance), triggering agent/model when available, the raw provider message, and a routing note. Wired the call into usage_limit_disable.py so it fires exactly once per disable window (only on an actual new write, never on an already-active skip), gated by the resolved notify setting, and isolated in its own try/except so a notification failure never masks a successful detection/disable-write. Added best-effort agent-name resolution from agent_meta.json. Removed the now-stale sase-n4(get_usage_limit_settings) symvision epic whitelist entry since it has a real caller now. Verified: just check (fmt/lint/mypy/symvision all green; scoped test selection escalated to the full suite — 31161 passed, 11 skipped; the 3 failures are pre-existing and unrelated, confirmed via git stash — schema-version drift in test_var_integration.py and two monitor_supervise timing tests that pass in isolation). Shipped the notification without an action per the phase's explicit fallback guidance (wiring a new NotificationModal dispatcher action was out of scope for this phase); logged as a PROPOSED FOLLOW-UP along with the pre-existing test_var_integration.py failure.

[2026-08-16T17:07:41Z · sase-n4.3] Added notify_provider_usage_limit_disabled() sender wired into usage_limit_disable.py enforce path (fires once per new disable window, gated by resolved notify setting, isolated try/except). Added test coverage in test_senders.py and test_llm_provider_usage_limit_disable.py. Removed stale get_usage_limit_settings symvision epic-whitelist entry from Justfile. Verified via just check: all lint/fmt/mypy/symvision gates green; full suite escalation 31161 passed, 3 pre-existing unrelated failures confirmed via git stash (schema-version drift in test_var_integration.py, 2 flaky monitor_supervise timing tests).

## Dependencies

- **Depends on:** [sase-n4.2](sase-n4.2.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.3/README.md) | [sase-n4.3](sase-n4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1fbc8c0`](https://github.com/sase-org/sase/commit/1fbc8c0f193338b0ac4fb63a435694f8f81cb403) | feat(llm-provider): notify on usage-limit auto-disable | [sase-n4.3](sase-n4.3.md) | 2026-08-16 13:13:37 EDT |
