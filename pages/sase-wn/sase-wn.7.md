# Bead: sase-wn.7 — Stop multi-second idle re-renders of the prompt panel

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.7` · **Size:** medium
**Created:** 2026-09-04 12:11:12 EDT · **Closed:** 2026-09-04 17:29:39 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-idle-render-cache: make prompt-panel rendering (section-navigation strips/heights, lazy syntax highlighting, frontmatter lexing) cache-stable across refreshes of unchanged content, so an idle ace stops logging 1.5-4s main-thread stalls re-rendering the same document.

## Notes

[2026-09-04T21:28:21Z · sase-wn.7] PROPOSED FOLLOW-UP: models-panel xdist flakes — test_panel_warns_once_and_keeps_alias_warning_through_refresh and earlier test_action_reset_custom_alias_deletes_custom_entry failed once each under the 8414-item scoped just check suite and passed in isolation; not caused by the idle render-cache change.

[2026-09-04T21:29:39Z · sase-wn.7] Idle prompt-panel renders of unchanged documents skip widget update (same generation/visual), reuse SectionTrackingVisual height/anchors/strips by content hash+width+style, and reuse frontmatter tokens plus CachedRenderable highlight/segments by content+width+style. Prompt-panel section navigation, lazy_syntax, frontmatter, and digest tests pass. just check lint green; scoped suite 8413 passed with one unrelated models-panel xdist flake that passed in isolation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.7/README.md) | [sase-wn.7](sase-wn.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`969c22b`](https://github.com/sase-org/sase/commit/969c22ba06edd575ff26629f2c11a6547ab3b71b) | feat(ace): cache idle prompt-panel renders of unchanged documents | [sase-wn.7](sase-wn.7.md) | 2026-09-04 19:06:31 EDT |
