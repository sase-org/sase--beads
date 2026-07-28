# Bead: sase-4q.2 — Phase 2 - Capture: stash keymaps + top-bar indicator + toasts

[Bead Pages](../README.md) / [sase-4q](README.md) / sase-4q.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4q.2`
**Created:** 2026-06-16 02:11:39 UTC · **Closed:** 2026-06-16 15:06:54 UTC
**Plan:** [202606/prompt\_stash.md](https://github.com/sase-org/sase--plans/blob/main/202606/prompt_stash.md)

## Notes

COMMIT: f9f86dbf7

[2026-07-27T21:34:20Z · sase-a1.land] [2026-06-16T15:04:51Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 (Capture) complete. Bar comma-leader ,s/,S (stash_active_pane/stash_all_panes in _prompt_input_bar_stack_actions.py) capture pane text(s)+frontmatter and post PromptInputBar.Stashed (presentation-only, D6). Comma leader extended to single-pane prompt mode (no prior char search) so ,s works on a lone draft while reverse char-search ,/repeat is preserved. App glue PromptBarStashMixin (_prompt_bar_stash.py) persists via prompt_stash_facade.append (project from prompt context, minted id/created_at), toasts, refreshes badge, and on empty bar unmounts via post-submit path (no double cancelled-history save). New StashedPromptsIndicator widget (❄ on #AF87FF, hidden at 0) in top bar; _refresh_prompt_stash_indicator reads snapshot count on startup + after each capture. normal_mode_subtitle advertises ,s/,S. Justfile pyvision whitelist trimmed (read/append/path now used; pop/rewrite remain for Phase 3). Tests: indicator rendering, widget capture, app-handler persistence/no-op. just check green.

## Dependencies

- **Depends on:** [sase-4q.1](sase-4q.1.md) ✓
- **Blocks:** [sase-4q.3](sase-4q.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4q.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4q.2/README.md) | [sase-4q.2](sase-4q.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`fec3f86`](https://github.com/sase-org/sase/commit/fec3f86830367ecd7914f1e3087ea5909dc9f451) | feat(prompt-stash): capture keymaps, top-bar indicator, and toasts (sase-4q.2) | [sase-4q.2](sase-4q.2.md) | 2026-06-16 15:07:43 |
