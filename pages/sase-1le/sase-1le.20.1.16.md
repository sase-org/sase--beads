# Bead: sase-1le.20.1.16 — History and duplicate sweep for reference/tui/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.16

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.16` · **Size:** medium
**Created:** 2026-10-16 08:04:39 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

tui-edit: strip history, bead IDs, and epic labels from the TUI reference pages into reference/upgrading/, replace keymap and registry restatements with generated links, and confirm template shape.

## Notes

[2026-10-16T20:20:41Z · sase-1le.20.1.16] Counts: history hits 101→52 on reference/tui/ and contribute/tui-rendering.md (kept current-feature "legacy" names, UI strings such as "no longer pending"/"no longer available", and "previously" as earlier-in-session). Replaced 2 hand-maintained CLI flag tables with generated-page links (sase tui, sase pager); linked generated screenshot/proc/final/agent-hold/patch-set-origin/tmux-agent/artifact CLI pages; added generated TUI keymaps links on agents-tab, files-and-preview, launch-control, procs-tab, projects-tab, and contribute/tui-rendering. All TUI pages keep opening sentence, Related, and description ≤160. Created docs/reference/upgrading/tui.md (command name, aliases, query tokens, prompt-history store, config/keymap aliases, in-process pager, detached procs, dismissed-name prefix, HITL/launch fallbacks, glossary lane, prompt-stack restore, session suffixes, Artifacts Agent pane, keymap moves, auto-name migration). 0 leftover --epic-symbol entries. just docs-lint passed (3 pre-existing contribute over-budget warnings). just docs-check passed (2776 URLs).

## Dependencies

- **Blocks:** [sase-1le.20.1.21](sase-1le.20.1.21.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.6](sase-1le.20.1.6.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.16](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.16.md) | [sase-1le.20.1.16](sase-1le.20.1.16.md) | 0 |
