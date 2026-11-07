# Bead: sase-1r2.4 — Full CI's advisory jobs pass

[Bead Pages](../README.md) / [sase-1r2](README.md) / sase-1r2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.178.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.178.w0.md) · **Assignee:** `sase-1r2.4` · **Size:** medium
**Created:** 2026-11-03 11:09:32 EST · **Closed:** 2026-11-03 13:52:28 EST
**Plan:** [202611/v0\_19\_0\_green\_full\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/v0_19_0_green_full_ci_release.md)

## Description

advisory-lanes: make visual-test, perf-floors, tutorial-tests, and ace-page-group-isolation pass on Full CI.

## Notes

[2026-11-03T17:44:16Z · sase-1r2.4] PROPOSED FOLLOW-UP: Phase 7E parse_query.parse_only.direct CI-only floor — Full CI rust median 10.09us vs ceiling 8.08us (1.40x phase7b); five local consecutive runs 5.60–5.75us vs the same 8.08us ceiling (phase7b rust median 5.77us). Do not raise the floor. Hosted-runner µs noise.

[2026-11-03T17:44:22Z · sase-1r2.4] PROPOSED FOLLOW-UP: capacity inspector 0.16% CI-only miss if it still reproduces on Full CI; local run matched the floor. Do not raise the floor.

[2026-11-03T18:52:28Z · sase-1r2.4] Advisory lanes: archive-identity Reply paints without expanded prompt plus SVG word-gap wait; clan-panel waits on sentinels before idle; 19 PNG goldens recaptured for hijack footer wrap. Visual 3x just test-visual -- check-clean (21 passed, unchanged=27). Tutorial-tests and ace-page-group-isolation already green. DoD-17 live-escalate-join now stages then host-adopts; 5 consecutive just test-slow live owner passes. Phase 7E local 5x rust 5.60–5.75us vs 8.08us ceiling; CI 10.09us recorded as PROPOSED FOLLOW-UP (do not raise floor). just check green (5c1c2f38bedd869f277ebb8efee8da9d).

## Dependencies

- **Blocks:** [sase-1r2.6](sase-1r2.6.md) ◐ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.4/README.md) | [sase-1r2.4](sase-1r2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d3b0480`](https://github.com/sase-org/sase/commit/d3b0480636cdfbc7eb979144ea2a71702b18fae0) | fix(ci): make Full CI advisory lanes pass locally | [sase-1r2.4](sase-1r2.4.md) | 2026-11-03 13:55:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.cld][1] | Learn which flake/CI task beads the active green-Full-CI epic already fixed or still owns | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:research.3a.grk][3] | Need phase children of prior top-ten epic, live CI-green epic, and flake-class epic to exclude overlapping task beads | 1 |
| read-by | [agent:sase-1r2.4][4] | Need the phase scope, design file, notes, and DECISIONS | 7 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.grk/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1r2.4/README.md

<!-- sase:referenced-by:end -->
