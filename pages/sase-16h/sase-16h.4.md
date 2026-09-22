# Bead: sase-16h.4 — Refuse a raw agent invocation of a guarded recipe

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.4` · **Size:** medium
**Created:** 2026-09-22 13:05:42 EDT · **Closed:** 2026-09-22 17:00:58 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

recipe-guard: add the dependency-free tools/require_tool_run script, wire it into check and check-full, document the environment contract, teach the adoption report bypasses and refusals, and record the decision that partly supersedes record-before-admit.

## Notes

[2026-09-22T20:59:42Z · sase-16h.4] PROPOSED FOLLOW-UP: just check is red on master — toobig flags tests/service/test_service_host_scenarios.py at 1242 lines (limit 1000, from 716c77dce), blocking every agent verification lane

[2026-09-22T21:00:13Z · sase-16h.4] PROPOSED FOLLOW-UP: two tests fail standalone on an untouched tree — test_no_system_clock_display_sites and test_preview_modal_resize_recomputes_geometry — needs triage as CI-failure or flake

[2026-09-22T21:00:58Z · sase-16h.4] recipe-guard landed: tools/require_tool_run (0755, POSIX sh, never starts sase) wired first dep of check/check-full; 17-test behavior matrix + wiring tests pass; adoption report gains bypassed class, refusal count, per-call timestamps (schema v2); docs/tool.md contract table; decisions/guarded-recipes.md added with record-before-admit marked superseded-in-part; sase memory init regenerated; manifest re-curated to 68. Verified: sase tool run check executes wrapped while raw just check refuses exit 2; scoped lane 45163 passed with only pre-existing failures (toobig red master, timezone/geometry tests, noted as follow-ups)

## Dependencies

- **Depends on:** [sase-16h.3](sase-16h.3.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16h.5](sase-16h.5.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.4/README.md) | [sase-16h.4](sase-16h.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7fad339`](https://github.com/sase-org/sase/commit/7fad3394ca04d16d0331755ffd70b64c3fc362b8) | feat(tool): refuse raw agent runs of guarded check recipes | [sase-16h.4](sase-16h.4.md) | 2026-09-22 17:02:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16h.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.4/README.md

<!-- sase:referenced-by:end -->
