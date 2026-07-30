# Bead: sase-ba.3 — Dry-run-first pruning and the trash lifecycle

[Bead Pages](../README.md) / [sase-ba](README.md) / sase-ba.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ba.3` · **Size:** medium
**Created:** 2026-07-30 14:40:18 UTC · **Closed:** 2026-07-30 16:42:07 UTC
**Plan:** [202607/artifact\_store\_lifecycle.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_store_lifecycle.md)

## Description

py-prune: add `sase artifact prune` (dry run unless `--apply`) and the `sase artifact trash {list,purge,restore}` group, with index-row removal and restoration performed under the existing index lock and every removal routed through the trash.

## Notes

[2026-07-30T16:42:07Z · sase-ba.3] Implemented dry-run-first artifact pruning plus trash list/purge/restore with lock-coordinated index removal/restoration and fail-safe protection scanning. Verified 24,368 tests passed (7 skipped); Ruff, mypy, Symvision, toobig, formatting, and changelog gates passed; scratch CLI apply/list/restore/purge round-trip passed; unavailable protection sources blocked apply; real-store read-only prune projected 2,852 rows / 379,383,155 bytes, trash was empty, and artifact doctor was healthy. Full just check reached repository validation but remains blocked by pre-existing stale deployed skill copies and plan/prompt backlink errors spanning three epics.

[2026-07-30T16:43:15Z · sase-ba.3] Finalizer verification: implementation files are present; 24,368 tests passed with 7 skipped; lifecycle scratch round-trip and real-store read-only checks passed.

## Dependencies

- **Depends on:** [sase-ba.2](sase-ba.2.md) ✓
- **Blocks:** [sase-ba.4](sase-ba.4.md) ◐
- **Blocks:** [sase-ba.5](sase-ba.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ba.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ba.3/README.md) | [sase-ba.3](sase-ba.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`be4c199`](https://github.com/sase-org/sase/commit/be4c19969fc6ce227ee4e474d9952722ea172b02) | feat(artifact): add pruning and trash lifecycle | [sase-ba.3](sase-ba.3.md) | 2026-07-30 16:43:50 |
