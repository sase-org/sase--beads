# Bead: sase-15b.6 — Split crates/sase\_core/src/tool\_run/store.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.6` · **Size:** medium
**Created:** 2026-09-21 11:31:45 EDT · **Closed:** 2026-09-21 16:19:15 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

tool_run_store: decompose the 3,229-line SQLite tool-run store into connection/schema, run lifecycle, query, and retention submodules under tool_run/store/.

## Notes

[2026-09-21T20:19:15Z · sase-15b.6] Split tool_run/store.rs (3,229 lines) into store/ tree: connection.rs 407, lifecycle.rs 797, query.rs 519, retention.rs 468, tests.rs 1085, mod.rs 19. All 20 store tests pass (30/30 with tool_run siblings); just check green; no file over 1500 lines; public API unchanged via mod.rs re-exports

## Dependencies

- **Depends on:** [sase-15b.5](sase-15b.5.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-15b.7](sase-15b.7.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.6/README.md) | [sase-15b.6](sase-15b.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b7af6b7`](https://github.com/sase-org/sase-core/commit/b7af6b7ce58a0888253e1f8223f2e502512d33bb) | refactor(sase-core): split tool\_run store into connection, lifecycle, query, retention modules | [sase-15b.6](sase-15b.6.md) | 2026-09-21 16:21:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability (split epic phase evidence) | 1 |
| read-by | [agent:sase-15b.6][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.6/README.md

<!-- sase:referenced-by:end -->
