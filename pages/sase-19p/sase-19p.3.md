# Bead: sase-19p.3 — CLOSED pill rendering, visibility guarantee, and goldens (TUI)

[Bead Pages](../README.md) / [sase-19p](README.md) / sase-19p.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s0.md) · **Assignee:** `sase-19p.3` · **Size:** medium
**Created:** 2026-09-25 14:05:32 EDT · **Closed:** 2026-09-25 20:53:02 EDT
**Plan:** [202609/agent\_closed\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_closed_beads.md)

## Description

render: paint agent-closed rows with a green check, a capped CLOSED pill, resolution and reopened-since states, closed-reason precedence, a lane-header closed count, and closure-first visible-row selection, then cover it with unit tests and new PNG goldens.

## Notes

[2026-09-26T00:52:39Z · sase-19p.3--1] PROPOSED FOLLOW-UP: just check SASE validation stage fails on clean base tree too (init memory --check wants sase/memory/README.md +2/-2 update); pre-existing, unrelated to this phase

[2026-09-26T00:53:02Z · sase-19p.3--1] Fixed mypy missing return annotation on _standing_close (-> BeadTouchClose | None) and made visible_bead_entries private (_visible_bead_entries, per symvision hierarchy: in-file use only) with test import updated. Verified: just _lint-symvision passes, mypy clean on touched file, 36 passed in test_agent_bead_touch_rows.py, 12 passed in test_bead_views + PNG snapshot suite. Full check: all fmt/lint stages green incl. mypy+symvision; only SASE validation init-memory README failure remains, which reproduces identically on clean base tree (recorded as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-19p.2](sase-19p.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19p.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.3.md) | [sase-19p.3](sase-19p.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7211290`](https://github.com/sase-org/sase/commit/72112905707800b3f51068d66edda19323d359ba) | feat(ace): add agent bead touches panel and sase context snapshots | [sase-19p.3](sase-19p.3.md) | 2026-09-25 20:55:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19p.3--1][1] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.3.md

<!-- sase:referenced-by:end -->
