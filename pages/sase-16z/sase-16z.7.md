# Bead: sase-16z.7 — Hot cadence for providers in active use

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.7` · **Size:** medium
**Created:** 2026-09-23 11:06:16 EDT · **Closed:** 2026-09-23 15:45:45 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

hot-cadence: add `llm_provider.usage_metrics.active_refresh_seconds` (default 120), pass the active cadence and warn percent into admission, and write best-effort 15-minute hot hints from the agent launch path and limit events. Update the config schema, defaults, and docs.

## Notes

[2026-09-23T19:45:02Z · sase-16z.7] PROPOSED FOLLOW-UP: just check symvision gate is red on 5 pre-existing unused symbols in files untouched by sase-16z.7 (ClanSummaryDigest, capability_cache_dir, invalidate_probe_capability, mark_all_message, resolve_provider_cli_command); verified present at HEAD with no cross-file src refs, plus test_chop_emits_nothing_due_summary fails on the clean tree (environment real-CLI dependent)

[2026-09-23T19:45:45Z · sase-16z.7] Hot cadence landed and verified: active_refresh_seconds (default 120, min 60, capped at refresh_seconds) in UsageMetricsSettings/config parse, default_config.yml, sase.schema.json, and docs/configuration.md table; _admit_one passes active_cadence_seconds+warn_percent into due and admit; best-effort mark_provider_usage_hot facade (ProviderUsageMarkHotOutcome wire, store/package exports) with 15-min hints from the agent launch path (gated on collection+probe) and limit events; docs hot rules in configuration.md/llms.md. Tests: new tests/llm_provider/test_usage_hot_cadence.py 15 passed; neighbors (config, adaptive-admission, refresh, runner-bindings, schema, hints, eligibility) 98 passed after updating the test admit fake for the new kwargs. just check red only on pre-existing debt: 5 symvision unused symbols verified at HEAD in untouched files plus test_chop_emits_nothing_due_summary failing on the clean tree (recorded as PROPOSED FOLLOW-UP); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-16z.6](sase-16z.6.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.7/README.md) | [sase-16z.7](sase-16z.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1f75302`](https://github.com/sase-org/sase/commit/1f753027252a7ed5332871f8430d86693c30f5e8) | feat(llm-provider): hot cadence for providers in active use | [sase-16z.7](sase-16z.7.md) | 2026-09-23 15:47:27 EDT |
