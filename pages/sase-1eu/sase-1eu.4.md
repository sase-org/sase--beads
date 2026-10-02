# Bead: sase-1eu.4 — Agents deck reverse focus, swap, close, and turn keys

[Bead Pages](../README.md) / [sase-1eu](README.md) / sase-1eu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ve](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md) · **Assignee:** `sase-1eu.4` · **Size:** medium
**Created:** 2026-10-02 11:33:56 EDT · **Closed:** 2026-10-02 15:21:19 EDT
**Plan:** [202610/three\_pane\_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)

## Description

deck-pane-keys: add ctrl+b reverse focus, ctrl+shift+f/b swap (aliases > and <), ctrl+shift+d close (alias ctrl+x) and ctrl+t turn on the Agents tab. Wire keymaps, registry pairs, availability, palette, help and docs, and move the debug leak chord to f12.

## Notes

[2026-10-02T19:21:19Z · sase-1eu.4] deck-pane-keys done: ctrl+b reverse focus, ctrl+shift+f/b + >/< swap, ctrl+shift+d/ctrl+x close, ctrl+t turn wired through keymaps/registry/availability/palette/help/docs; debug leak moved to f12. Verified: 117 focused tests (layout/keymaps/availability), 659 deck + 107 catalog + 266 keymap + 128 palette/footer + 67 command-availability tests pass; ruff/mypy/symvision/fmt/validate gates pass. One real conflict found and fixed via new {close_deck_panel, prev_chop_run} allowlist pair (existing ctrl+x override test passes). Full test-scoped (51k, ~22min) exceeds single-turn window; ran all directly-affected suites instead, no failures.

## Dependencies

- **Depends on:** [sase-1eu.3](sase-1eu.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eu.5](sase-1eu.5.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.4/README.md) | [sase-1eu.4](sase-1eu.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2bbc346`](https://github.com/sase-org/sase/commit/2bbc346036cc79c1069ce27ad1bc7f29788f0c0a) | feat(ace): add deck layout operations, keymaps, and palette entries | [sase-1eu.4](sase-1eu.4.md) | 2026-10-02 15:23:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eu.4][1] | Need full description design and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.4/README.md

<!-- sase:referenced-by:end -->
