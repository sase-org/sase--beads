# Bead: sase-1le.20.1.5 — Move the prompt, snippet, and Launch Control sections of ace.md

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.5` · **Size:** medium
**Created:** 2026-10-16 08:04:36 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Previously Closed

> ↺ Closed 2026-10-16T14:13:36Z · done
>
> (none)
>
> Reopened 2026-10-16T14:46:09Z by a status update

## Description

tui-prompt-move: move-only partial split of the prompt input, prompt completion, prompts overlay, snippets, macro browser, and Launch Control sections of ace.md (about 33K words).

## Notes

[2026-10-16T14:13:09Z · sase-1le.20.1.5] PROPOSED FOLLOW-UP: tools/render_keymap_macro_reference mypy errors (5, lines 303-306) reproduce identically on clean base and block sase tool run check; file is owned by phase sase-1le.20.1.6 which must edit it for the ace.md link update

[2026-10-16T14:13:18Z · sase-1le.20.1.5] PROPOSED FOLLOW-UP: tools/docs_split nested-split defects hand-worked-around in tui_prompt.yml (dedup-suffixed anchors not written as explicit {#id}; nested Moved-to pointers emitted root-relative which strict MkDocs leaves unrewritten; stray <a id> lines reserve ids that poison later real headings); needs split-tool follow-up before tui-move runs nested selections

[2026-10-16T14:13:36Z · sase-1le.20.1.5] Moved ace.md prompt/snippet/Launch Control sections to 9 budget-clean reference/tui pages (prompt-input, prompt-modes, prompt-stacks, prompt-completion, prompt-completion-panels, prompts-overlay, snippets, launch-control, launch-control-overrides); mapping docs/_meta/splits/tui_prompt.yml; hub+nav updated. Verified: dry-run budgets all within 6000, strict mkdocs build ok, URL contract 564/564 incl frozen /ace/#prompt-history-modal, check_docs ok, fmt-docs-check ok, 61 scoped pytest pass. Also fixed 2 docs_split crash/anchor defects +3 mypy renames with 2 new regression tests (37 pass). Pre-existing render_keymap mypy errors recorded as follow-up; full check still red on those identical-to-base errors.

[2026-10-16T14:46:10Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

## Dependencies

- **Depends on:** [sase-1le.20.1.4](sase-1le.20.1.4.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.6](sase-1le.20.1.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.5/README.md) | [sase-1le.20.1.5](sase-1le.20.1.5.md) | 0 |
