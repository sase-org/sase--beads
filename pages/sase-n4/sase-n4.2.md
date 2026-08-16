# Bead: sase-n4.2 — Runtime disable and retry precedence

[Bead Pages](../README.md) / [sase-n4](README.md) / sase-n4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03j.md) · **Assignee:** `sase-n4.2` · **Size:** medium
**Created:** 2026-08-16 10:34:06 EDT · **Closed:** 2026-08-16 12:23:43 EDT
**Plan:** [202608/llm\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/llm_usage_limit_auto_disable.md)

## Description

enforce: call detection from the LLM invocation error paths, write the temporary provider disable through the existing Rust-backed store with a structured source, make a usage-limit failure take precedence over the retry loop so agents stop sleeping through futile waits, and record telemetry.

## Notes

[2026-08-16T16:23:00Z · sase-n4.2] PROPOSED FOLLOW-UP: `just check` scoped-test escalation (triggered by the Justfile broadening rule) is flaky under full-suite parallel load — three consecutive full runs each failed on a different, unrelated timing-sensitive test (tests/test_config_cache.py::test_current_config_token_refresh_is_single_flight, test_clear_config_cache_resets_config_token_time_gate, test_explicit_invalidation_wins_race_with_background_refresh, test_yaml_content_cache_survives_config_cache_clear, test_load_merged_config_caches_default_layer; tests/ace/tui/test_config_center_state.py::test_save_atomically_replaces_existing_state). All pass cleanly in isolation and are unrelated to sase-n4.2 (llm_provider/axe retry/telemetry) files. Worth investigating whether these single-flight/atomic-replace tests need higher timing tolerance under CPU contention.

[2026-08-16T16:23:43Z · sase-n4.2] Implemented handle_possible_usage_limit (src/sase/llm_provider/usage_limit_disable.py) wired into both _invoke.py error paths (CalledProcessError and LLMInvocationError), writing disable_provider/disable_provider_until with source=usage_limit, guarded against double-write via get_active_provider_disable, and incrementing LLM_PROVIDER_AUTO_DISABLES. Added retry precedence in run_agent_exec_retry.py: a usage-limit match skips the wait-and-retry branch, allows fallback only to a different non-disabled provider, and records the skip reason on the attempt snapshot (plumbed through AttemptRecord/_AttemptMeta and rendered in the ACE agent list + prompt panel). Verified: targeted suite (tests/test_llm_provider_usage_limit_disable.py, test_llm_provider_usage_limit_config.py, test_axe_run_agent_exec_retry.py, test_llm_provider_invoke.py) — 88/88 pass, including codex-usage-limit-skips-retry and transient-429-still-retries regression cases. Fixed a stale METRIC_DEFS count assertion (27->28) in tests/telemetry/test_metrics.py for the new counter. just check: all lint gates green (fmt, ruff, mypy, pyscripts, symvision, toobig, SASE validation, committed plans); the scoped-test lane escalated to the full suite (Justfile broadening rule) and passed my diff's tests every run, with only pre-existing unrelated flaky timing tests failing intermittently (filed as a PROPOSED FOLLOW-UP note, confirmed via isolated re-runs that all pass).

## Dependencies

- **Depends on:** [sase-n4.1](sase-n4.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n4.3](sase-n4.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n4.4](sase-n4.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.2/README.md) | [sase-n4.2](sase-n4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9ef675`](https://github.com/sase-org/sase/commit/c9ef675105258e853f80629628c6826f9ad33fe2) | feat(llm-provider): auto-disable providers on usage-limit errors | [sase-n4.2](sase-n4.2.md) | 2026-08-16 12:24:54 EDT |
