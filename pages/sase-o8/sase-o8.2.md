# Bead: sase-o8.2 — Placeholder context store

[Bead Pages](../README.md) / [sase-o8](README.md) / sase-o8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.2` · **Size:** medium
**Created:** 2026-08-17 06:01:52 EDT · **Closed:** 2026-08-17 06:56:16 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

store: grow the durable common-placeholder store to version 2 with per-entry context bags and corpus statistics, record that evidence on the submit and launch paths, read version 1 stores forward-compatibly, and backfill context once from prompt history.

## Notes

[2026-08-17T10:55:37Z · sase-o8.2] PROPOSED FOLLOW-UP: Flaky test_derived_only_collision_returns_composed_template — full parallel lane left the verdict at "Checking ⇥ todo in …" after pause(0.25); isolation re-run passed. Unrelated to the placeholder store.

[2026-08-17T10:55:53Z · sase-o8.2] PROPOSED FOLLOW-UP: Flaky test_usage_limit_failure_disables_only_fakey_and_preserves_error — TemporaryProviderDisable equality failed on created_at/expires_at at 1e-16 under the full parallel lane; isolation re-run passed. Likely belongs on in-progress epic sase-n4 / sase-n4.5.

[2026-08-17T10:56:16Z · sase-o8.2] Version-2 placeholder store with per-entry context bags and corpus stats. Verified: v1 files load with counts/last_used intact and empty bags; seed upgrades v1 in place and re-merges a racing submit; recording increments prompt_count/context_frequency/context_uses once per prompt and never puts a tag's own <text> in its bag; tag tokens survive stopword/cap filters; trims are deterministic; LRU drops bags but keeps corpus stats; remove leaves corpus stats; unknown/corrupt stores stay empty; common_placeholder_count 0 still disables; failed writes leave the previous file readable. tests/history/test_prompt_placeholders.py 37 passed. just check lint gates green; scoped lane escalated on the Justfile epic-symbol whitelist and the full suite was 31864 passed / 2 unrelated flakes that passed in isolation (noted as PROPOSED FOLLOW-UP).

[2026-08-17T10:57:46Z · sase-o8.2] Version-2 placeholder store with per-entry context bags and corpus stats. Verified: v1 files load with counts/last_used intact and empty bags; seed upgrades v1 in place and re-merges a racing submit; recording increments prompt_count/context_frequency/context_uses once per prompt and never puts a tag's own <text> in its bag; tag tokens survive stopword/cap filters; trims are deterministic; LRU drops bags but keeps corpus stats; remove leaves corpus stats; unknown/corrupt stores stay empty; common_placeholder_count 0 still disables; failed writes leave the previous file readable. tests/history/test_prompt_placeholders.py 37 passed. just check lint gates green; scoped lane escalated on the Justfile epic-symbol whitelist and the full suite was 31864 passed / 2 unrelated flakes that passed in isolation (noted as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-o8.3](sase-o8.3.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.2/README.md) | [sase-o8.2](sase-o8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ded7f1a`](https://github.com/sase-org/sase/commit/ded7f1a5f05e4d2c1554cd75677f874b7eac6b1f) | feat(history): persist placeholder context bags and corpus stats | [sase-o8.2](sase-o8.2.md) | 2026-08-17 06:58:24 EDT |
