# Bead: sase-1ux.4 — Failure signals on Agents-tab rows, waves, and jump strips

[Bead Pages](../README.md) / [sase-1ux](README.md) / sase-1ux.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1f4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1f4.md) · **Assignee:** `sase-1ux.4` · **Size:** medium
**Created:** 2026-11-22 08:33:07 EST · **Closed:** 2026-11-22 14:13:13 EST
**Plan:** [202611/failed\_clan\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_clan_visibility.md)

## Description

row-signals: render the failure clearly in the list. Add a clan-row cause chip naming the failed member and its cause, show the failure time instead of a running hourglass on Failed rollups, and draw a red ✗ wave pip and ▶→✗ in WAVES. Put the ‖ glyph in SESSION TURNS and add a visual golden for the incident shape.

## Notes

[2026-11-22T18:52:04Z · sase-1ux.4] PROPOSED FOLLOW-UP: terminology guard still fails on notification-gates.md compatibility spellings (sase-1uy)

[2026-11-22T18:52:10Z · sase-1ux.4] PROPOSED FOLLOW-UP: project metadata audit still expects pre-split lumberjack refresh site (sase-1uz)

[2026-11-22T18:52:15Z · sase-1ux.4] PROPOSED FOLLOW-UP: Failed-clan cause chip drop waits for the next grouping rebuild; first paint and terminal resize do not recompute the drop

[2026-11-22T19:12:37Z · sase-1ux.4] PROPOSED FOLLOW-UP: test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads leaked FinalizerInventoryWorkerResult once in scoped check 033db6ea7cbd381ea400582027fd159a; local rerun passed and the leftover is file-completion GC, not row-signals

[2026-11-22T19:13:13Z · sase-1ux.4] Clan cause chip, failed-turn time column, WAVES ✗, and SESSION TURNS ‖ land on FailureFocus; goldens at 120/80 cols stayed pixel-stable in host TZ and TZ=UTC. Chip drop uses ancestor-capped viewport width and does not treat that budget as insert membership. just check 033db6ea7cbd381ea400582027fd159a: remaining NEW are sase-1uy plus a non-reproducing FinalizerInventoryWorkerResult GC leftover; KNOWN sase-1uz; FLAKY hijack canary.

## Dependencies

- **Depends on:** [sase-1ux.3](sase-1ux.3.md) ✓ · ⧖ 2026-11-22
- **Blocks:** [sase-1ux.5](sase-1ux.5.md) ✓ · ⧖ 2026-11-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ux.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.4/README.md) | [sase-1ux.4](sase-1ux.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`623c826`](https://github.com/sase-org/sase/commit/623c826812eef397bd0912d1d1002682a7570d22) | feat(tui): show failure cause chips, times, and glyphs on Agents rows | [sase-1ux.4](sase-1ux.4.md) | 2026-11-22 14:14:48 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ux.4][1] | Need current phase status, notes, and remaining work before continuing | 4 |
| read-by | [agent:sase-1ux.5][2] | Check earlier phases landed | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.5/README.md

<!-- sase:referenced-by:end -->
