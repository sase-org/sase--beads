# Bead: sase-17m.5.1.4 — Prompt-panel widgets, visible copy, keymaps, and config

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.4` · **Size:** medium
**Created:** 2026-09-25 00:06:05 EDT · **Closed:** 2026-09-25 03:04:22 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

copy: rename widgets/prompt_panel/_agent_display_family{,_render} and every family identifier, widget id, and CSS id in the ACE widgets. Change the visible copy from FAMILY SHELLS to SESSION SHELLS (including the "also listed under" and "see ... SHELLS" tails) and the identity header from FAMILY to SESSION, and rename FAMILY_IDENTITY_COLOR. Update the bindings.py and keymaps/metadata.py labels, the help_modal text, the "collapse family" command-palette alias, and the clipboard copy. Update the family wording in the default_config.yml comments and the sase.schema.json descriptions. Re-baseline, through /sase_monitor, only the PNG goldens whose pixels change because of the copy.

## Notes

[2026-09-25T06:53:54Z · sase-17m.5.1.4--1] PROPOSED FOLLOW-UP: `tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots` timed out waiting for the `agent-xprompt` section anchor in the initial capture and both serial recovery attempts; the anchor helper and detached-xprompt code are unchanged from the base tree, so this is outside the copy-only phase (visual run 9145426c3c614970a237fdbe8d04e83f).

[2026-09-25T07:03:56Z · sase-17m.5.1.4--2] PROPOSED FOLLOW-UP: `sase tool run check` fails only because `sase init memory --check` wants a +2/-2 update to `sase/memory/README.md`; all memory sources and init-memory implementation are unchanged from HEAD, and the standalone check reproduces it, so this is clean-base generated-documentation drift outside the copy-and-snapshot phase.

[2026-09-25T07:04:22Z · sase-17m.5.1.4--2] Verified `just fix`; the targeted `just fix-tui-screenshots` rebaseline completed successfully with 25 updated existing PNG goldens and no PNG creates, removals, or renames; inspected every old/new golden pair and confirmed FAMILY-to-SESSION session-copy-only pixel changes. `sase tool run check` passed formatting and all lint gates; its only failure is the separately recorded clean-base `init memory --check` README drift. Recorded the out-of-scope agent-xprompt anchor-timeout follow-up. `sase bead epic-symbols sase-17m.5.1.4` reported no entries.

## Dependencies

- **Depends on:** [sase-17m.5.1.3](sase-17m.5.1.3.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.5](sase-17m.5.1.5.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.4.md) | [sase-17m.5.1.4](sase-17m.5.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b79b9da`](https://github.com/sase-org/sase/commit/b79b9da246b434897fad03229097f76be34a7848) | feat(ace): rename family prompt panels to sessions | [sase-17m.5.1.4](sase-17m.5.1.4.md) | 2026-09-25 03:05:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.5.1.4--2][1] | Need the assigned phase scope and design evidence before final verification and closure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.5.1.4.md

<!-- sase:referenced-by:end -->
