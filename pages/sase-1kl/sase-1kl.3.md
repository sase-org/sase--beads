# Bead: sase-1kl.3 — Dispatch Full CI on a reliable two-hour clock

[Bead Pages](../README.md) / [sase-1kl](README.md) / sase-1kl.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.106](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.106.md) · **Assignee:** `sase-1kl.3` · **Size:** medium
**Created:** 2026-10-13 14:15:36 EDT · **Closed:** 2026-10-13 14:40:47 EDT
**Plan:** [202610/v0\_18\_0\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_unblock.md)

## Description

full-ci-clock: replace GitHub's dropped `17 */2` cron with a guarded dispatcher that starts Full CI on master when the newest run is at least 2h old and none is in flight.

## Notes

[2026-10-13T18:40:28Z · sase-1kl.3] PROPOSED FOLLOW-UP: bugyi-chops just check still fails 4 toobig_split tests on clean master — `_assert_planned_prompts_use_lumberjack_wait_runners` expects `%queue(runners=3)` which sase 0.17.0 plan_chop_proposals no longer emits; tracked by sase-1gn. ci_watch lint/mypy/92 tests/build passed.

[2026-10-13T18:40:47Z · sase-1kl.3] Implemented the athena cadence_driver: ci_watch now reads vars.heavy_dispatch_every_hours (0/absent = off) like other per-repo release settings and, independently of merge/incidents, applies the dispatch rule to each repo's heavy_workflows on the default branch via a bounded `gh run list --workflow` query (not the shared all-workflow window). Live mode runs `gh workflow run`; dry-run reports would-dispatch. Last dispatch is persisted per repo/workflow with a 15-minute cooldown. Failures are summary+report only and do not flip release eligibility. chezmoi sase_athena.yml sets heavy_dispatch_every_hours: {sase-org/sase: 2} and updates the mutation-allowlist descriptions. Verified: bugyi-chops just lint, just build, and 92 test_ci_watch.py tests (due, not-due, each in-flight status, cooldown, dry-run, disabled, dispatch-failure leaves merge untouched, per-workflow isolation). sase axe job doctor: configured scripts resolve (pre-existing WARN for unconfigured sase_job_tg_inbound). just check still fails 4 toobig_split tests on clean master (sase-1gn). Deployment is phase release.

## Dependencies

- **Blocks:** [sase-1kl.4](sase-1kl.4.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kl.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.3/README.md) | [sase-1kl.3](sase-1kl.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@1316405`](https://github.com/bbugyi200/dotfiles/commit/13164059d5825c4debb8039d96483719302c0d6e) | feat(athena): enable two-hour Full CI dispatch from ci\_watch | [sase-1kl.3](sase-1kl.3.md) | 2026-10-13 14:43:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kl.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.3/README.md

<!-- sase:referenced-by:end -->
