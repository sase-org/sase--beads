# Bead: sase-16n.6 — Tag rendering in the agent panel and prompt editor

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.6` · **Size:** medium
**Created:** 2026-09-22 18:48:50 EDT · **Closed:** 2026-09-23 07:03:56 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

tag-display: the humanizer renders project refs as tags; the shared tokenizer emits project_tag spans; accent styles in both highlight systems; the prompt editor, the AGENT XPROMPT sections (main, family, hint, and clan), and their visual snapshots.

## Notes

[2026-09-23T02:40:12Z · sase-16n.6] PROPOSED FOLLOW-UP: PNG golden coverage for tag rendering (prompt-highlighting tag fixture + agents_xprompt tag case) needs a fix-tui-screenshots capture run with report inspection

[2026-09-23T02:40:40Z · sase-16n.6] PROPOSED FOLLOW-UP: symvision flags delete_paths_in_background in src/sase/_linked_repo_workspaces.py as unused-public (pre-existing at HEAD, in-file use only)

## Dependencies

- **Depends on:** [sase-16n.5](sase-16n.5.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.7](sase-16n.7.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.9](sase-16n.9.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.6/README.md) | [sase-16n.6](sase-16n.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eea59a6`](https://github.com/sase-org/sase/commit/eea59a65147a1dcd2d3ae7d91e818e3c463227ec) | feat(xprompt): render project tags in agent panel and prompt editor | [sase-16n.6](sase-16n.6.md) | 2026-09-22 22:43:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.6/README.md

<!-- sase:referenced-by:end -->
