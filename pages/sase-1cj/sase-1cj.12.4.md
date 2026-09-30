# Bead: sase-1cj.12.4 — Recalibrate presets and settle the archive default

[Bead Pages](../README.md) / [sase-1cj.12](sase-1cj.12.md) / sase-1cj.12.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1cj.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cj.land.md) · **Assignee:** `sase-1cj.12.4` · **Size:** medium
**Created:** 2026-09-29 18:29:18 EDT · **Closed:** 2026-09-30 13:52:12 EDT
**Plan:** [202609/finish\_prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_prompt_next_word_prediction.md)

## Description

recalibrate: re-run the prequential replay under the corrected support semantics, recalibrate balanced and eager, make cautious measurably stricter than balanced, finish the history-plus-archive comparison and RSS measurement, and record all numbers.

## Notes

[2026-09-30T17:50:31Z · sase-1cj.12.4] PROPOSED FOLLOW-UP: just check lint (symvision) fails identically on the clean base tree — 7 unused-public-symbol hits in untouched files (tool/detach.py escalation_enabled, tool/starter.py StarterResolution, tool/handoff_launch.py HandoffSubmitResult, tool/owner.py owner_ref, core/tool_run.py tool_run_join/tool_run_release_join/tool_run_sync_wait_budget); verified via git stash + just _lint-symvision on base

[2026-09-30T17:50:45Z · sase-1cj.12.4] PROPOSED FOLLOW-UP: prediction RSS budget missed — building history corpus retains ~180MB and pruned archive corpus ~130MB more (VmRSS before/after with gc.collect, corroborated twice; ~3.6x approx_bytes resident) against the <=60MB budget; needs lossy pruning/quantization (product decision) or allocator/layout work, never silent evidence drops

[2026-09-30T17:52:12Z · sase-1cj.12.4] Recalibrated under corrected support semantics (2026-09-30 replay: 11631 rows, 3301 typed, 1971 scored, 142120 pos). Presets now balanced 0.75/0.20/2 (cov 25.9 prec 80.7 novel 65.1), eager 0.40/0.05/1 (59.0/62.9), cautious 0.60/0.40/5 (18.1/85.0/novel 77.6, strictly tighter via support, measurably differs). Recorded in predict.rs doc comments + docs/rust_backend.md. New --score-every K sampling (core+tool, tested) enabled the archive verdict: history,archive K=6 drops novel top-3 40.3->31.2, default stays [history]. RSS measured (~310MB retained vs 60MB budget) filed as follow-up. Verified: sase-core sase tool run check green; 86 Rust prompt_prediction tests; 96+31 sase prediction tests green; validate_sase_core_rs exit 0 (recalibration also resolves the parent-epic probe mismatch notes #2/#3 — 3-row corpus passes balanced support 2); epic-symbols clean; sase just check green except symvision hits proven identical on clean base (filed as follow-up)

## Dependencies

- **Depends on:** [sase-1cj.12.1](sase-1cj.12.1.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.12.2](sase-1cj.12.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.12.3](sase-1cj.12.3.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.12.5](sase-1cj.12.5.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.12.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.4/README.md) | [sase-1cj.12.4](sase-1cj.12.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c3042fd`](https://github.com/sase-org/sase-core/commit/c3042fdded0d32ccd8d19ac1df550da7a869bf40) | feat(prompt-prediction): recalibrate predict thresholds and add replay sampling | [sase-1cj.12.4](sase-1cj.12.4.md) | 2026-09-30 13:55:00 EDT |
| sase | [`782bffa`](https://github.com/sase-org/sase/commit/782bffaf725b913f40acbe113ed12e188351aa77) | feat(prompt-prediction): recalibrate presets, add archive score sampling and replay sources | [sase-1cj.12.4](sase-1cj.12.4.md) | 2026-09-30 14:08:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cj.12.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.12.4/README.md

<!-- sase:referenced-by:end -->
