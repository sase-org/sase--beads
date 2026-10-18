# Bead: sase-1mk.2 — Teach the release watcher about the core release PR

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.2` · **Size:** medium
**Created:** 2026-10-18 09:58:29 EDT · **Closed:** 2026-10-18 11:52:36 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

watcher-core: read the sase-core release-plz PR, stop with CORE_CI_RED when it is red, and optionally dispatch the core release cut.

## Notes

[2026-10-18T15:52:15Z · sase-1mk.2] PROPOSED FOLLOW-UP: flaky tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree[sbd show --for-sbd show --format ] — failed once in the full test-scoped lane of `sase tool run check` (run 66ed91b191ad, 56463 passed, 1 failed) under load; passes alone in 1.4s on the same tree, and nothing in this phase touches completion code.

[2026-10-18T15:52:26Z · sase-1mk.2] watcher-core landed in tools/release_watch: new core_pr signal (reads the open sase-core release-plz PR by branch/title shape, deduped rollup per workflow+check, plus the last 20 Release-plz runs incl. event, only while --await-core-version is set and published core is older); CORE_CI_RED = exit 19 when every check on the PR head completed with a failure and that held 45 min of observation (new head SHA or any check restarting resets the clock); opt-in --dispatch-core-cut (requires --await-core-version) runs `gh workflow run release-plz.yml -R sase-org/sase-core --ref master -f dry_run=false` when checks are registered and none failed, no Release-plz run is in flight, no workflow_dispatch run started in 90 min, cap 3 per watch, honors --no-dispatch/--dry-run/--once (would dispatch:core_cut); state line carries core_pr=off|none|#N:vX.Y.Z:HEAD12:no_checks|pending|failing|red|green[:cut_in_flight]; evidence block lists core PR rollup, failing checks with URLs, and Release-plz runs; docs/contribute/rust-backend.md updated. Live read-only preflight (--await-core-version 0.42.0 --dispatch-core-cut --once --dry-run, exit 0) parsed core PR #331 as core_pr=#331:v0.42.0:e5ebd9613b25:red with no core_cut action because macOS is still red. New tests: tests/test_release_watch_core_parse.py and tests/test_release_watch_core_decisions.py (39 tests); all 86 pre-existing release_watch tests still pass. This phase fixes no flake task beads.

[2026-10-18T15:52:36Z · sase-1mk.2] watcher-core done: tools/release_watch reads the sase-core release-plz PR + Release-plz runs while awaiting core, stops with CORE_CI_RED (exit 19) after 45 min of fully-completed red checks on one head, and (opt-in --dispatch-core-cut, core_cut=yes) dispatches release-plz.yml dry_run=false under the specified gates, 90-min cooldown and cap of 3; core_pr= state-line field, evidence block, --help and docs/contribute/rust-backend.md updated. Verified: 39 new tests + 86 existing release_watch tests pass; live --once --dry-run preflight exit 0 parsed core PR #331 as red; just fix clean; sase tool run check passed every lint gate and 56463 tests, with one load flake (tests/completion/test_zsh_smoke.py sbd completion) that passes alone and is recorded as a PROPOSED FOLLOW-UP; epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.2/README.md) | [sase-1mk.2](sase-1mk.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3b78c03`](https://github.com/sase-org/sase/commit/3b78c034416896078989ebf6274034223ff00d16) | feat(release-watch): watch the sase-core release PR and add CORE\_CI\_RED | [sase-1mk.2](sase-1mk.2.md) | 2026-10-18 11:53:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1mk.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.2/README.md

<!-- sase:referenced-by:end -->
