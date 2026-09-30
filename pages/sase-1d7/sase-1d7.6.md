# Bead: sase-1d7.6 — One batched unread chrome helper with no full rebuilds

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.6` · **Size:** medium
**Created:** 2026-09-30 07:18:14 EDT · **Closed:** 2026-09-30 11:57:39 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

unread-chrome-helper: route every unread change through one helper that patches only visible changed rows via an identity map, skips collapsed panels, never falls back to a full rebuild, and refreshes titles, info panel, machine chip/tab strip and tribe summary once each.

## Notes

[2026-09-30T15:57:12Z · sase-1d7.6] PROPOSED FOLLOW-UP: sase tool run check blocked in _setup by validate_sase_core_rs prompt-prediction probe (confident False, expected True); reproduces byte-identically on clean base tree, unrelated to this phase

[2026-09-30T15:57:39Z · sase-1d7.6] One batched unread chrome helper: new _unread_chrome.apply_unread_chrome routes bulk/single/undo/rollback/reconcile paint through an identity map, skips collapsed/off-tab rows, rebuilds at most the failing panel (never full rebuild), refreshes titles+info+header/tab-strip+tribe once each, emits unread.chrome_apply span; _try_patch uses identity lookup + refresh_title flag. Verified: 152 unread tests incl 6 new chrome tests pass, 150 display-patch consumer tests pass, ruff+format+mypy clean on touched files; full check blocked by base-reproducing validator failure (see bead note).

## Dependencies

- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.7](sase-1d7.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.8](sase-1d7.8.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.9](sase-1d7.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.6/README.md) | [sase-1d7.6](sase-1d7.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`30a04f9`](https://github.com/sase-org/sase/commit/30a04f9a31beb60da60f808611f680f045e1733e) | feat(agents): one batched unread chrome helper with no full rebuilds | [sase-1d7.6](sase-1d7.6.md) | 2026-09-30 11:59:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.6][1] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.6/README.md

<!-- sase:referenced-by:end -->
