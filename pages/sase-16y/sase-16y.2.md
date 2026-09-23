# Bead: sase-16y.2 — Dot jump-panel toggle plumbing and the non-run toggle move

[Bead Pages](../README.md) / [sase-16y](README.md) / sase-16y.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q0.md) · **Assignee:** `sase-16y.2` · **Size:** small
**Created:** 2026-09-23 10:49:55 EDT · **Closed:** 2026-09-23 11:35:39 EDT
**Plan:** [202609/agent\_jump\_footer\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_jump_footer_panel.md)

## Description

keymap: add the inert Agents-only toggle_agent_jump_panel action on full_stop, move the Agents show/hide non-run agents toggle to a new toggle_hide_non_run_agents action on I, narrow toggle_hide_reverted to Services, and update availability, registry pairs, palette, help, docs, and keymap tests.

## Notes

[2026-09-23T15:35:39Z · sase-16y.2] Keymap phase done: toggle_agent_jump_panel on '.' (Agents-only, inert via getattr until panel lands), non-run toggle moved to toggle_hide_non_run_agents on 'I', toggle_hide_reverted narrowed to Services; availability/registry/palette/help/docs/tests updated. Verified: 197 targeted tests pass; fmt/ruff/mypy/flags/waits/toobig green; epic-symbols clean; scoped suite 45k+ pass with only pre-existing unrelated failures (bead/prompt-history/query-profile flakes, none touching new symbols); pyscripts+symvision red only on pre-existing untouched files.

## Dependencies

- **Blocks:** [sase-16y.3](sase-16y.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16y.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.2/README.md) | [sase-16y.2](sase-16y.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3408056`](https://github.com/sase-org/sase/commit/34080568e6e9e91376eed89906eae3d99f24dd7b) | feat(ace): add Agents jump-panel keymap phase with non-run toggle | [sase-16y.2](sase-16y.2.md) | 2026-09-23 11:37:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16y.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.2/README.md

<!-- sase:referenced-by:end -->
