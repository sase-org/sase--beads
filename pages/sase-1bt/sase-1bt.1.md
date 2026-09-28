# Bead: sase-1bt.1 — Live glance, node summaries, brief lists, and the verdict bucket in sase-core

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.1` · **Size:** medium
**Created:** 2026-09-27 18:32:34 EDT · **Closed:** 2026-09-27 19:22:03 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

core-glance: add the fingerprint-free tool_run_live_glance, tool_run_briefs and tool_run_node_summaries projections, one shared verdict-bucket helper, the silent threshold constant, and agent/owner indexes, with PyO3 bindings and round-trip tests.

## Notes

[2026-09-27T23:21:36Z · sase-1bt.1] PROPOSED FOLLOW-UP: sase-core gate red on base tree — clippy 1.98 lints in untouched launch_scratch_liveness.rs:300 (too_many_arguments) and :477 (manual_repeat_n) fail just check with -D warnings; fix there or pin toolchain

[2026-09-27T23:21:48Z · sase-1bt.1] PROPOSED FOLLOW-UP: move triage_show and receipt load_triage_facts verdict request-building onto projection verdict_summary_for_runs shared helper after proving outputs identical (left as copies per plan C0)

[2026-09-27T23:22:03Z · sase-1bt.1] core-glance done in sase-core: tool_run::projection with live_glance/briefs/node_summaries, shared verdict bucket, silent_after_s=60, agent/owner/reference indexes, 3 PyO3 bindings. Verified: 23 new core tests pass, full sase_core lib 3707 pass, sase_core_py 222 pass, clippy/fmt clean on touched files. just check gate stays red only on 2 pre-existing clippy lints in untouched launch_scratch_liveness.rs (recorded as follow-up).

## Dependencies

- **Blocks:** [sase-1bt.2](sase-1bt.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.3](sase-1bt.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.1/README.md) | [sase-1bt.1](sase-1bt.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9368ddf`](https://github.com/sase-org/sase-core/commit/9368ddfc916e44cf2b05d95ca46dcc428a6b9dd0) | feat(tool-run): add live glance, briefs, and node-summary projections | [sase-1bt.1](sase-1bt.1.md) | 2026-09-27 19:26:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.1/README.md

<!-- sase:referenced-by:end -->
