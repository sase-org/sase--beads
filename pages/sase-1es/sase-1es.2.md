# Bead: sase-1es.2 — Quadratic scans, span memoization, and the dismissed-view leak

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.2` · **Size:** medium
**Created:** 2026-10-02 08:37:46 EDT · **Closed:** 2026-10-02 12:27:26 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

scan-leak-fixes: fix the theme-watcher leak that keeps every closed pager alive, make link scanning and window-label row lookups near-linear, memoize per-section target spans and live-pin digests, and stop trail entries from retaining search copies.

## Notes

[2026-10-02T16:26:10Z · sase-1es.2] PROPOSED FOLLOW-UP: check-lane failures reproduce on clean base — tests/ace/tui/widgets/test_directive_completion_interactions.py (2 tests), tests/test_xprompt_directive_contract.py, tests/ace/tui/test_app_import_budget.py fail identically with src+tests stashed (likely ahead sase-core checkout contract drift + loaded-host budget)

[2026-10-02T16:26:29Z · sase-1es.2] PROPOSED FOLLOW-UP: full-suite-only flakes pass in isolation with and without this phase — test_directive_completion_matches_aliases_to_canonical_insertions, zsh test_alias_sbd_completes_static_bead_tree[sbd show --for-sbd show --format ], test_block_spread_bracket_top_aligns all pass standalone on both trees but failed in the 16-minute loaded-host check run

[2026-10-02T16:26:43Z · sase-1es.2] PROPOSED FOLLOW-UP: pager visual check-mode reports 38 would-update goldens identically on clean base — exact-pixel drift from this host renderer stack, not from scan-leak-fixes (updated sets match byte-for-byte between trees)

[2026-10-02T16:27:26Z · sase-1es.2] scan-leak-fixes verified: theme signal subscribe/unsubscribe replaces app-theme watch (push/pop x3 + split + app-exit leak tests fail on old code, pass on new; bench leak_live_views=0); scan_links 20k link-dense 21s->0.45s with 400-trial fixed-seed parity vs old algorithm; window label rows O(offset)->O(log+line) with 6000-probe parity (5k-row walks 70s->0.04s); section_target_spans/live-digest/line-prefix memoized per section object; trail PagerSearchState drops corpus/line_starts with rebuild-on-restore; reading_anchor/current_section bisect with reference parity. Gates: just fmt clean, full sase tool run check lint stages incl symvision green, 51571 passed with 7 failures all dispositioned (4 reproduce on clean base, 3 pass in isolation with and without changes = load flakes, recorded as follow-ups); pager visual 102 passed with 38-golden drift set identical on base.

## Dependencies

- **Depends on:** [sase-1es.1](sase-1es.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.5](sase-1es.5.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.2/README.md) | [sase-1es.2](sase-1es.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8d1ac50`](https://github.com/sase-org/sase/commit/8d1ac50c51706848d18aaaf8215ec0dd05745d74) | feat(pager): fix dismissed-view leak, near-linear scans, span/digest memoization, trailless search copies (sase-1es.2) | [sase-1es.2](sase-1es.2.md) | 2026-10-02 13:07:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0vd][1] | Check phase status, deps and notes to assess conflict with three-pane split work | 1 |
| read-by | [agent:sase-1es.2][2] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1es.8][3] | Need prior phase measurements for final comparison | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0vd/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.8/README.md

<!-- sase:referenced-by:end -->
