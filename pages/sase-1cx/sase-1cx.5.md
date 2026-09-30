# Bead: sase-1cx.5 — sase monitor start -J/--join and the joiner worker

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.5` · **Size:** large
**Created:** 2026-09-29 20:32:19 EDT · **Closed:** 2026-09-30 13:48:05 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

monitor-join: add `-J/--join RUN` to `sase monitor start`. It records the join atomically before the proc starts and releases it if the start fails. A hidden `sase tool _join` worker streams the run into the monitor log and mirrors its exit. Monitor stop and timeout, `sase tool stop`, and settlement all route through the join. `-f` is refused with `--join` in v1.

## Notes

[2026-09-30T17:47:22Z · sase-1cx.5] PROPOSED FOLLOW-UP: allow -f/--completion with -J/--join. Needs (1) stage-diagnostics mirroring for the joined run's settlement summary so the prepared-completion binding can evaluate the follow-up, and (2) a join-time workspace fingerprint guard so the frozen verification command still matches the run that was joined. v1 refuses the combination with exit 2 pointing at -n/--next.

[2026-09-30T17:47:40Z · sase-1cx.5] PROPOSED FOLLOW-UP: just check is red on the clean base for reasons outside this phase. (1) tools/validate_sase_core_rs prompt-prediction probe expects confident=True but the installed wheel returns confident=False, failing _setup before any gate runs (reproduced exit 1 with this phase's work stashed). (2) symvision flags three pre-existing unused-public symbols untouched by this phase: HandoffSubmitResult, StarterResolution, owner_ref. (3) The test-selection baseline is 3709 commits stale so check escalates to the full suite (est. ~50 min), beyond a single-turn inline run.

[2026-09-30T17:48:05Z · sase-1cx.5] Implemented monitor joins per 202609/monitor_join.md. Verified: tests/monitor/test_monitor_join.py (23 tests: all -J refusals/exit codes, flag-off, label/reason/command derivation, join-before-submit + release-on-failure, settle race teardown, replay, both tool-stop routings, both settlement paths), tests/tool/test_join.py (9 tests: worker replay/output/codes, pre-join streaming, stop/timeout reasons, mapped codes), full tests/monitor + tests/tool detach/bounded-wait/handoff + parser/completion suites green, hermetic smoke harness green incl. new dod-17-detach-join, ruff/mypy/keep-sorted/pyscripts/waits/changelog/terminology/flags/model-policy/docs/committed-plans/prettier/sase-validate green, symvision clean for all new symbols. just check cannot pass here: _setup validator probe + 3 symvision items fail identically on the clean base (recorded as follow-ups).

## Dependencies

- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.4](sase-1cx.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.7](sase-1cx.7.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.5.md) | [sase-1cx.5](sase-1cx.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e032ec4`](https://github.com/sase-org/sase/commit/e032ec4d4ac33578f25caf8005140393fab0261e) | feat(tool): join detached ToolRuns with monitors (sase-1cx.5) | [sase-1cx.5](sase-1cx.5.md) | 2026-09-30 14:11:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cx.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.land/README.md

<!-- sase:referenced-by:end -->
