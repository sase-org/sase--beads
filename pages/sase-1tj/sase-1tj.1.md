# Bead: sase-1tj.1 — Resolve research paths at agent run time

[Bead Pages](../README.md) / [sase-1tj](README.md) / sase-1tj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dz.md) · **Assignee:** `sase-1tj.1` · **Size:** small
**Created:** 2026-11-18 11:26:28 EST · **Closed:** 2026-11-18 12:46:23 EST
**Plan:** [202611/research\_commit\_gap.md](https://github.com/sase-org/sase--plans/blob/main/202611/research_commit_gap.md)

## Description

research-macro-paths: make the five research macros resolve the research checkout through an agent-run sase repo open research instead of a launch-time sase repo path substitution; update docs, add a regression test, and note the general launch-time cwd hazard.

## Notes

[2026-11-18T16:58:39Z · sase-1tj.1] PROPOSED FOLLOW-UP: Resolve the general launch-time cwd hazard with the sase-1tc land agent — since efc66a420b, cwd-dependent commands in macro bodies (for example sase repo path, git rev-parse, pwd) run against the runner cwd before workspace claim. Consider entering the known workspace before expansion for non-deferred launches, or delaying authored commands until after claim.

[2026-11-18T17:46:00Z · sase-1tj.1] PROPOSED FOLLOW-UP: Investigate the five existing runner cancellation tests triaged KNOWN by check c8fbf549a33e3fd56ae2869a4674661a (witness 6a06e0823754c1c7dc7499d26219cc77; triage listed no owner): test_clan_cancellation_during_launch_settles_current_and_stops_next, test_cancel_open_units_does_not_erase_launched, test_cancel_after_first_mixed_unit_preserves_launched, test_cancellation_priority_and_reconcile_selection, and test_synchronous_gate_answer_claims_and_releases_runner_slot_capacity_like_an_agent. These are unrelated to the docs-only change; no tracking task bead was identified in the check output.

[2026-11-18T17:46:23Z · sase-1tj.1] Updated all five research macros to resolve the opened research checkout at agent run time, updated #research docs, added raw-source regression coverage, and documented the launch-time cwd hazard. Plugin check passed. Main check lint/docs passed; scoped suite exited 1 with five KNOWN runner-cancellation failures (recorded as proposed follow-up). Epic-symbol check found no leftovers.

## Dependencies

- **Blocks:** [sase-1tj.3](sase-1tj.3.md) ✓ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tj.1/README.md) | [sase-1tj.1](sase-1tj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43ef590`](https://github.com/sase-org/sase/commit/43ef590bb62ec0873fda2a6e7566b2e5b8e0ad66) | docs(macros): clarify command substitution cwd behavior | [sase-1tj.1](sase-1tj.1.md) | 2026-11-18 12:48:05 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tj.1][1] | Check whether earlier phase work left notes or remaining-work guidance | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tj.1/README.md

<!-- sase:referenced-by:end -->
