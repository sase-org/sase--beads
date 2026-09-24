# Bead: sase-17o.1 — Awaits relation in the sase-core registry

[Bead Pages](../README.md) / [sase-17o](README.md) / sase-17o.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qk.md) · **Assignee:** `sase-17o.1` · **Size:** small
**Created:** 2026-09-24 08:23:08 EDT · **Closed:** 2026-09-24 08:32:35 EDT
**Plan:** [202609/agent\_wait\_bead\_links.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_wait_bead_links.md)

## Description

core-relation: in the linked sase-core repo, add the projection-only `awaits` / `awaited-by` builtin relation to the artifact-link registry, with Rust tests.

## Notes

[2026-09-24T12:32:35Z · sase-17o.1] Added projection-only awaits/awaited-by builtin to sase-core registry with Rust tests (builtins_cover_v1_table + new awaits_is_a_projection_only_agent_to_bead_relation). Focused relation tests 8/8 pass; full sase tool run check gate green (192s). No schema bump per produced-by/launched precedent.

## Dependencies

- **Blocks:** [sase-17o.2](sase-17o.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17o.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17o.1/README.md) | [sase-17o.1](sase-17o.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@eef7ca4`](https://github.com/sase-org/sase-core/commit/eef7ca415c763e8ba7c7b3040b50cee5d08c7539) | feat(artifact-links): add projection-only awaits/awaited-by relation | [sase-17o.1](sase-17o.1.md) | 2026-09-24 08:33:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17o.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17o.1/README.md

<!-- sase:referenced-by:end -->
