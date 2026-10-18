# Bead: sase-1mk.3 — Fix the files Ctrl-J anchor-scroll Full CI flake at its root

[Bead Pages](../README.md) / [sase-1mk](README.md) / sase-1mk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.3` · **Size:** medium
**Created:** 2026-10-18 09:58:29 EDT · **Closed:** 2026-10-18 11:07:22 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

deck-scroll: make test_files_ctrl_j_scrolls_page_anchor_to_top (sase-1a7) deterministic under Full CI load.

## Notes

[2026-10-18T15:07:09Z · sase-1mk.3] PROPOSED FOLLOW-UP: Revisit existing monitor-capacity flake sase-12f — check ToolRun 804cd408b2b32ed47b9f88e827134e2f exited 1/no_new_failures with the renamed delayed-child-bootstrap node triaged FLAKY; sase-12f already tracks repeated loaded-lane evidence.

[2026-10-18T15:07:22Z · sase-1mk.3] Fixed Files spread Ctrl-J by scheduling the page jump after reserve-backed layout, requiring the live anchor to be within max_scroll_y, and retrying until the refreshed view confirms the landing; transition generations discard stale callbacks. Earlier 1c1.7 only invalidated the old transition restore, while 1i5.7 made the test follow a moving target; neither reapplied a scroll clamped against the old extent. Verified 20 focused spread/block pilot tests under six workers and six spread-pilot-file copies under six workers (78 passed, including repeated Files jumps). sase tool run check exited 1/no_new_failures: formatting, lint, SASE validation, and committed-plan checks passed; the sole FLAKY delayed-child-bootstrap failure is tracked by sase-12f and noted as follow-up. epic-symbols was empty.

## Dependencies

- **Blocks:** [sase-1mk.8](sase-1mk.8.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.3/README.md) | [sase-1mk.3](sase-1mk.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7dd39ff`](https://github.com/sase-org/sase/commit/7dd39ff95f7720417fe021307673bb439aed7742) | fix(ace): defer Files spread scroll until layout settles | [sase-1mk.3](sase-1mk.3.md) | 2026-10-18 11:08:45 EDT |
