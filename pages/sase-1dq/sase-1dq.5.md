# Bead: sase-1dq.5 — Mid-sentence next-word peek in the prompt border

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.5` · **Size:** medium
**Created:** 2026-09-30 16:38:27 EDT · **Closed:** 2026-09-30 21:19:15 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

mid-sentence-peek: where an inline ghost would shift prose, show a styled violet peek in the prompt bar's border subtitle. It trims words the text after the cursor already has, degrades by width, appears after the reveal beat when typing-triggered, and is taken with Ctrl+T (one word) or Ctrl+L (all) using the menu separator rules.

## Notes

[2026-10-01T01:19:15Z · sase-1dq.5] Mid-sentence peek done: violet border-subtitle peek with redundancy trim and width degradation; reveal-beat timing; Ctrl+T one-word and Ctrl+L accept-all with menu separator rules; verified by 93 widget tests incl 25 new peek tests, 2 inspected PNG goldens, clean ruff/mypy/symvision, official check lint gates green

## Dependencies

- **Depends on:** [sase-1dq.4](sase-1dq.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.6](sase-1dq.6.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.5/README.md) | [sase-1dq.5](sase-1dq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7255e8c`](https://github.com/sase-org/sase/commit/7255e8cd06e9e43f05bcec1d04ccfa49d78e6d49) | feat(ace-tui): mid-sentence next-word peek in the prompt border (sase-1dq.5) | [sase-1dq.5](sase-1dq.5.md) | 2026-09-30 21:21:55 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dq.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1dq.5/README.md

<!-- sase:referenced-by:end -->
