# Bead: sase-1r2.6 — One Full CI run on master is green in every job

[Bead Pages](../README.md) / [sase-1r2](README.md) / sase-1r2.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.178.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.178.w0.md) · **Assignee:** `sase-1r2.6` · **Size:** medium
**Created:** 2026-11-03 11:09:32 EST
**Plan:** [202611/v0\_19\_0\_green\_full\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202611/v0_19_0_green_full_ci_release.md)

## Description

full-ci: dispatch Full CI on a tip holding every fix, repair what is still red, and repeat until a first attempt is green.

## Notes

[2026-11-07T13:39:04Z · sase-1r2.6--1] Round-1 Full CI verdict (run 42370668331 @ d2aa3ef832): 10/12 required jobs green; test (3.12) red on one node test_trailing_reserve_remeasures_when_flag_already_enabled (known flake, task bead sase-1qd READY, no live owner); visual-test red with 118 golden updates, sampled diff shows the sase-1r2.4 conditional AGENT PROMPT heading removal (expected No-prompt-file panel now renders without the heading). Repair plan: recapture affected goldens, verify, land, redispatch round 2.

[2026-11-07T14:47:40Z · sase-1r2.6--1] PROPOSED FOLLOW-UP: renamed_generic_session_root CI-only scroll drift is the product bug tracked by open task bead sase-1ln (background re-delivery clamps scroll); no fix attempted here.

[2026-11-07T14:47:46Z · sase-1r2.6--1] PROPOSED FOLLOW-UP: stranded_resolve_modal CI-only layout drift (jump badges, doubled border) is a focus/timing flake with no tracking bead; needs determinism hardening.

[2026-11-07T14:47:51Z · sase-1r2.6--1] PROPOSED FOLLOW-UP: artifacts_beads_empty CI-only 389px drift near inbox label needs identification (glyph vs count-dependent text); no tracking bead.

[2026-11-07T15:31:47Z · sase-1r2.6--1] Round-1 repair verified and ready to land: 109 goldens recaptured for the sase-1r2.4 conditional AGENT PROMPT heading removal (51/56 CI actual renders byte-identical to local renders; other 5 are the known CI-only cases below); capacity hostname seam pinned to athena in capacity visual tests (mechanism proven by spoof probe); turns_gate_90x40 hardened with footer-hint wait; 4 residual CI-only flakes triaged (renamed->sase-1ln, stranded modal, beads_empty glyph, trailing_reserve->sase-1qd). just fix clean; sase tool run check run ccc057c5da0ccfe2d76b8b1ce379c370 verdict pass (all lint gates + full suite after core-identity escalation). sase tool run check is the wrapped form; es67j8 follow-up: goldens already landed by this turn submit, skip to targeted check then dispatch Full CI round 2.

[2026-11-07T15:36:28Z · sase-1r2.6--1] Landing accepted: submit committed 109 goldens + capacity pin + gate wait with keep (host finalizes after turn end; new SHA pending). Round-2 dispatch could not be staged: lane blocked by orphan staged monitor es67j8. Next owner (es67j8 follow-up if it adopts, else next turn): poll origin/master for fix(ci): repair Full CI visual-test drift, dispatch full.yml on that tip, watch ~1-6h, judge all required jobs, close done or repair toward round 3.

## Dependencies

- **Depends on:** [sase-1r2.2](sase-1r2.2.md) ✓ · ⧖ 2026-11-03
- **Depends on:** [sase-1r2.3](sase-1r2.3.md) ✓ · ⧖ 2026-11-03
- **Depends on:** [sase-1r2.4](sase-1r2.4.md) ✓ · ⧖ 2026-11-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1r2.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1r2.6.md) | [sase-1r2.6](sase-1r2.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d2aa3ef`](https://github.com/sase-org/sase/commit/d2aa3ef832f8c8b620dbb9856eb016d0d79e0e09) | fix(ci): repair Full CI first-attempt reds at master tip | [sase-1r2.6](sase-1r2.6.md) | 2026-11-07 07:01:02 EST |
| sase | [`48d0c3e`](https://github.com/sase-org/sase/commit/48d0c3ea2d3f193b1538505d565afd681e21c45b) | fix(ci): repair Full CI visual-test drift and pin capacity hostname seam | [sase-1r2.6](sase-1r2.6.md) | 2026-11-07 10:38:01 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3a.cld][1] | Learn which flake/CI task beads the active green-Full-CI epic already fixed or still owns | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:research.3a.grk][3] | Need CI-green phase closeout plus remaining high-impact candidates and install-canary drafts to judge conflict and priority | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.grk/README.md

<!-- sase:referenced-by:end -->
