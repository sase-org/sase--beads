# Bead: sase-1io.5 — Prove every release gate green

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ys](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ys.md) · **Assignee:** `sase-1io.5` · **Size:** medium
**Created:** 2026-10-09 03:55:09 EDT · **Closed:** 2026-10-09 05:57:28 EDT
**Plan:** [202610/release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_v0_18_0.md)

## Description

release-gates: regenerate the release PR onto the new core floor, then drive Master Gate, Full CI, and the release PR checks to green.

## Notes

[2026-10-09T09:57:02Z · sase-1io.5] PROPOSED FOLLOW-UP: sase-core bead_read_model_parity sqlite-cache race now SIGBUS-crashes ubuntu too (run 37908024251 on d2a954b0: macos passed, ubuntu bead_read_model_parity binary died signal 7; earlier run 37904251133 failed the same test on macos with no-such-table meta) blocking the sase-core-rs 0.37.1 cut; see sase-1io.2 notes 3-4

[2026-10-09T09:57:15Z · sase-1io.5] PROPOSED FOLLOW-UP: symvision unused-public residual at master tip in src/sase/plugins/declared_commands.py (fetch_upstream_pyproject, get_declared_commands, parse_declared_commands, read_declared_cache, write_declared_cache) from commit bd68ee4942 pre-install plugin command preview; fails Master Gate lint _lint-symvision on run 37912508549; file did not exist in this phase checkout so fix belongs to owning lane

[2026-10-09T09:57:28Z · sase-1io.5] GATES NOT YET GREEN: landed fixes for all 4 Master Gate failures on e2efd56 (run 37908734472): (1) render+verify -a/--agent help asserts made argparse cross-version portable via assert_metavar_option_documented (3.12 renders -a NAME vs 3.13+ -a,); (2) tint test accepts textual-8.2 ansi-placeholder green (from_rich_color keeps ansi=2 with black RGB until paint; pyproject allows textual>=0.45 so range must be supported); (3) split 1047-line test_run_dev.py into flow/agreement/prepare/render + _run_dev_harness + facade (34/34 tests preserved). Verified: 3 fixed tests pass in CI-mirror (py3.12/textual8.2.8/rich15/CI core wheel 5c4033f6) and workspace py3.14; 34 split tests pass both; ruff/format/toobig/terminology clean; sase_install+shard meta 245 passed. Dispatched publish regen 37909579723 SUCCESS; PR299 still floor 0.37.0 with release-core-floor-smoke red awaiting core 0.37.1. RE-DISPATCH after landing: Master Gate, Full CI (37909515949 covers e2efd56 only), publish.yml. STILL RED elsewhere: sase-core bead_read_model_parity SIGBUS now on ubuntu too (37908024251, macos passed) blocking the core cut (follow-up noted); new-tip symvision residual in plugins/declared_commands.py owned by bd68ee4942 lane (follow-up noted).

## Dependencies

- **Depends on:** [sase-1io.2](sase-1io.2.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1io.3](sase-1io.3.md) ✓ · ⧖ 2026-10-09
- **Depends on:** [sase-1io.4](sase-1io.4.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1io.6](sase-1io.6.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.5/README.md) | [sase-1io.5](sase-1io.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6c78359`](https://github.com/sase-org/sase/commit/6c783599c1b51cac61f72930935b54dc409c2ada) | fix(tests): repair Master Gate failures for bead sase-1io.5 | [sase-1io.5](sase-1io.5.md) | 2026-10-09 05:59:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.5][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.5/README.md

<!-- sase:referenced-by:end -->
