# Bead: sase-1ez.3 — One live version per path or scope in the module snapshot caches

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.3` · **Size:** medium
**Created:** 2026-10-02 16:44:59 EDT · **Closed:** 2026-10-02 16:59:00 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

snapshot-caches: re-key the artifact-file index cache by resolved path, and the artifact-links and LinkIndex caches by project scope, so a changed stat or signature replaces the entry instead of piling up 32/64 superseded full copies. Add a just-check structural test (N external rewrites leave one entry per key) and audit the remaining token-keyed module caches.

## Notes

[2026-10-02T20:59:00Z · sase-1ez.3] Re-keyed all three snapshot caches to one live version per key: artifact-file index by resolved Path storing (stat, rows) with stat-equality gate; artifact-links by project-scope tuple storing (signature, snapshot) LRU8; LinkIndex by scope from source_key storing (source_key, index) LRU8, empty () handled. Stale/older-worker overwrites cost a reload, never serve mismatched data. Verified: 18 focused tests pass (relation bounds + storage), 73 artifact_links tests pass, ruff check/format clean, mypy clean on 3 source files, epic-symbols none. Audit: patch/cache, _json_cache, notification_store, artifact/glossary/memory_reads, _artifact_ref_completion_catalog, xprompt/save_index all path/scope-keyed with stored token (correct, no change); file_panel diff/linked_deltas TTL+capped (fine); _panel_artifact_cache LRU256 rare/small (fine); agent_tribe_evidence unbounded version-keyed but small/rare (follow-up candidate to re-key by paths).

## Dependencies

- **Blocks:** [sase-1ez.4](sase-1ez.4.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.3/README.md) | [sase-1ez.3](sase-1ez.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a6e90ea`](https://github.com/sase-org/sase/commit/a6e90ea76046f73458d52406194ce8029542372e) | fix(tui): re-key module snapshot caches to one live version per path or scope | [sase-1ez.3](sase-1ez.3.md) | 2026-10-02 17:01:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ez.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.3/README.md

<!-- sase:referenced-by:end -->
