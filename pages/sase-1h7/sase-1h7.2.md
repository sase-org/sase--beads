# Bead: sase-1h7.2 — Derive produced-by links from recorded epics

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.2` · **Size:** small
**Created:** 2026-10-06 18:17:35 EDT · **Closed:** 2026-10-06 21:53:06 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

links: publish portable `created_epic_ids` and project `bead:<epic> produced-by agent:<creator>` edges, both from published metadata and from bead-store attribution, so unpublished planners also get the edge. Widen the relation guidance in sase-core.

## Notes

[2026-10-07T01:52:36Z · sase-1h7.2] PROPOSED FOLLOW-UP: just check lint (symvision) fails on clean tree: _runs privately imported in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py (verified identical with changes stashed; no tracking bead found)

[2026-10-07T01:52:48Z · sase-1h7.2] PROPOSED FOLLOW-UP: sase-core check fmt-check fails on clean tree: crates/sase_core/src/bead/fingerprint.rs and crates/sase_core_py/src/beads/fingerprint.rs need rustfmt single-line asserts under current toolchain (files at HEAD, untouched by links phase)

[2026-10-07T01:53:06Z · sase-1h7.2] links phase done and verified: portable created_epic_ids published (validation+inventory_io, 5 new tests green); agent-created-epic + agent-created-epic-attributed rules registered in _entry with bead_store_root on ProjectionInputs (9 new projection tests green, incl. worker-keeps-implements and older-publisher-silent); produced-by guidance widened to bead sources in sase-core relation.rs (+new rust test, 106 artifact_link tests green), Python fallback, artifact_relations.json, docs/artifact_links.md. ruff/mypy/fmt gates pass. Two pre-existing failures recorded as PROPOSED FOLLOW-UPs (symvision _runs imports; sase-core fingerprint fmt drift), both proven identical on clean tree. sase-core edit left uncommitted in linked checkout for host finalizer; pin not moved (no new binding, core commit not yet landed).

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.10](sase-1h7.10.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.2/README.md) | [sase-1h7.2](sase-1h7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f4be6ce`](https://github.com/sase-org/sase-core/commit/f4be6cee136df4258e54af1ede98ac82e5a776a1) | feat(artifact-link): widen produced-by guidance to bead sources | [sase-1h7.2](sase-1h7.2.md) | 2026-10-06 21:55:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h7.2/README.md

<!-- sase:referenced-by:end -->
