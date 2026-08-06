# Bead: sase-gj.6 — Stop charging known flakes to the false-negative metric

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.6` · **Size:** small
**Created:** 2026-08-06 16:03:42 EDT · **Closed:** 2026-08-06 16:30:22 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

flakes: require a full-run failure to be reproducible, or to be absent from a known-flake list, before it is correlated against a scoped selection.

## Notes

[2026-08-06T20:30:22Z · sase-gj.6] Implemented reproducible_flake_nodeids + find_flake_suppressed in tests/_test_selection_health.py: a full-run failure is now treated as a known flake (excluded from false_negatives, reported separately) only when it recurs across >=2 full runs whose change sets share no file, so no single diff explains it. Updated SelectionHealth/summarize, health_payload, and the text/JSON report renderers with a flake_suppressed field, plus docs/development.md. Verified: new correlation+report tests (31) pass; just check (fmt/lint/mypy/pyscripts/changelog/symvision/toobig/SASE validation/committed plans/scoped tests) passes clean; ran just selection-health against the real host store post-fix — false negatives dropped from 9 to 5, with 4 nodes (10 matches) correctly reclassified as flake-suppressed (verified reproducing across full runs with disjoint change sets), remaining 5 are single-full-run matches correctly left as false negatives pending a second occurrence per the design.

## Dependencies

- **Blocks:** [sase-gj.7](sase-gj.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.6/README.md) | [sase-gj.6](sase-gj.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`87961cd`](https://github.com/sase-org/sase/commit/87961cd0e17a2d5a137b327325bb68b28156cc28) | fix(test-selection): stop charging known flakes to the false-negative metric | [sase-gj.6](sase-gj.6.md) | 2026-08-06 16:31:38 EDT |
