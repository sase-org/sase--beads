# Bead: sase-16t.1 — Wildcard matching in the sase-core query evaluator

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.1` · **Size:** small
**Created:** 2026-09-23 08:23:30 EDT · **Closed:** 2026-09-23 08:40:17 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

core-glob: in the linked sase-core repo, make `*` a wildcard inside string-field property values (anchored for exact-match fields and `sha`, unanchored for substring fields, literal for enums), with Rust tests proving `id:alpha-1.*` semantics and byte-identical behavior for values without `*`.

## Notes

[2026-09-23T12:39:44Z · sase-16t.1] PROPOSED FOLLOW-UP: sase-core provider_priority concurrent_priority_changes_and_auto_disables_are_serialized flakes under full check lane (LockTimeout), passes alone — needs a flake bead

[2026-09-23T12:40:17Z · sase-16t.1] core-glob done in sase-core: anchored * globs for exact-match fields and sha, unanchored for substring fields, literal for enums, values without * on historical path; boolean tokenizer accepts * in property values. 5 new Rust tests (flat+boolean id:alpha-1.* semantics, sha:ab*12, enum literal, no-* regression) pass; sase tool run check green (one unrelated provider_priority lock-timeout flake passed alone, noted as follow-up). epic-symbols clean.

## Dependencies

- **Blocks:** [sase-16t.2](sase-16t.2.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.1/README.md) | [sase-16t.1](sase-16t.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4af70ce`](https://github.com/sase-org/sase-core/commit/4af70ce1e84b39ed6f4dd503a2bd6515f55d6aed) | feat(query): support \* wildcards in string property values | [sase-16t.1](sase-16t.1.md) | 2026-09-23 08:42:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16t.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-16t.2][2] | check core-glob status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.2/README.md

<!-- sase:referenced-by:end -->
