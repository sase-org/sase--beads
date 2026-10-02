# Bead: sase-1ez.5 — Share immutable cached snapshots instead of copying them on every hit

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.5` · **Size:** medium
**Created:** 2026-10-02 16:45:03 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

cached-snapshot-sharing: stop the notification facade deep-cloning about 1.6k rows on every cache hit. Make shared rows safe through immutability or audited copy-on-write callers. Return the cached frozenset of dismissed bundle identities and the cached artifact-index tuple instead of fresh copies, with guard tests that caller mutation cannot corrupt a cache.

## Dependencies

- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.5/README.md) | [sase-1ez.5](sase-1ez.5.md) | 0 |
