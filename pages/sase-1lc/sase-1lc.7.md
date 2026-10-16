# Bead: sase-1lc.7 — Live verification, golden sweep, and glossary

[Bead Pages](../README.md) / [sase-1lc](README.md) / sase-1lc.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4j.linker.w0.md) · **Assignee:** `sase-1lc.7` · **Size:** small
**Created:** 2026-10-15 15:02:49 EDT · **Closed:** 2026-10-15 22:45:44 EDT
**Plan:** [202610/clan\_waves\_in\_agents\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202610/clan_waves_in_agents_tab.md)

## Description

verify: review live screenshots of real clans, run the full visual golden sweep and perf checks, fix polish issues, apply the glossary decisions, and record v2 follow-ups.

## Notes

[2026-10-16T02:44:53Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Add a dependency-cone highlight for the selected member, showing WAITS ON and BLOCKS in the clan view.

[2026-10-16T02:44:58Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Compact the completed prefix in very long clan dependency chains.

[2026-10-16T02:45:03Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Explore a Gantt card for clan wave timing.

[2026-10-16T02:45:08Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Support optional producer stage labels in the clan wave UI.

[2026-10-16T02:45:12Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Expose derived wave information in `sase agent show`.

[2026-10-16T02:45:17Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Add clan wave fields to the editor integration at `src/sase/integrations/_agent_list_entry_build.py`.

[2026-10-16T02:45:22Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Show epic phase titles in the WAVES ladder using the associated-plan worker cache.

[2026-10-16T02:45:27Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Add wave gutters in rail density.

[2026-10-16T02:45:32Z · sase-1lc.7--1] PROPOSED FOLLOW-UP: Reconcile `tools/render_docs --format-only` and Prettier formatting for generated Markdown; `sase tool run check` currently cannot pass both generated-doc and Markdown formatting gates.

[2026-10-16T02:45:44Z · sase-1lc.7--1] Verified full screenshot sweep: 1,370 passed, one parallel capture failed but passed serial recovery, 72 verification snapshots passed; reviewed 96 updated goldens and the five ignored unexpected candidates. Real Agents screenshot showed live epic/research clan waves; traced session had 43 refresh records and zero clan_member_order_change fallbacks. Clan J/K benchmark passed at all fold levels (p95 10.69–13.97 ms). sase tool run check was attempted twice and stopped at existing generated Markdown formatter drift; follow-ups recorded, including the formatter mismatch and all v2 candidates.

## Dependencies

- **Depends on:** [sase-1lc.6](sase-1lc.6.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lc.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.7.md) | [sase-1lc.7](sase-1lc.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e1edb8`](https://github.com/sase-org/sase/commit/7e1edb8d76b753f98d9f2a31fd0d1eb8b82a3136) | feat(ace): finish clan wave verification | [sase-1lc.7](sase-1lc.7.md) | 2026-10-15 22:46:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lc.7--1][1] | Review prior phase notes and remaining work before finishing verification | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.7.md

<!-- sase:referenced-by:end -->
