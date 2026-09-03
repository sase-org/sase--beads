# Bead: sase-w2.4 — Evidence-backed v1-to-v2 adoption unwedges blocked machines

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.4` · **Size:** large
**Created:** 2026-09-03 12:32:00 EDT · **Closed:** 2026-09-03 17:31:22 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

v2-adoption: let v2 claims supersede matching legacy v1 registry state, refresh matched v1 artifacts in place with full v2 data, repair forged local-ownership rows, preserve dismissed state, and add a dry-run-first forget-import fallback command.

## Notes

[2026-09-03T20:00:26Z · sase-w2.4] PROPOSED FOLLOW-UP: v1-to-v2 adoption leaves orphaned v1 chat files — when an adopted run has its own v2 chat, the old ~/chats/<shard>/imported-<name>-<ts>.md copy stays on disk unreferenced (338 files on the observed wedged machine); a sweep should reclaim chat files whose only referrer was a v1 agent_meta.json that adoption rewrote.

[2026-09-03T20:01:27Z · sase-w2.4] PROPOSED FOLLOW-UP: duplicate source-run-id derivation — src/sase/agents_sync/v2_import_history.py::_source_run_id is a byte-identical copy of src/sase/agents_sync/inventory_io.py::source_run_id; the two must never drift because v1-to-v2 adoption matching depends on the destination recomputing exactly what the source published. Collapse to one implementation.

[2026-09-03T20:02:39Z · sase-w2.4] PROPOSED FOLLOW-UP: no serialized count for adopted hoods — v1-to-v2 adoption is reported only through hoods_refreshed plus a free-text diagnostic because adding a field to IntegrationCounts/CachedIntegrationResult would bump the incoming-cache wire schema. Once the migration telemetry matters, add an explicit adopted count with the schema bump.

[2026-09-03T21:31:22Z · sase-w2.4] Auto-closed by `sase stitch create` after create_commit landed bdd2eadcf ("feat(agents-sync): evidence-backed v1-to-v2 adoption unwedges blocked machines"). No verification is implied by this note. Reopen with `sase bead open sase-w2.4`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-w2.3](sase-w2.3.md) ✓ · ⧖ 2026-09-03
- **Blocks:** [sase-w2.5](sase-w2.5.md) ✓ · ⧖ 2026-09-03
- **Blocks:** [sase-w2.7](sase-w2.7.md) ◐ · ⧖ 2026-09-03
- **Blocks:** [sase-w2.8](sase-w2.8.md) ◐ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w2.4.md) | [sase-w2.4](sase-w2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bdd2ead`](https://github.com/sase-org/sase/commit/bdd2eadcf65b84d467ce26cfae34f11f2fb67fee) | feat(agents-sync): evidence-backed v1-to-v2 adoption unwedges blocked machines | [sase-w2.4](sase-w2.4.md) | 2026-09-03 17:30:08 EDT |
