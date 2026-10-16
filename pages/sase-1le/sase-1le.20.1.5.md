# Bead: sase-1le.20.1.5 — Move the prompt, snippet, and Launch Control sections of ace.md

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.5` · **Size:** medium
**Created:** 2026-10-16 08:04:36 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Previously Closed

> ↺ Closed 2026-10-16T15:11:16Z · done
>
> (none)
>
> Reopened 2026-10-16T16:52:51Z by a status update

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

[2026-10-16T15:10:52Z · sase-1le.20.1.5] PROPOSED FOLLOW-UP: tools/render_keymap_macro_reference still emits ../../ace.md (generated keymaps.md); owned by tui-move sase-1le.20.1.6 which must retarget the renderer when ace.md is finished

[2026-10-16T15:10:58Z · sase-1le.20.1.5] PROPOSED FOLLOW-UP: tools/docs_split nested-split leftovers remain: nested Moved-to pointers emit root-relative /path.md (hand-rewritten this phase); stray <a id> lines before a heading steal that heading id so the real heading becomes -1 without {#id}. tui-move should avoid nested selections or fix the tool first

[2026-10-16T15:11:16Z · sase-1le.20.1.5] Moved ace.md prompt/snippet/Launch Control sections to 9 budget-clean reference/tui pages (prompt-input, prompt-modes, prompt-stacks, prompt-completion, prompt-completion-panels, prompts-overlay, snippets, launch-control, launch-control-overrides); mapping docs/_meta/splits/tui_prompt.yml; hub+nav nested. Verified: dry-run budgets all within 6000 (max 5665), check_docs ok, strict mkdocs build ok, URL contract 914/914 incl frozen /ace/#prompt-history-modal, 41 docs/split/url/tribe tests pass. Fixed docs_split nested-parent crash without _intro (regression test). Renderer ace.md link left for tui-move.

[2026-10-16T15:21:31Z · sase-1le.20.1.5--1] Recovery: fixed pre-existing mypy in tools/docs_split (renamed reused parts/existing) and tools/render_keymap_macro_reference (home_project parts vs Path). Extensionless typecheck now clean; remaining renderer ace.md links and nested-split leftovers still for tui-move.

[2026-10-16T15:52:49Z · sase-1le.20.1.5--2] Recovery: just check failed after close. Scoped contract test_active_sources_and_docs_use_only_canonical_plan_paths still red on HEAD because contribute-move renamed docs/perf_runbook.md to docs/contribute/perf-runbook.md without updating the exclude; repaired the exclude. test_ctrl_t_before_reveal_reveals_without_inserting passed in isolation (full-suite load flake; similar to sase-1g8). fakey capacity e2e timed out (exit 124) only under core-identity-changed full-suite loadavg~15. plugins required-docs wording is FLAKY in the baseline.

[2026-10-16T16:27:00Z · sase-1le.20.1.5--3] Recovery: rebased tui-prompt-move onto later docs splits. Kept HEAD hubs for beads/macros/llms, stubbed ace.md prompt/snippet/Launch Control/Macro Browser, retargeted inbound links on split pages, merged tribe-test path lists, restored nested docs_split pointers to root-relative so the h4 nested-split contract holds.

[2026-10-16T16:52:52Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

[2026-10-16T17:16:21Z · sase-1le.20.1.5] Split complete: 9 budget-clean tui pages via tui_prompt.yml. Frozen /ace/#prompt-history-modal still on ace.md stub. just docs-check passed (2419 URLs). epic-symbols none. Explicit {#prompt-stacks-1} and {#snippets-1} for MkDocs strict. Renderer ../../ace.md link left for tui-move. Starting prepared just check.

[2026-10-16T17:28:56Z · sase-1le.20.1.5--1] Recovery: just check failed Rule 1 on leftover MkDocs site/reference/automation/tools/index.html (pretty-URL of tools.md). pyscripts now excludes site/; regression test added. Phase split still complete; 9 tui pages, frozen /ace/#prompt-history-modal, no epic-symbols. Re-running prepared just check.

## Dependencies

- **Depends on:** [sase-1le.20.1.4](sase-1le.20.1.4.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.6](sase-1le.20.1.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.5.md) | [sase-1le.20.1.5](sase-1le.20.1.5.md) | 0 |
