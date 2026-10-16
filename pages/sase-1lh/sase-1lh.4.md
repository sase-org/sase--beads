# Bead: sase-1lh.4 — Fix the perf-floor flake and the Full CI time budget

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.4` · **Size:** small
**Created:** 2026-10-16 13:00:20 EDT · **Closed:** 2026-10-16 13:13:09 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

ci-budget: recalibrate the Phase 7E perf ceiling that fails about 30% of runs, and check every Full CI job's headroom against its timeout.

## Notes

[2026-10-16T17:12:54Z · sase-1lh.4] PROPOSED FOLLOW-UP: just check docs-gen-check fails identically on clean base (sase tool run cb0428a26c28d2e161575f70a53384d1, exit 1) — docs-epic generated CLI reference drift, owned by gate-fix phase, not ci-budget

[2026-10-16T17:13:09Z · sase-1lh.4] ci-budget done. (1) Recalibrated persistent_query_keystroke override 2.90x->3.10x (ceiling ~206.78us, ~6.1% above hosted max) from 79 Full CI perf-floors runs 2026-10-02..16 (range 77.88-194.93us, median 171.77us; old 193.44us ceiling failed runs 38842775619/38906709061); no other anchor within 2% of ceiling (nearest: parse_query direct 88.2%, scan_facade 85.2%). Evidence tests updated and passing (tests/perf/phase7: 38 passed, 1 skipped). (2) Job budgets over last 20 runs: worst test leg 3.12 coverage 101.2m/120m=84.3%, visual-test 33.0m/45m=73.3% — none over 90%, no timeout changes. Full sase tool run check red only in docs-gen-check, reproduced identically on clean base (pre-existing docs-epic drift, recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.4/README.md) | [sase-1lh.4](sase-1lh.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e69c455`](https://github.com/sase-org/sase/commit/e69c455bd6a65d69727711fcfe9a308e1674c3fc) | perf(ci-budget): recalibrate persistent\_query\_keystroke floor to 3.10x | [sase-1lh.4](sase-1lh.4.md) | 2026-10-16 13:14:27 EDT |
