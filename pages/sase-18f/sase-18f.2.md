# Bead: sase-18f.2 — Split the two oversized ACE modules

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.2` · **Size:** medium
**Created:** 2026-09-24 17:18:54 EDT · **Closed:** 2026-09-24 19:44:14 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

toobig-splits: split command_line/screen.py and widgets/decks/panel.py under the toobig limit with purely mechanical moves. Import no `_private` names across modules, keep the public import paths stable, and keep symvision and mypy green.

## Notes

[2026-09-24T23:22:38Z · sase-18f.2] PROPOSED FOLLOW-UP: just _lint-toobig remains red because unchanged tests/tool/test_settlement.py is 1048 lines on HEAD; split it under the owning follow-up work.

[2026-09-24T23:39:14Z · sase-18f.2] PROPOSED FOLLOW-UP: just _lint-symvision is master-red on unchanged HEAD due to unused AgentSurvivorsError/Survivor in actions/agents/_kill_termination.py and environ_has_launch_key in agent/process_tree.py; resolve under the owning lint follow-up.

[2026-09-24T23:44:14Z · sase-18f.2] Split command-line behavior into submission, navigation, and completion mixins and deck Files behavior into a mixin; public screen/panel imports and test seams remain stable. Verified 265 command-line/deck tests, ruff, mypy, source toobig, and wrapped check through its clean-base Symvision blocker.

## Dependencies

- **Depends on:** [sase-18f.1](sase-18f.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.4](sase-18f.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.2/README.md) | [sase-18f.2](sase-18f.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b18f3d3`](https://github.com/sase-org/sase/commit/b18f3d38f28a132de174cbf1e8ad3939e2b4372a) | refactor(ace): split oversized command and deck panels | [sase-18f.2](sase-18f.2.md) | 2026-09-24 19:45:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.2/README.md

<!-- sase:referenced-by:end -->
