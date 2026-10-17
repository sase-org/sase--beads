# Bead: sase-1m3.4.1.4 — Aggregate Output and lifetime statistics and expose the binding

[Bead Pages](../README.md) / [sase-1m3.4.1](sase-1m3.4.1.md) / sase-1m3.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.4.md) · **Assignee:** `sase-1m3.4.1.4` · **Size:** medium
**Created:** 2026-10-16 22:16:03 EDT · **Closed:** 2026-10-17 01:34:32 EDT
**Plan:** [202610/project\_stats\_core\_engine.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_core_engine.md)

## Description

query-binding: implement footer attribution, deduplicated project and portfolio aggregates, coverage and fingerprints, query dispatch, the project_stats_query binding, and measured cold and warm history acceptance.

## Notes

[2026-10-17T05:29:52Z · sase-1m3.4.1.4] PROPOSED FOLLOW-UP: Core check remains blocked by the clean-base Clippy 1.95.0 clippy::nonminimal_bool deny in crates/sase_core/src/project_onboarding/classify.rs:500-502 (tracked by sase-1an); classify.rs is outside this phase and git blame shows it unchanged on HEAD 855ed4c3.

[2026-10-17T05:34:32Z · sase-1m3.4.1.4] Implemented footer-first attribution, unique walks by (identity, common_dir, tip), project/portfolio SHA-union Output and lifetime, coverage, fingerprints that ignore cache_dir, query dispatch, and the project_stats_query PyO3 binding. Domain tests 42 passed (1 ignored); sase_core_py project_stats 3 passed. Measured sase-core checkout: history_commits=1568 range_commits=395 tip=855ed4c3788f6564c9a00a8838ae005aed882bcc budget_ms=30000 max_bytes=33554432 cold_ms=237.7 warm_median_ms=93.2 includes_extension_startup=false; cold/warm fingerprints matched. just fmt clean. sase tool run check failed only on the clean-base Clippy 1.95.0 nonminimal_bool deny in project_onboarding/classify.rs:500-502 (sase-1an); this phase's aggregate.rs manual_range_contains was fixed. epic-symbols: none leftover. Code/Runs/plans stay unimplemented.

## Dependencies

- **Depends on:** [sase-1m3.4.1.3](sase-1m3.4.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.4.1.4/README.md) | [sase-1m3.4.1.4](sase-1m3.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@be2bfbe`](https://github.com/sase-org/sase-core/commit/be2bfbee126354e387e093bbbdb37c9b2ad35114) | feat(project-stats): aggregate Output and expose project\_stats\_query | [sase-1m3.4.1.4](sase-1m3.4.1.4.md) | 2026-10-17 01:38:02 EDT |
