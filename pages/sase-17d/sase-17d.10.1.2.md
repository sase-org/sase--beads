# Bead: sase-17d.10.1.2 — Delete the legacy detail UI and retire its keymap ids

[Bead Pages](../README.md) / [sase-17d.10.1](sase-17d.10.1.md) / sase-17d.10.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.md) · **Assignee:** `sase-17d.10.1.2` · **Size:** large
**Created:** 2026-09-24 10:13:46 EDT
**Plan:** [202609/deck\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_cutover.md)

## Description

legacy-ui-deletion: delete the p picker, the view modal, the zoom modal and its seed and CSS, the panel/layout enums and cycle, the hidden compat host ids and legacy CSS, the view chip, the section-stop actions and the redirect handlers. Retire choose_agent_view and the section-stop ids, rename next/prev_agent_file to next/prev_chop_run with aliases, and delete or migrate the tests of the deleted code, including visual test modules.

## Notes

[2026-09-24T17:24:34Z · 0qz--code] symvision_green_master sweep: slow_tool_overflow_hint is now _slow_tool_overflow_hint (prompt_panel/_agent_slow_tools.py) and NodeSpineExpandRequested is now NodeSpine.ExpandRequested (handler stays on_node_spine_expand_requested). Rebase carefully; it edits the hint list.

## Dependencies

- **Depends on:** [sase-17d.10.1.1](sase-17d.10.1.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17d.10.1.3](sase-17d.10.1.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.10.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17d.10.1.2.md) | [sase-17d.10.1.2](sase-17d.10.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`742c1df`](https://github.com/sase-org/sase/commit/742c1df38b04d1b190a5102168f0cf2ab37e6840) | feat(ace): remove legacy agents UI | [sase-17d.10.1.2](sase-17d.10.1.2.md) | 2026-09-24 14:37:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0qz--code][1] | check open before noting symvision renames | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qz.md

<!-- sase:referenced-by:end -->
