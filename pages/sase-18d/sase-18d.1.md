# Bead: sase-18d.1 — Rust cleanup wire for live runners and atomic dismissed index

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.1` · **Size:** medium
**Created:** 2026-09-24 16:28:30 EDT · **Closed:** 2026-09-24 17:23:09 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

core-wire: in sase-core, add runner_is_live to the cleanup target wire (schema 5) so a FAILED row with a live runner becomes a kill item. Add an atomic, locked, merge-on-write dismissed-index update API. Then update the Python wire, the reference planner, the target projection, and the sase-core revision pin in the same change.

## Notes

[2026-09-24T21:22:37Z · sase-18d.1] PROPOSED FOLLOW-UP: land the linked sase-core core-wire change (uncommitted in the linked checkout) then move sase-core-revision.txt past that commit — pin left at 6d0d0e6 so CI keeps building schema-4 core until then

[2026-09-24T21:23:09Z · sase-18d.1] core-wire done: schema-5 runner_is_live kill rule in Rust planner + Python mirror with parity tests; atomic locked dismissed-index update API with binding, add/remove wrappers; sase-core check green except unrelated gateway load flake (passes alone); sase focused/related suites green (73+281+17); ruff/keep-sorted clean, mypy+symvision findings all pre-existing in untouched files; pin move deferred to land agent per bead note

## Dependencies

- **Blocks:** [sase-18d.5](sase-18d.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.1/README.md) | [sase-18d.1](sase-18d.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e3f3a4b`](https://github.com/sase-org/sase/commit/e3f3a4bd4010d3ca892d9b2e7c49dec19e77e3ff) | feat(cleanup): carry runner\_is\_live on wire v5 with FAILED+live kill rule | [sase-18d.1](sase-18d.1.md) | 2026-09-24 17:25:12 EDT |
| sase-core | [`sase-core@f226caf`](https://github.com/sase-org/sase-core/commit/f226caf0ba4b61648d3968ef6278793c7636deae) | feat(cleanup): add runner\_is\_live to cleanup target wire (schema 4-\>5) | [sase-18d.1](sase-18d.1.md) | 2026-09-24 17:28:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18d.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.1/README.md

<!-- sase:referenced-by:end -->
