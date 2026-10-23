# Bead: sase-1nn.3 — Restore Full CI's build-core job and authenticate release metadata sync

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Size:** small
**Created:** 2026-10-23 11:30:06 EDT · **Closed:** 2026-10-23 12:24:14 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

ci-workflows: move build-core's setup-uv step after the sase-core checkouts, give Publish's ratchet step a GitHub token, and pin both with workflow tests.

## Notes

[2026-10-23T16:23:55Z · sase-1nn.3--1] PROPOSED FOLLOW-UP: just check has 4 pre-existing TUI failures that reproduce identically on the clean base tree (verified via git stash): test_gc_policy::test_freeze_happens_once (KNOWN, witness 0565caed0d1ee997557a16ec01dc1ecb), test_gc_policy::test_census_off_by_default, test_app_import_budget::test_tui_app_import_stays_under_startup_budget, test_statistics_perf::test_populated_perf_renderable_covers_every_panel. Unrelated to this phase (only .github/workflows/build-core.yml, publish.yml + workflow tests changed); prior beads (e.g. sase-1nf.10.1.1, sase-1nk.1) already track the import-budget failure.

[2026-10-23T16:24:14Z · sase-1nn.3--1] ci-workflows done: build-core setup-uv moved after sase-core checkouts, Publish ratchet step has GH_TOKEN, workflow tests pin both (18 passed in tests/test_github_actions_build_core.py + tests/test_github_actions_publish.py). Full just check: only 4 TUI failures, all reproduce identically on clean base (stash-verified), 1 KNOWN + 3 pre-existing, recorded as PROPOSED FOLLOW-UP. epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1nn.6](sase-1nn.6.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.3.md) | [sase-1nn.3](sase-1nn.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b2a4c38`](https://github.com/sase-org/sase/commit/b2a4c380cf464ee2bda5c49d24c08812081e2900) | fix(ci): restore Full CI build-core job and authenticate release metadata sync | [sase-1nn.3](sase-1nn.3.md) | 2026-10-23 12:25:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: sase-1nn status | 1 |
| read-by | [agent:sase-1nn.3--1][2] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1nn.6][3] | Need sibling phase close notes and epic status before Full CI triage | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.3.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md

<!-- sase:referenced-by:end -->
