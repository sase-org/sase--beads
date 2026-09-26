# Bead: sase-1aa.1 — Replace shipped-value copies in tests and guard the existing generated alias table

[Bead Pages](../README.md) / [sase-1aa](README.md) / sase-1aa.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1t](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1t.md) · **Assignee:** `sase-1aa.1` · **Size:** medium
**Created:** 2026-09-25 22:26:16 EDT · **Closed:** 2026-09-25 22:49:22 EDT
**Plan:** [202609/model\_catalog\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_catalog_maintenance.md)

## Description

data_driven_tests: derive routing and completion expectations from shipped data, preserve behavioral policy tests, and add a generated-doc drift check to fast verification and CI.

## Notes

[2026-09-26T02:48:40Z · sase-1aa.1] PROPOSED FOLLOW-UP: Fix pre-existing F601 duplicate dict key in tests/test_agent_artifact_marker_path_passing_audit.py:266 which fails whole-repo ruff check and just fix on the clean base tree

[2026-09-26T02:48:58Z · sase-1aa.1] PROPOSED FOLLOW-UP: Triage 83 pre-existing usage-probe/usage-subsystem pytest failures (test_usage_probe, test_muse_usage_probe, test_codex/grok/agy/claude usage probes, adaptive_admission, capability_cache, peek, refresh_runner, etc.) that fail identically on the clean base tree — look environmental (subprocess/deadline-sensitive), unrelated to model-catalog work

[2026-09-26T02:49:22Z · sase-1aa.1] Phase 1 done: render_model_alias_docs --check + fmt-docs-check gate wired into fmt-check/check/check-full/CI (verified exit 1 on alias-target drift with diff, exit 0 when current); alias/routing/completion/priority tests derive expectations from shipped loader+registry (53/53 pass under a @large reorder with zero edits; effort-ladder/Muse-contributor/graph-shape tripwires kept); one-time registry+payload baseline snapshot committed for Phase 2 migration comparison. Focused suites: 250 passed; full tests/llm_provider failure set byte-identical to clean tree (83 pre-existing usage-probe env failures recorded as follow-ups).

## Dependencies

- **Blocks:** [sase-1aa.2](sase-1aa.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aa.1/README.md) | [sase-1aa.1](sase-1aa.1.md) | 0 |
