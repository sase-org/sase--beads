# Bead: sase-1dr.2 — Prose-aware comparison engine in sase-core

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.2` · **Size:** medium
**Created:** 2026-09-30 19:09:18 EDT · **Closed:** 2026-09-30 20:09:03 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

prose-diff: add a pure sase-core `prose_diff` module and binding. Given two Markdown texts, it returns per-line change marks, reflow-insensitive word operations, hunks with heading paths, a bidirectional line map, a YAML-aware frontmatter delta, word stats, and unified diff text.

## Notes

[2026-10-01T00:06:25Z · sase-1dr.2] PROPOSED FOLLOW-UP: sase-core `just check` clippy gate fails on pre-existing nonminimal_bool lints in crates/sase_core/src/tool_run/store/triage.rs (untouched by this phase; reproduced on clean HEAD 5a59e78 worktree) — needs its own cleanup bead

[2026-10-01T00:09:03Z · sase-1dr.2] Implemented sase_core::prose_diff (compare_prose: frontmatter delta with type promotion, per-line marks + removal anchors, reflow-insensitive word ops, hunks with heading breadcrumbs, monotonic bidirectional line map, stats, unified diff) plus sase_core_py compare_prose/prose_diff_wire_schema_version bindings (GIL-releasing). Verified: 11 core tests + 3 binding tests pass, fmt clean, new code clippy-clean; full just check blocked only by pre-existing triage.rs clippy lints reproduced on clean HEAD (recorded as PROPOSED FOLLOW-UP). No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1dr.4](sase-1dr.4.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.2/README.md) | [sase-1dr.2](sase-1dr.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3b27df5`](https://github.com/sase-org/sase-core/commit/3b27df51a78b33be41429b0adb7ed869c05eb1fe) | feat(prose-diff): add pure sase-core prose\_diff module and Python binding | [sase-1dr.2](sase-1dr.2.md) | 2026-09-30 20:11:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dr.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.2/README.md

<!-- sase:referenced-by:end -->
