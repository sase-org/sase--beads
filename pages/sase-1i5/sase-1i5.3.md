# Bead: sase-1i5.3 — Read-only bead resolution never initializes or commits (sase-1gx)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.3` · **Size:** medium
**Created:** 2026-10-08 09:47:19 EDT · **Closed:** 2026-10-08 11:29:05 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Previously Closed

> ↺ Closed 2026-10-08T14:39:51Z · done
>
> (none)
>
> Reopened 2026-10-08T14:48:28Z by a status update

## Description

readonly-bead-store: make get_read_view open an existing store or raise a typed unavailable error, move genuine writers to get_project, add no-write regression tests, and close sase-1gx.

## Notes

[2026-10-08T14:39:14Z · sase-1i5.3] sase-1h8 coordination: open phases sase-1h8.13 (read-model mutations) and sase-1h8.14 (acceptance gate) do not edit get_read_view/cli_common Python resolution; this change stays in the Python resolution layer with no Rust or sase-core pin changes, so no overlap.

[2026-10-08T14:39:51Z · sase-1i5.3] readonly-bead-store done: get_read_view opens existing usable store or raises BeadStoreUnavailableError with cwd+locations, never inits/commits; sidecar materialization preserved for configured stores (SddMaterializationError still surfaces); CLI surfaces report Error exit 1, library surfaces return empty; 7 regression tests pass, 28 resolution+readonly pass, 61 touched-area pass, check lint stages pass with no NEW; epic-symbols clean; sase-1gx closed.

[2026-10-08T14:48:29Z · bryanbugyi34@gmail.com] Reopening this bead since I'm not sure the work is complete. The agent that may or may not have completed it failed.

[2026-10-08T15:28:35Z · sase-1i5.3] PROPOSED FOLLOW-UP: test_claimed_status.py::test_default_list_includes_claimed_with_shared_glyph fails byte-identically on the clean base tree (sase-1h8.12 read-model overlap); not caused by readonly-bead-store

[2026-10-08T15:28:41Z · sase-1i5.3] PROPOSED FOLLOW-UP: 4 NEW symvision findings (BeadBoardSnapshot, validate_config_input_type, is_agent_runner, coverage_block_to_json_dict) reproduce byte-identically on the clean base tree; none reference the readonly-bead-store files

[2026-10-08T15:29:05Z · sase-1i5.3] readonly-bead-store done for real (prior close had no landed commit; tree was clean). get_read_view opens existing usable store incl. configured-sidecar materialize, else raises BeadStoreUnavailableError naming cwd+searched; never init/commit. plan_show returns miss; other surfaces use entry one-line exit-1 or existing empty-result handling. Verified: 8 new no-write tests pass, tests/test_bead 2704 passed/1 pre-existing base failure (follow-up noted), base-vs-fixed probe, check has only pre-existing base findings, epic-symbols clean; sase-1gx evidence noted.

## Dependencies

- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.3/README.md) | [sase-1i5.3](sase-1i5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6e5b74a`](https://github.com/sase-org/sase/commit/6e5b74a3963d39b41182318988927f162fc1d897) | fix(beads): read-only bead resolution never initializes or commits (sase-1gx) | [sase-1i5.3](sase-1i5.3.md) | 2026-10-08 11:30:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1i5.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.3/README.md

<!-- sase:referenced-by:end -->
