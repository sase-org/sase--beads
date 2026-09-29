# Bead: sase-1cj.5 — Off-thread prediction corpus warm cache for the TUI

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.5` · **Size:** medium
**Created:** 2026-09-29 07:14:31 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

prediction-cache: build history rows (origin, project, cancelled), compile the history and session corpora off-thread next to the history-word warm job, swap them in atomically, compose the model, and give widgets a non-blocking predict accessor that degrades to silence.

## Dependencies

- **Blocks:** [sase-1cj.10](sase-1cj.10.md) ◐ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.2](sase-1cj.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.4](sase-1cj.4.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.6](sase-1cj.6.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.8](sase-1cj.8.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.9](sase-1cj.9.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.5/README.md) | [sase-1cj.5](sase-1cj.5.md) | 0 |
