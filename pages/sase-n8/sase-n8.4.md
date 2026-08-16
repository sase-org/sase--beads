# Bead: sase-n8.4 — The per-alias history limit config field

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.4` · **Size:** small
**Created:** 2026-08-16 11:31:56 EDT · **Closed:** 2026-08-16 12:10:47 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

config: add `llm_provider.model_alias_history_limit` (default 10, minimum 1) to the JSON schema, the shipped default config commentary, and a validated accessor, and document it in the configuration and LLM references.

## Notes

[2026-08-16T16:01:04Z · sase-n8.4] PROPOSED FOLLOW-UP: config-init doctor test flakes under full-suite xdist — just check escalated to the full suite and failed once in tests/doctor/test_checks_config_init.py::test_config_init_doctor_reports_missing_then_current_owner_identity; the same test passes in isolation and is unrelated to llm_provider.model_alias_history_limit.

[2026-08-16T16:09:54Z · sase-n8.4] PROPOSED FOLLOW-UP: logs pane scroll test flakes under full-suite xdist — a second just check full-suite escalation failed once in tests/ace/tui/test_logs_pane.py::test_logs_tab_g_and_shift_g_scroll_detail_extremes; the same test passes in isolation and is unrelated to llm_provider.model_alias_history_limit.

[2026-08-16T16:10:47Z · sase-n8.4] Verified llm_provider.model_alias_history_limit config/schema/docs/accessor changes with targeted pytest tests/test_llm_provider_default_effort.py tests/test_config_schema_models.py (46 passed), direct public import/default check, git diff --check, and just check lint/validation gates through committed plans. just check escalated to the full suite because src/default_config.yml changed; two reruns each failed on a different unrelated xdist-only test that passed in isolation, recorded as PROPOSED FOLLOW-UP notes.

[2026-08-16T16:12:04Z · sase-n8.4] Implemented llm_provider.model_alias_history_limit default 10/minimum 1 across accessor, schema, default config, docs, and tests. Verified just install; focused pytest files passed; direct import/default check returned 10 10; git diff --check passed; just check lint/validation gates passed, but two full-suite xdist-only failures reproduced as unrelated because each failing test passed in isolation and both were recorded as proposed follow-ups.

## Dependencies

- **Blocks:** [sase-n8.5](sase-n8.5.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.4/README.md) | [sase-n8.4](sase-n8.4.md) | 0 |
