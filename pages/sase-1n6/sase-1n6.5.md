# Bead: sase-1n6.5 — Qualify the candidate against the published core

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.5` · **Size:** large
**Created:** 2026-10-19 16:40:08 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

qualify: ci.yml gains ref and core-source inputs, a versioned N1 inventory decides what blocks, and release.yml qualifies against the exact published core with fail-closed evidence.

## Notes

[2026-10-20T04:07:35Z · sase-1n6.5.1.4] PUBLISH INTEGRATION SEAM from release-wiring (sase-1n6.5.1.4): publication (sase-1n6.6) must depend on the qualify job verdict plus exercise, never on the qualify-ci aggregate. qualify exposes verdict/observation/token/run-id/attempt/candidate-id/generation/intended-core-version/tested-core-version outputs; its result is success-with-red-verdict only via the always() final verdict step, so publish needs an explicit status condition such as needs.qualify.outputs.verdict == pass. That condition must pass through required verdicts even when an advisory ancestor failed: default success propagation would silently skip publication after a red advisory job fails qualify-ci. Red qualification observations persist on the draft (release) or as artifacts (rehearse) under candidate-gen<N>-qualification-run<R>-attempt<A>.json.

[2026-10-20T05:35:34Z · sase-1n6.5.1.5.2] Qualification live proofs still outstanding. sase-1n6.5.1.5.2 could not dispatch release.yml rehearse at 400572eab6: reusable ci.yml rejected job-level ${{ runner.temp }} (HTTP 422). A step-level fix is landing with that phase. Pre-existing toobig in tests/test_release_watch_health.py (1253 lines) still fails just lint, so qualify-ci lint will stay red until toobig_split. Publish seam from sase-1n6.5.1.4 is unchanged.

## Dependencies

- **Depends on:** [sase-1n6.2](sase-1n6.2.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.3](sase-1n6.3.md) ✓ · ⧖ 2026-10-19
- **Depends on:** [sase-1n6.4](sase-1n6.4.md) ✓ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.6](sase-1n6.6.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.md) | [sase-1n6.5](sase-1n6.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.1][1] | Need parent-phase notes and inherited qualification decisions | 1 |
| read-by | [agent:sase-1n6.5.1.4][2] | Need epic DECISIONS and land context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.4/README.md

<!-- sase:referenced-by:end -->
