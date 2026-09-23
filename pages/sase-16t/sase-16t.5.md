# Bead: sase-16t.5 — Agent and File context queries plus Agents-tab reveal

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.5` · **Size:** medium
**Created:** 2026-09-23 08:23:35 EDT · **Closed:** 2026-09-23 12:24:22 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

flat-panes: add hood/family context queries for the Artifacts Agent pane and creating-agent context for Files, and make `agent:` jumps reveal folded rows on the Agents tab, falling back to Artifacts ▸ Agent when the Agents-tab filter hides them.

## Notes

[2026-09-23T16:23:38Z · sase-16t.5] PROPOSED FOLLOW-UP: just check symvision flags ExpandedLaunchSegments in src/sase/agent/launch_cwd_segments.py as unused-public on clean master (proven via stash); unrelated to sase-16t.5, blocks every lane

[2026-09-23T16:24:22Z · sase-16t.5] flat-panes done: Agents hood/family + Files creating-agent host_reveal_context with member_count limits; _follow_loaded_agent searches full set via prepare/reveal with TARGET_FILTERED fallthrough flag threaded to RevealOutcome; 11 new tests (3 real-pane AcePage incl. limit raise and ^ restore, 5 pure context cases, folded-in-place + filtered-flag harness, fallback-to-outcome) plus adjacent suites (link_follow, planner, seam, ladder, hydration, member_jump, agents/files panes) all green; ruff+mypy clean, just check red only on pre-existing symvision ExpandedLaunchSegments item (noted as follow-up)

## Dependencies

- **Depends on:** [sase-16t.4](sase-16t.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16t.8](sase-16t.8.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.5/README.md) | [sase-16t.5](sase-16t.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`60b236b`](https://github.com/sase-org/sase/commit/60b236b5b3d5ed591d986410da68cc6351ffc4ac) | feat(ace): agent and file context queries plus Agents-tab reveal | [sase-16t.5](sase-16t.5.md) | 2026-09-23 12:26:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16t.5][1] | check close status for finalizer | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.5/README.md

<!-- sase:referenced-by:end -->
