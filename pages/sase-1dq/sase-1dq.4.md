# Bead: sase-1dq.4 — Inline ghost placement before closing punctuation, calmer hints, and module split

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.4` · **Size:** medium
**Created:** 2026-09-30 16:38:25 EDT · **Closed:** 2026-09-30 19:35:05 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

inline-ghost-placement: split the next-word mixin into a host-neutral ghost display layer and pure placement helpers. Add the before-closer inline placement with tail-aware width fitting, and make Ctrl+L accept-all everywhere with fish keys only at true end of line. Typing-triggered hints wait for a 350 ms reveal beat, boundary auto triggers work away from line end, and ghosts are allowed in the legacy feedback mode.

## Notes

[2026-09-30T23:34:38Z · sase-1dq.4] PROPOSED FOLLOW-UP: symvision flags get_unread_set_generation (plus has_unread_probe_cache_key, note_unread_set_changed siblings) in src/sase/ace/tui/actions/agents/_unread_set_generation.py as unused-public; verified identical on the clean base tree via git stash plus direct symvision run, so pre-existing and unrelated to this phase; no open task bead tracks it

[2026-09-30T23:35:05Z · sase-1dq.4] inline-ghost-placement done: new pure next_word_placement module (none/inline_eol/inline_tail/peek, closing-tail set, tail-aware fitting, generalized auto trigger) and host-neutral _next_word_ghost_display mixin (ghost state/validation/accepts, 350ms reveal-beat timer, hint-surface hook); _prompt_next_word is prompt-only (chain/ladder/menu). Ctrl+L accepts everywhere, Right/Ctrl+F and Alt+F take ghost only at true EOL (Textual default inserts live suggestion, so plain motion drops it first), feedback mode unblocked for ghosts, auto triggers on any non-word char after a word. Verified: 75 focused tests pass (placement 10, prompt_next_word 29, inline_tail 11, completion+menu 25), 3 visual goldens applied and inspected (new before_closer plus 2 hint-text updates), sase tool run check clean except pre-existing base-tree symvision flags in _unread_set_generation.py (recorded as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1dq.3](sase-1dq.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.5](sase-1dq.5.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.4/README.md) | [sase-1dq.4](sase-1dq.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7b3d47c`](https://github.com/sase-org/sase/commit/7b3d47c3ea9a0c43d8c179658fcd3b0179397951) | feat(ace-tui): next-word ghost placement, display mixin and prompt integration | [sase-1dq.4](sase-1dq.4.md) | 2026-09-30 19:37:33 EDT |
