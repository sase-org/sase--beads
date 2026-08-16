# Bead: sase-n4.5.2 — Correct matching, provider attribution, and end-to-end behavior

[Bead Pages](../README.md) / [sase-n4.5](sase-n4.5.md) / sase-n4.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-n4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n4.land.md) · **Assignee:** `sase-n4.5.2` · **Size:** medium
**Created:** 2026-08-16 14:19:51 EDT · **Closed:** 2026-08-16 16:15:42 EDT
**Plan:** [202608/finish\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_usage_limit_auto_disable.md)

## Description

runtime-correctness: consume the atomic store result in usage-limit enforcement, make replace_patterns literal even for an empty list, keep retry attribution pinned to the execution provider recorded for each attempt including fallback attempts, and add a full fakey invocation-to-disable-to-notification acceptance test that proves one attempt, unchanged error propagation, and no collateral provider disable.

## Notes

[2026-08-16T20:14:16Z · sase-n4.5.2] PROPOSED FOLLOW-UP: ratchet sase-core-rs floor to 0.27.15 — just check probe now reports provider_disable_try_set_{relative,until} first appear in published v0.27.15 (n4.5.1 recorded this while still unpublished against 0.27.11)

[2026-08-16T20:14:40Z · sase-n4.5.2] PROPOSED FOLLOW-UP: tests/test_file_panel.py static/live render tests fail with mock.update not called / NoneType subscript — unrelated to usage-limit (also noted on sase-n4.5.1)

[2026-08-16T20:15:07Z · sase-n4.5.2] PROPOSED FOLLOW-UP: tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner and test_load_merged_config_local_overrides_global fail under xdist full-suite (pass in isolation)

[2026-08-16T20:15:42Z · sase-n4.5.2] Consumed try_disable_provider/_until in usage_limit_disable so telemetry, info log, and notify run only on inserted=true. replace_patterns:true plus a present patterns key is a literal replacement including []. Retry detection no longer scans other providers when exec_llm_provider is known and refreshes that identity from agent_meta after fallback. Verified empty-replacement config/detect; 8-way store contention (one disable, one metric, one notification); Codex+quoted Claude weekly-limit still retries; fallback uses recorded exec_llm_provider; unknown provider still scans; fakey e2e (one subprocess, no retry sleep, only fakey source=usage_limit, one notification/metric, sibling preserved, skip reason, original FAKEY-USAGE-LIMIT raised). Transient 429 and Claude/Codex/Grok corpus retained. just install; just check lint passed; scoped run escalated (justfile + core-identity) with 8 unrelated failures recorded as follow-ups.

[2026-08-16T20:17:00Z · sase-n4.5.2] Consumed try_disable_provider/_until so telemetry, info log, and notify run only on inserted=true. replace_patterns:true plus a present patterns key is a literal replacement including []. Retry detection no longer scans other providers when exec_llm_provider is known and refreshes that identity from agent_meta after fallback. Verified empty-replacement config/detect; 8-way store contention (one disable, one metric, one notification); Codex+quoted Claude weekly-limit still retries; fallback uses recorded exec_llm_provider; unknown provider still scans; fakey e2e (one subprocess, no retry sleep, only fakey source=usage_limit, one notification/metric, sibling preserved, skip reason, original FAKEY-USAGE-LIMIT raised). Transient 429 and Claude/Codex/Grok corpus retained. just install; just check lint passed; scoped run escalated (justfile + core-identity) with 8 unrelated failures recorded as follow-ups.

## Dependencies

- **Depends on:** [sase-n4.5.1](sase-n4.5.1.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.5.2/README.md) | [sase-n4.5.2](sase-n4.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eba0eab`](https://github.com/sase-org/sase/commit/eba0eab736081b34b0d35175912d222a74d87701) | fix(llm-provider): pin usage-limit disable and retry to first writer | [sase-n4.5.2](sase-n4.5.2.md) | 2026-08-16 16:18:45 EDT |
