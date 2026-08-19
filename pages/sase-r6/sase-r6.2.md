# Bead: sase-r6.2 — Rebind existing load-more panels

[Bead Pages](../README.md) / [sase-r6](README.md) / sase-r6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.086](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.086.md) · **Assignee:** `sase-r6.2` · **Size:** medium
**Created:** 2026-08-19 17:09:40 EDT · **Closed:** 2026-08-19 19:13:18 EDT
**Plan:** [202608/load\_more\_ctrl\_j.md](https://github.com/sase-org/sase--plans/blob/main/202608/load_more_ctrl_j.md)

## Description

modals: switch prompt-history, alias-history, and revive-agent paging to Ctrl+J / Ctrl+K with plus-or-minus page-size, not doubling.

## Notes

[2026-08-19T23:13:18Z · sase-r6.2] Rebind prompt-history, alias-history, and revive-agent paging to Ctrl+J load-more / Ctrl+K unload with ace.page_size (default 100), plus-or-minus not doubling. Prompt-history and revive keep a page/cursor stack so unload drops only the last page and the next load-more refetches it; alias-history adds/subtracts page_size down to model_alias_history_limit. Intercepts both chords while modal filters are focused. Docs, unit/pilot tests, and alias-history plus prompt-history PNG goldens updated. just check passed (symvision included; scoped tests escalated to the full suite because Justfile dropped the sase-r6.2(get_ace_page_size) epic-symbol after the three modals consumed it). sase bead epic-symbols sase-r6.2 reports no leftovers. CHANGELOG is release-please generated from the feat commit at land.

[2026-08-19T23:14:28Z · sase-r6.2] Rebind prompt-history, alias-history, and revive-agent paging to Ctrl+J load-more / Ctrl+K unload with ace.page_size (default 100), plus-or-minus not doubling. Prompt-history and revive keep a page/cursor stack so unload drops only the last page and the next load-more refetches it; alias-history adds/subtracts page_size down to model_alias_history_limit. Intercepts both chords while modal filters are focused. Docs, unit/pilot tests, and alias-history plus prompt-history PNG goldens updated. just check passed (symvision included; scoped tests escalated to the full suite because Justfile dropped the sase-r6.2(get_ace_page_size) epic-symbol after the three modals consumed it). sase bead epic-symbols sase-r6.2 reports no leftovers.

## Dependencies

- **Depends on:** [sase-r6.1](sase-r6.1.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r6.2/README.md) | [sase-r6.2](sase-r6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`84e09d5`](https://github.com/sase-org/sase/commit/84e09d5daf448aeb2235daee2d3f6aa28bdd1dbe) | feat(ace): rebind load-more panels to Ctrl+J / Ctrl+K | [sase-r6.2](sase-r6.2.md) | 2026-08-19 19:15:16 EDT |
