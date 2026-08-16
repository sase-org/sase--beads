# Bead: sase-n4.1 — Usage-limit detection core

[Bead Pages](../README.md) / [sase-n4](README.md) / sase-n4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03j.md) · **Assignee:** `sase-n4.1` · **Size:** medium
**Created:** 2026-08-16 10:33:43 EDT · **Closed:** 2026-08-16 11:15:54 EDT
**Plan:** [202608/llm\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/llm_usage_limit_auto_disable.md)

## Description

detect: add the `llm_provider.usage_limit` config section, its JSON schema, the `llm_default_usage_limit_config` plugin hook, evidence-based built-in patterns for every shipped provider, and the normalize/match/exclude plus reset-hint parsing logic, with a regression corpus of real captured provider messages.

## Notes

[2026-08-16T15:15:19Z · sase-n4.1] PROPOSED FOLLOW-UP: `just check`'s scoped test lane shows non-deterministic failures unrelated to this phase — different tests fail across repeated runs (tests/test_config_cache.py::test_first_config_token_read_does_not_start_worker, tests/test_config.py::test_legacy_overlay_is_discovered_but_not_a_complete_owner, and the tests/ace/tui/widgets/test_vim_normal_key_containment.py::* family all pass in isolation but fail intermittently under the full parallel run). Separately, tests/test_query_profile.py::test_provider_query_schema_derives_fields_from_the_notes_fixture fails deterministically even on a clean master checkout (extra `family`/`related` fields returned beyond the expected `{title, status}`) — a real pre-existing regression, not flakiness. Investigate the shared global state causing the parallel-run flakiness and fix the query-profile fixture-vs-assertion drift.

[2026-08-16T15:15:54Z · sase-n4.1] Added src/sase/llm_provider/usage_limit_config.py implementing ProviderUsageLimitConfig/UsageLimitSettings/UsageLimitDetection, config merge (additive patterns/exclude_patterns with replace_patterns escape hatch, key-presence scalar overrides), normalize_for_match (NFKC + apostrophe-variant + whitespace normalization, order-fixed so U+00B4 doesn't escape translation via NFKC decomposition), find_matching_pattern/is_usage_limit_error, parse_reset_hint (zoned/local-clock/duration forms, 60s grace, no cross-form fallthrough on a failed zone lookup), and detect_usage_limit tying it together with reset-hint-only min/max clamping. Added the llm_default_usage_limit_config pluggy hookspec and evidence-based built-ins for all 8 providers (claude, codex, grok verified from captured failures/binaries; qwen/agy transport-level; muse/opencode conservative unverified baseline; fakey deterministic trigger). Added llm_provider.usage_limit to sase.schema.json and default_usage_limit_config to provider registry metadata. Added tests/test_llm_provider_usage_limit_config.py and tests/test_llm_provider_usage_limit_defaults.py (61 tests) covering the regression corpus from the plan (Claude weekly-limit + reset hint, Grok curly-apostrophe capture, Codex Upgrade-to-Pro) plus Claude's negative advisory/grace-window/fast-limit/close-to-limit cases. Verified: just lint clean (ruff/mypy/symvision — added --epic-symbol sase-n4(...) whitelist entries in Justfile for the 9 symbols only enforce/notify/surface will consume); all 1136 llm_provider+config-related tests pass serially; just check's scoped test lane showed only pre-existing unrelated flakiness (confirmed via clean-master baseline and repeat runs, logged as a follow-up note).

[2026-08-16T15:17:03Z · sase-n4.1] Verified: 61 new tests pass (test_llm_provider_usage_limit_config.py, test_llm_provider_usage_limit_defaults.py); just lint clean with --epic-symbol whitelist entries added; just check scoped suite confirmed pre-existing flakiness unrelated to this change via clean-master baseline comparison.

## Dependencies

- **Blocks:** [sase-n4.2](sase-n4.2.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.1/README.md) | [sase-n4.1](sase-n4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3201e7f`](https://github.com/sase-org/sase/commit/3201e7fdb793e9eb0043e08c2c61629eafbfc656) | feat(llm-provider): add usage-limit detection core | [sase-n4.1](sase-n4.1.md) | 2026-08-16 11:18:09 EDT |
