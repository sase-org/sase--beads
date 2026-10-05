# Bead: sase-1eq.5.1.6 — PNG goldens, terminology guard, and navigation benchmark

[Bead Pages](../README.md) / [sase-1eq.5.1](sase-1eq.5.1.md) / sase-1eq.5.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.6` · **Size:** medium
**Created:** 2026-10-03 13:29:51 EDT · **Closed:** 2026-10-04 20:49:21 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1ge][1] | Proposing phase: note #2 reproduced the failure on a clean base during the j/k benchmark run |
| related | [bead:sase-1gf][2] | Proposing phase: note #2 reproduced the failure on a clean base during the j/k benchmark run |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ge/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1gf/README.md

<!-- sase:links:end -->

## Description

tui-goldens: rename the xprompt PNG goldens, re-baseline changed pixels, widen the terminology guard over the TUI scope, and run the j/k navigation benchmark.

## Notes

[2026-10-04T20:26:21Z · sase-1eq.5.1.6] PROPOSED FOLLOW-UP: the core-flip phase must rename the Jinja scope and completion spacer binding; pinned sase-core still accepts the xprompt scope and exports the xprompt completion spacer binding, so TUI adapters centralize those names until sase-1eq.10.

[2026-10-05T00:48:00Z · sase-1eq.5.1.6--3] PROPOSED FOLLOW-UP: triage clean-base and xdist failures surfaced during tui-goldens — detail: test_machine_bootstrap_help_has_no_secret_cli_value fails identically on a clean base worktree and no matching task was found; seven j/k benchmark failures reproduce on clean base (selected-tribe p95 is tracked by sase-lx, AXE sample-set mismatch by sase-199, plus clan stall, three fleet-fault p95s, and link-rail delta); output-variable PNG verification fails on clean base and is tracked by sase-1bb; artifacts-limit Ctrl+J failed only in the full xdist check and passed focused rerun, matching the FrontmatterPanel NoMatches flake class in sase-1fy and sase-1g5.

[2026-10-05T00:49:21Z · sase-1eq.5.1.6--3] Regenerated and reviewed the full TUI PNG inventory: 0 creations, 2 expected pixel updates, 6 stale removals supported by full-inventory evidence; macro terminology guard passed (10 tests) and focused related suites passed (105 tests). The j/k benchmark failures reproduced on clean base (recorded with sase-lx/sase-199); output-variable PNG failure is tracked by sase-1bb. Full check reported 52,588 passed and 2 failures: machine bootstrap help reproduced on clean base, and the artifacts Ctrl+J xdist failure passed focused rerun; both are recorded as proposed follow-up. Epic-symbol check was empty.

## Dependencies

- **Depends on:** [sase-1eq.5.1.5](sase-1eq.5.1.5.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.6.md) | [sase-1eq.5.1.6](sase-1eq.5.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`404b0e2`](https://github.com/sase-org/sase/commit/404b0e2ac2081d84d9c198b50639277ae655f46c) | refactor(tui): finish macro terminology and PNG golden sweep | [sase-1eq.5.1.6](sase-1eq.5.1.6.md) | 2026-10-04 22:07:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.6--3][1] | Verify recorded proposed follow-up before closing this phase | 4 |
| read-by | [agent:sase-1eq.5.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.1.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->
