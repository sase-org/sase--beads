# Bead: sase-nb.9 — The first two real flags

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.9` · **Size:** medium
**Created:** 2026-08-16 12:26:24 EDT · **Closed:** 2026-08-16 19:50:29 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

consumer: convert one opt-in beta env gate and one disable_* env gate into registered flags with real flag beads, and record why plugin discovery cannot be the first consumer.

## Notes

[2026-08-16T23:38:38Z · sase-nb.9] WHY NOT plugins_enabled: discover_plugin_resources("sase_config") feeds the plugin:* config layers, so a flag resolved from config cannot gate plugin discovery without a bootstrap cycle (config needs plugins, plugins would need the flag, the flag needs config). If plugins_enabled is ever wanted, it needs an explicit bootstrap scope resolved from the registry default and SASE_FEATURE_FLAGS only — a later decision, not a v1 consumer.

[2026-08-16T23:39:03Z · sase-nb.9] PROPOSED FOLLOW-UP: sase flag new printed the pre-collision id — `sase flag new coder_inherits_planner_chat` reported Created flag bead: sase-nv, but sase-nv is a pre-existing task bead and the flag bead that was actually committed is sase-nw. The returned Issue.id is the pre-commit allocation; a remint on collision is not reflected in the scaffold. Registry was corrected to sase-nw by hand.

[2026-08-16T23:40:08Z · sase-nb.9] PROPOSED FOLLOW-UP: just check is red on master HEAD before this phase — tools/check_test_wait_helpers fails tests/test_config_cache.py:622,666 and tests/test_config_cache_isolation.py:127 (fixed-sleep-missing-pragma). Confirmed with my consumer diff stashed. Also, sase-nb.7 left a stray HistoryWordCompletionMetadata = _HistoryWordCompletionMetadata alias (NameError/F811); deleted that one line so ruff could run.

[2026-08-16T23:49:50Z · sase-nb.9] PROPOSED FOLLOW-UP: escalated full suite has two unrelated reds — tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_agy_captured_failure_disables_small_pool_member (StopIteration) and tests/ace/tui/widgets/test_agent_list_monitor_rows.py::test_family_container_badge_does_not_alter_status_chip (format_agent_option unexpected parallel_family_counts). Both fail in isolation on this tree; not caused by the consumer flags.

[2026-08-16T23:50:29Z · sase-nb.9] Registered coder_inherits_planner_chat (beta, default false, bead sase-nw) and prettier_enabled (sunset, default true, bead sase-nx). Call sites use current_flags().enabled(FeatureFlag.*); SASE_DISABLE_PRETTIER still maps into the snapshot with a deprecated_env diagnostic on sase flag list and flags.overrides. Verified both states, schema regen, tools/check_feature_flags (static+bead), sase flag list/show with live 90d·v0.18.0 countdowns, and 81 focused tests. just check: fmt/ruff/mypy/flags/symvision/validate green; test-waits already red on HEAD; scoped run escalated on schema and passed after fixing test_static_main_ignores_exploding_bd_command. Recorded why plugins_enabled cannot be a v1 consumer.

[2026-08-16T23:53:14Z · sase-nb.9] Registered coder_inherits_planner_chat (beta, default false, bead sase-nw) and prettier_enabled (sunset, default true, bead sase-nx). Call sites use current_flags().enabled(FeatureFlag.*); SASE_DISABLE_PRETTIER still maps into the snapshot with a deprecated_env diagnostic. Verified sase flag list/show with live 90d·v0.18.0 countdowns and call sites, SASE_DISABLE_PRETTIER=1 maps prettier_enabled off with deprecation warning, and 103 focused tests passed.

## Dependencies

- **Blocks:** [sase-nb.10](sase-nb.10.md) ◐ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.5](sase-nb.5.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.6](sase-nb.6.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-nb.7](sase-nb.7.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.9/README.md) | [sase-nb.9](sase-nb.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b458f1`](https://github.com/sase-org/sase/commit/5b458f1bb9b31515c85957bc436dad8252195669) | feat(flags): register the first two consumer feature flags | [sase-nb.9](sase-nb.9.md) | 2026-08-16 19:58:13 EDT |
