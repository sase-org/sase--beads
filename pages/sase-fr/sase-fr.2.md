# Bead: sase-fr.2 — Adopt the release and carry close history through Python storage

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.2` · **Size:** medium
**Created:** 2026-08-05 21:18:38 EDT · **Closed:** 2026-08-05 22:34:39 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

core-adopt: raise the sase-core-rs window to the release from core-model and thread close_history through the Python model, wire conversion, issues.jsonl, the SQLite mirror with its migration, and the projection repair guard.

## Notes

[2026-08-06T02:34:25Z · sase-fr.2] PROPOSED FOLLOW-UP: raise sase-core-rs floor once close_history ships — sase-core PR #86 (close_history reducer) is unmerged, so no release carries it; the window stays >=0.18.1,<0.19.0 and must be bumped after the release cuts.

[2026-08-06T02:34:39Z · sase-fr.2] Threaded close_history through the Python storage stack: ReopenCause enum + frozen CloseRecord with validate() in model.py, shared wire codec in close_history_codec.py, conversion in core/bead_wire.py, issues.jsonl round-trip, SQLite column + _migrate_add_close_history + insert/select/update lists, and work.py/cli_admin.py allowed_fields. Added 25 storage tests plus an end-to-end test through BeadProject; verified end-to-end against a wheel built from sase-core PR #86 (66011f5) then restored the pinned 0.18.1 build. just lint clean; tests/test_bead 1388 passed/1 skipped and tests/test_core_facade 166 passed. The sase-core-rs window bump is blocked (PR #86 unmerged, no release carries close_history) and recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-fr.1](sase-fr.1.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.3](sase-fr.3.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.2/README.md) | [sase-fr.2](sase-fr.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1da5a3e`](https://github.com/sase-org/sase/commit/1da5a3e277326bf52cf79c72c1ec824cbdc2e02b) | feat(bead): carry close history through Python bead storage | [sase-fr.2](sase-fr.2.md) | 2026-08-05 22:35:14 EDT |
