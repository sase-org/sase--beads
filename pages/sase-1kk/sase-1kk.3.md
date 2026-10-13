# Bead: sase-1kk.3 — sase-core bindings for the remaining Python artifact-index reads and alias writes

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.3` · **Size:** small
**Created:** 2026-10-13 12:24:28 EDT · **Closed:** 2026-10-13 13:21:43 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

core-index-readers: add read-only no-migrate schema-version and column-projection bindings plus alias upsert/delete/list bindings for agent_artifact_index.sqlite.

## Notes

[2026-10-13T17:21:28Z · sase-1kk.3] PROPOSED FOLLOW-UP: sase-core check hit known flake sase-17n — tool_run::store::tests::private_argv_is_not_serialized_on_queries failed under the full parallel lane (assert !encoded.contains("abc")) and passed when rerun alone; unrelated to artifact-index reader bindings.

[2026-10-13T17:21:43Z · sase-1kk.3] Added read-only no-migrate schema-version and column-projection APIs plus alias upsert/delete/list for agent_artifact_index.sqlite in sase-core, with PyO3 bindings. Core and binding tests cover stale schema (no migrate), missing meta (0), missing/unreadable files (None), rejected columns, catalog/provenance projections, and alias round-trips. sase tool run check failed only on known flake sase-17n (private_argv under parallel load); that test passed alone. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1kk.5](sase-1kk.5.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.3/README.md) | [sase-1kk.3](sase-1kk.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6306bd2`](https://github.com/sase-org/sase-core/commit/6306bd2bb6dfc2be595edaeb5e7c8663dcef59fa) | feat(agent-scan): add no-migrate index readers and alias bindings | [sase-1kk.3](sase-1kk.3.md) | 2026-10-13 13:23:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kk.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.3/README.md

<!-- sase:referenced-by:end -->
