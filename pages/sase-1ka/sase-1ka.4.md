# Bead: sase-1ka.4 — Inbox gate card reuses the collapsed card

[Bead Pages](../README.md) / [sase-1ka](README.md) / sase-1ka.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4a.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4a.linker.w0.md) · **Assignee:** `sase-1ka.4` · **Size:** small
**Created:** 2026-10-12 09:11:09 EDT · **Closed:** 2026-10-12 10:31:20 EDT
**Plan:** [202610/gate\_panel\_decision\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202610/gate_panel_decision_cards.md)

## Description

inbox: render the notification inbox plan-gate Decisions block with the read-only collapsed card builder (name left, answer chip right, dim question line, width-1 toggle glyphs) and regenerate its two goldens.

## Notes

[2026-10-12T14:31:12Z · sase-1ka.4] PROPOSED FOLLOW-UP: Resolve the pre-existing KNOWN Symvision private import of _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py (witness 0d0e7cc8a4cdd11885a1c3a085839d9; also noted on sase-1ka.5). This is outside the inbox phase; no task bead currently tracks it.

[2026-10-12T14:31:20Z · sase-1ka.4] Reused the collapsed decision-card builder in the read-only inbox block; pending/answered visual tests pass and both goldens are updated and clean under local TZ and TZ=UTC. Focused inbox tests pass; sase tool run check reported no new failures (one pre-existing KNOWN Symvision issue recorded as a proposed follow-up). epic-symbols had no leftovers.

## Dependencies

- **Depends on:** [sase-1ka.1](sase-1ka.1.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ka.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ka.4/README.md) | [sase-1ka.4](sase-1ka.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a93229e`](https://github.com/sase-org/sase/commit/a93229e65d9adaf06cd4689c5c70b0fa9701a504) | feat(ace): reuse decision cards in inbox gates | [sase-1ka.4](sase-1ka.4.md) | 2026-10-12 10:32:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ka.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ka.4/README.md

<!-- sase:referenced-by:end -->
