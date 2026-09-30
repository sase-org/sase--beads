# Bead: sase-1d7.4 — Roster generation counter and cached projection index

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.4` · **Size:** medium
**Created:** 2026-09-30 07:18:10 EDT · **Closed:** 2026-09-30 10:08:48 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

roster-generation: introduce one app-wide roster generation bumped on every roster assignment and in-place status mutation, cache agent_node_projection_index per generation, and remove its quadratic dedupe.

## Notes

[2026-09-30T14:08:17Z · sase-1d7.4--1] PROPOSED FOLLOW-UP: just check _setup fails on clean base tree too — validate_sase_core_rs prompt-prediction probe expects confident=True/ghost=[the] but installed sase_core_rs 0.36.0 returns confident=False/ghost=[]; sase-core checkout fast-forwarded to origin/master ahead of pyproject window, test selection escalates to FULL_SUITE via core-identity-changed

[2026-09-30T14:08:48Z · sase-1d7.4--1] roster-generation done: app-wide generation + cached projection index + O(1) dedupe; verified 26 passed (roster_generation+agent_nodes), 76 passed (incl unread projection/toggle), mypy clean 5339 files, ruff/fmt clean; just check _setup Rust prompt-prediction probe fails identically on clean base tree (pre-existing infra, recorded as follow-up)

## Dependencies

- **Blocks:** [sase-1d7.10](sase-1d7.10.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.11](sase-1d7.11.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.3](sase-1d7.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.9](sase-1d7.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.4.md) | [sase-1d7.4](sase-1d7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8a00076`](https://github.com/sase-org/sase/commit/8a00076f1ffa374e9d604ea9f66a4b1881906843) | feat(agents): add roster generation counter and cached projection index | [sase-1d7.4](sase-1d7.4.md) | 2026-09-30 10:12:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.10][1] | Need roster generation design to build on | 1 |
| read-by | [agent:sase-1d7.4--1][2] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.10/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.4.md

<!-- sase:referenced-by:end -->
