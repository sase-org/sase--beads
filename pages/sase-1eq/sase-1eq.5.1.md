# Bead: sase-1eq.5.1 — TUI macro surfaces and goldens

[Bead Pages](../README.md) / [sase-1eq.5](sase-1eq.5.md) / sase-1eq.5.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) · **Assignee:** `sase-1eq.5.1.land`
**Created:** 2026-10-03 13:29:42 EDT
**Plan:** [202610/tui\_macro\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/tui_macro_surfaces.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/tui_macro_surfaces.md

<!-- sase:links:end -->

## Description

Rename the SASE TUI's xprompt modules, identifiers, CSS, copy, keymap actions, and Admin Center ids to macro spellings. The agent prompt tab and headings say raw prompt. Pre-rename resume state still opens, retired keymap actions stay flag-gated aliases, and the PNG goldens match the new pixels.

## Notes

[2026-10-04T20:21:49Z · sase-1fv.land] DISCOVERED ISSUE: During implementation of the existing-definition catalog fix, targeted just fix-tui-screenshots runs repeatedly timed out at tests/ace/tui/visual/test_ace_png_snapshots_existing_finder.py::test_existing_snippet_finder_png_snapshot waiting for the TODO sentinel. The last frame showed the snippet finder open with the first gh plugin row selected and GitHub snippet body in Preview; both TODO rows were visible lower in the match list, so the sentinel does not describe the default selected preview. Likely update the fixture to select todo or wait for the current plugin preview. Three retries failed in each run; the snippet golden remained untouched. This is in scope for the active TUI macro surfaces and goldens work.

[2026-10-04T21:00:37Z · 50--c] -d 🔒 sase-1eq-prompt-precedence-note.md

## Attachments

- 🔒 sase-1eq-prompt-precedence-note.md · text/markdown · 1.05176 KiB (private attachment)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md) | [sase-1eq.5.1](sase-1eq.5.1.md) | 0 |
