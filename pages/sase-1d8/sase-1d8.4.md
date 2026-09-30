# Bead: sase-1d8.4 — Prune machine rows from the existing store

[Bead Pages](../README.md) / [sase-1d8](README.md) / sase-1d8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ud](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ud.md) · **Assignee:** `sase-1d8.4` · **Size:** medium
**Created:** 2026-09-30 07:44:52 EDT · **Closed:** 2026-09-30 11:05:06 EDT
**Plan:** [202609/prompt\_history\_human\_only.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_history_human_only.md)

## Description

prune: extend sase-core's looks_generated classifier and expose it to Python; add sase prompt prune --generated/--legacy with preview, backup and typed-wins protection; report origin counts in sase prompt doctor.

## Notes

[2026-09-30T14:41:31Z · sase-1d8.4] PROPOSED FOLLOW-UP: tools/validate_sase_core_rs predict probe expects confident=True ghost=[the] but core returns confident=False ghost=[]; reproduces identically on clean base tree (stashed origin/binding changes, rebuilt base wheel, probe still False/[]); likely validator/model skew from recent prediction calibration

[2026-09-30T14:57:11Z · sase-1d8.4] PROPOSED FOLLOW-UP: tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list fails identically on clean base tree (stashed prune changes, still FAILED); environmental, unrelated to prune phase

[2026-09-30T14:57:40Z · sase-1d8.4] Dry-run on live store (no mutation): total=11631 typed=22 generated=119 missing-origin=11490 heuristic-flagged=8211; prune --generated --legacy --dry-run would remove 8330 (119 explicit + 8211 legacy), keeping 3301. Matches plan expectation (~79 explicit + ~8100 legacy of ~11600).

[2026-09-30T15:05:06Z · sase-1d8.4] Prune phase done across sase-core (looks_generated chop/job markers with tribe-boundary match, doc fix, prompt_looks_generated binding) and sase (prompt_origin adapter, prune --generated/--legacy with typed-wins merge, timestamped .bak backup, tier preview; doctor origin counts; docs). Verified: core 85+6 tests, clippy/fmt clean; sase 659 history/prompt_command + 58 parser/origin + 15 inventory + 313 completion pass; ruff/mypy/symvision/flags/changelog pass. Live dry-run (no mutation): 119 explicit + 8211 legacy of 11631. Two base-identical failures filed as PROPOSED FOLLOW-UP (core validator predict probe; bead-candidates completion test).

## Dependencies

- **Depends on:** [sase-1d8.1](sase-1d8.1.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d8.4/README.md) | [sase-1d8.4](sase-1d8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0ad6e44`](https://github.com/sase-org/sase-core/commit/0ad6e44174c60d8f698bd5861bb10dff4e6bacd0) | feat(prompt-prediction): flag chop and job tribe origins as generated | [sase-1d8.4](sase-1d8.4.md) | 2026-09-30 11:08:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d8.4][1] | Need full description and design details | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d8.4/README.md

<!-- sase:referenced-by:end -->
