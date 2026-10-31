# Bead: sase-1q2.4 — Fix the pager, footprint, import-budget, and visual-lane reds

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Assignee:** `sase-1q2.4` · **Size:** medium
**Created:** 2026-10-30 12:37:07 EDT · **Closed:** 2026-10-31 01:41:51 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

tui-reds: fix the pager notify teardown errors, the footprint microbench, the TUI import budget, and the tool-runs visual sentinel, then clear any other visual drift.

## Notes

[2026-10-31T05:41:33Z · sase-1q2.4--b] PROPOSED FOLLOW-UP: just check _lint-flags fails on macro input-schema drift — the sase_core_rs builtin catalog contains a wait_target input type while src/sase/config/sase.schema.json and src/sase/macros/workflow.schema.json lack it; phase diff touches neither side (git show HEAD confirms 0 wait_target in both files), so the owner of macro input types or the core pin should run tools/sync_macro_input_schemas --write and land the regenerated schemas.

[2026-10-31T05:41:43Z · sase-1q2.4--b] PROPOSED FOLLOW-UP: full parallel screenshot run (6 workers) reports 2 unstable-but-passing recaptures (agents_renamed_generic_session_root, agents_stranded_resolve_modal) while 20/20 serial -n 1 cycles are clean with zero unstable; likely parallelism contention flake for the visual-lane owner to triage, not product drift (goldens unchanged, harness status clean, exit 0).

[2026-10-31T05:41:51Z · sase-1q2.4--b] tui-reds complete: pager notify teardown, footprint microbench, TUI import budget, and tool-runs visual sentinel fixed plus visual drift cleared. Verified: TZ=UTC just fix-tui-screenshots --check exit 0, status clean, created=0 updated=0 stale=0 (1137 unchanged); 20/20 serial targeted captures clean; just fix exit 0; sase bead epic-symbols empty. sase tool run check still fails only on pre-existing macro input-schema drift (wait_target), recorded as PROPOSED FOLLOW-UP; parallel-run unstable recaptures also recorded.

## Dependencies

- **Blocks:** [sase-1q2.6](sase-1q2.6.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q2.4.md) | [sase-1q2.4](sase-1q2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e28334c`](https://github.com/sase-org/sase/commit/e28334c45a72ec02d10b0564b06909f6d14751bf) | fix(tui): clear pager, footprint, import-budget, and visual-lane reds | [sase-1q2.4](sase-1q2.4.md) | 2026-10-31 01:43:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q4.2][1] | Need pager-reds epic phase scope before classifying PagerScreen.notify teardown errors | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.2/README.md

<!-- sase:referenced-by:end -->
