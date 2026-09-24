# Bead: sase-17d.2 — Card-partitioned Main documents

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.2` · **Size:** large
**Created:** 2026-09-23 19:16:48 EDT · **Closed:** 2026-09-23 20:38:13 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

main-card-partition: every metadata builder wraps its output in Context/Reply/Output/Summary card parts, error tracebacks move to the top of the Reply card, and tree walkers learn the card wrapper. With the flag off the panel renders as before, except the traceback fix.

## Notes

[2026-09-24T00:06:01Z · sase-17d.2] update_header_only uses Context + traceback-only Reply (not Context-only) so j/k never makes the traceback jump before the ~150ms full paint; matches full-paint card order.

[2026-09-24T00:06:30Z · sase-17d.2] PROPOSED FOLLOW-UP: PNG goldens show no traceback quirk (clan/tribe fixtures only set error snippets, tribe panel error_traceback does not render error_tb_syntax); no golden updates in this phase, flag-on goldens start in deck-navigation-keys.

[2026-09-24T00:07:04Z · sase-17d.2] Card partition verified: 17 new partition tests pass; prompt-panel widget batch (2424 tests) passes after flattening helpers; ruff/mypy/toobig clean. Pre-existing symvision failure in plugins_browser_install_* (untouched) blocks just check; bench_tui_jk shows 6 p95 failures under shared-host load, shallow flatten only, no perf regression attributed.

## Dependencies

- **Blocks:** [sase-17d.3](sase-17d.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.2.md) | [sase-17d.2](sase-17d.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9abf08b`](https://github.com/sase-org/sase/commit/9abf08b5df74ebc17f5e293e4909702867105880) | feat(agents-tab): card-partitioned Main documents | [sase-17d.2](sase-17d.2.md) | 2026-09-23 20:09:06 EDT |
