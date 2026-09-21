# Bead: sase-15b.8 — Split crates/sase\_core/src/editor/directive.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.8` · **Size:** medium
**Created:** 2026-09-21 11:31:48 EDT · **Closed:** 2026-09-21 17:19:42 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

editor_directive: decompose the 2,952-line editor directive module into metadata tables, contract lookup, completion candidates, and context detection submodules under editor/directive/.

## Notes

[2026-09-21T21:19:42Z · sase-15b.8] Split editor/directive.rs (2952 lines) into editor/directive/ tree: metadata.rs 791, candidate_lists.rs 371, context.rs 481, contract.rs 212, tests.rs 1103, mod.rs 30 — all <=1500, verbatim moves, no public API change. 29/29 directive tests pass (matches baseline); just check green (fmt, clippy, all workspace tests incl. 56 sase_core_py tests). No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-15b.7](sase-15b.7.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-15b.9](sase-15b.9.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.8/README.md) | [sase-15b.8](sase-15b.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@59327d6`](https://github.com/sase-org/sase-core/commit/59327d62c18b61c8680d367e69ab58c6f1c296f9) | refactor(sase-core): split editor directive into metadata, contract, candidate, context modules | [sase-15b.8](sase-15b.8.md) | 2026-09-21 17:21:30 EDT |
