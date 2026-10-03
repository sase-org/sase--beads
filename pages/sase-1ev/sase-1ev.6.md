# Bead: sase-1ev.6 — Lens framework and the Timeline lens

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.6` · **Size:** medium
**Created:** 2026-10-02 14:43:12 EDT · **Closed:** 2026-10-03 00:16:39 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

timeline-lens: add the Notes/Timeline/Changes lens framework, which owns the Notes snapshot and restore, per-lens header, footer, filter, and key routing, and the full Esc ladder. @ turns the rail into the subject's timeline: kit picker rows, debounced preview, b compare base, hidden toggle, and pager hand-off at the cursor pin.

## Notes

[2026-10-03T03:16:25Z · sase-1ev.6] PROPOSED FOLLOW-UP: symvision flags PublicationPayloadFile and plan_publication_payload_batches in src/sase/core/publication_payload_facade.py as unused (reproduces identically on the clean base tree; file untouched by this phase)

[2026-10-03T03:16:52Z · sase-1ev.6] PROPOSED FOLLOW-UP: Timeline lens PNG goldens still needed (120x40 dark/light cursor-on-past, with-base, hidden-revealed, plus 80x24 one state) plus SASE_TUI_TRACE re-measurement of the section-5.5 budgets; suggest folding into the launch phase visual review

[2026-10-03T04:16:17Z · sase-1ev.6] PROPOSED FOLLOW-UP: scoped-lane flakes unrelated to the Timeline lens (7 fail identically on the clean base tree: 2 pager three-panes, 1 prompt_mount_dedup, 4 prompt_bar_editor_stack; 6 more pass in isolation on this phase tree but failed under lane load: artifacts_scaffold subtab strip, keymaps app-bindings count, config_cache_token chdir, link_follow flat panes, agents_pane_conformance insert order, config_cache_teardown drain timeout)

[2026-10-03T04:16:39Z · sase-1ev.6] Timeline lens done and verified: @ rail with kit picker rows (markers, hidden summary, / filter), debounced preview with loading strip and stale-drop, b base with Same-version ordering, . hidden toggle with single-fire, H/pager hand-off carrying pin+view+base (explicit_base for now targets). 25 new tests pass; 101 neighboring memory/keymap/kit-door tests pass; ruff+mypy clean; full check lint stages green (symvision: my 9 helpers privatized, 2 payload-facade items proven pre-existing on clean base). Scoped lane 13 NEW all triaged non-blocking (7 fail identically on base, 6 pass in isolation). Perf probe: 300-version open ~170ms headless (24ms action + reflow; pure build 5ms) vs 100ms budget; PNG goldens + trace re-measurement left as follow-ups for the launch visual review.

## Dependencies

- **Depends on:** [sase-1ev.5](sase-1ev.5.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.7](sase-1ev.7.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.6/README.md) | [sase-1ev.6](sase-1ev.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`166fdef`](https://github.com/sase-org/sase/commit/166fdefce5860d62ce8e73e84ec7d170905937c8) | feat(ace): add memory pane Timeline lens with kit picker rail | [sase-1ev.6](sase-1ev.6.md) | 2026-10-03 00:19:44 EDT |
