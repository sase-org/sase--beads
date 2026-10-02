# Bead: sase-1ez.5 — Share immutable cached snapshots instead of copying them on every hit

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.5` · **Size:** medium
**Created:** 2026-10-02 16:45:03 EDT · **Closed:** 2026-10-02 17:15:49 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

cached-snapshot-sharing: stop the notification facade deep-cloning about 1.6k rows on every cache hit. Make shared rows safe through immutability or audited copy-on-write callers. Return the cached frozenset of dismissed bundle identities and the cached artifact-index tuple instead of fresh copies, with guard tests that caller mutation cannot corrupt a cache.

## Notes

[2026-10-02T21:15:49Z · sase-1ez.5] cached-snapshot-sharing done. Facade _read_snapshot_cached returns fresh outer lists sharing cached Notification rows (no per-row deep clone); token race guard kept. Modal owns its rows via replace() at intake (NotificationModal init + undismiss provider reload) so in-place optimistic updates can't reach the cache; app-level _remove_agent_completion_notifications_from_cache audited (outer-list slice-assign only, safe). dismissed_bundle_identities_snapshot returns the cached frozenset; bundle-identities channel widened to AbstractSet, 3 set() per-load copies removed. read_artifact_file_index returns the cached tuple (frozen rows); annotation honest. Guard tests: shared row identity + outer-list mutation isolation (facade), frozenset identity + AttributeError on mutation (dismissed), tuple identity + AttributeError on append (artifact), modal intake-copy test. Verified: 569 passed across facade/notification/artifact/dismissed/modal/loader suites; ruff check+format clean; mypy clean (5477 files); symvision lane clean. No epic-symbol entries left.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.5/README.md) | [sase-1ez.5](sase-1ez.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2eed4bd`](https://github.com/sase-org/sase/commit/2eed4bdcb5947a2cd96c30031ff22e5b53b57a77) | feat(tui): share immutable cached snapshots instead of copying on every hit | [sase-1ez.5](sase-1ez.5.md) | 2026-10-02 17:38:18 EDT |
