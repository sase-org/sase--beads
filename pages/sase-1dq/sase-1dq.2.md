# Bead: sase-1dq.2 — Replay calibration, Python wire, bench, and core pin for word completion

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.2` · **Size:** medium
**Created:** 2026-09-30 16:38:22 EDT · **Closed:** 2026-10-01 01:12:23 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

word-completion-calibration: add a mid-word replay mode and calibrate min_prefix_chars per preset. Mirror the new request/result fields in the Python wire and facade, extend the replay tool with --midword and draft-length --bench buckets to choose the synchronous-draft threshold, move the sase-core pin, and record the results in docs/rust_backend.md.

## Notes

[2026-10-01T03:56:45Z · sase-1dq.2--1] bench 2026-10-01 (300 samples, real history): rows_total=11643 rows_used=3273 tokens=237949 contexts=225485 successor_entries=320677; compile_ms=891.4 per_1k_ms=272.3 approx_mb=54.40; sampled=300 blocked=209 confident=33; predict_p50=1.099 p95=1.901 max=2.663; ghost_p50=0.238 p95=0.603 max=0.952; rank_prefix_n=12 p50=0.213 p95=0.317; draft buckets: <=1000 n=87 typing p50=0.225 p95=0.566 / <=4000 n=4 typing p50=0.634 p95=0.917 / <=10000 n=0 / <=20000 n=0; sync_threshold recommendation NEXT_WORD_SYNC_MAX_DRAFT_CHARS=4000 (thin sample above 1000 chars; full log /tmp/sase_1dq2_bench.log). Full --midword replay handed to monitor next.

[2026-10-01T05:11:47Z · sase-1dq.2--4] PROPOSED FOLLOW-UP: just _lint-symvision flags 4 unused public symbols identically on the clean base tree (verified via git stash): HandoffSubmitResult in src/sase/tool/handoff_launch.py, StarterResolution in src/sase/tool/starter.py, fit_next_word_ghost in src/sase/ace/tui/widgets/next_word_completion.py, owner_ref in src/sase/tool/owner.py. None are touched by sase-1dq.2 (additive-only diff); fit_next_word_ghost may belong to a later sase-1dq phase.

[2026-10-01T05:12:23Z · sase-1dq.2--4] Calibrated min_prefix_chars finals 3/2/2 (eager 1->2 in sase-core predict.rs after k=1 failed novel gate 63.2% vs 75.9%); post-edit wheel confirmed via smoke replay (eager k=1 suppressed). Docs: Current-word completion subsection in docs/rust_backend.md with calibration table, bench, NEXT_WORD_SYNC_MAX_DRAFT_CHARS=4000. Verified: sase-core check green, core prompt_prediction 108 passed, facade pytest 18 passed, local check green except 4 symvision symbols proven identical on clean base (recorded as follow-up). Both repos left dirty for host two-repo pin.

[2026-10-01T06:13:24Z · sase-1dq.2--5] PROPOSED FOLLOW-UP: check NEW failure tests/test_config_schema_repositories.py::test_config_schema_documents_intrinsic_agents_sidecar_contract reproduces identically on clean base 8bbee1883b and onto 7ee7252555 (schema says repos/<role>, test expects literal repos/agents; stitch files untouched) — pre-existing, not caused by sase-1dq.2

## Dependencies

- **Depends on:** [sase-1dq.1](sase-1dq.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.6](sase-1dq.6.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.2.md) | [sase-1dq.2](sase-1dq.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d7f802c`](https://github.com/sase-org/sase-core/commit/d7f802c5f4d6e37b97228e16fe17ce7ebe726d6e) | feat(prompt-prediction): mid-word replay metrics and eager min\_prefix\_chars 2 (sase-1dq.2) | [sase-1dq.2](sase-1dq.2.md) | 2026-10-01 01:26:18 EDT |
| sase | [`41b2bc5`](https://github.com/sase-org/sase/commit/41b2bc5035f91b98196b46be0b30781337afb8f4) | feat(prompt-prediction): calibrate current-word completion thresholds, wire, bench, and docs (sase-1dq.2) | [sase-1dq.2](sase-1dq.2.md) | 2026-10-01 02:14:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dq.2--4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.2.md

<!-- sase:referenced-by:end -->
