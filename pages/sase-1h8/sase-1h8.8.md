# Bead: sase-1h8.8 — Read-model substrate, freshness protocol, and parity harness

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.8` · **Size:** medium
**Created:** 2026-10-06 18:59:39 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

read-model-store: add the versioned SQLite read model under the clone's git dir with an O(1) freshness token, full-rebuild fallback, transparent read integration, doctor --verify-cache, and a cache-vs-replay parity harness.

## Notes

[2026-10-07T02:50:52Z · sase-1h8.8] read-model-store landed: versioned SQLite read model under <git-dir>/sase/bead-read-model/<key>.sqlite (WAL) with O(1) freshness token (streams-dir mtime+inode + manifest/config sigs), full-sweep confirm, full-rebuild fallback with generation CAS, fail-open transparent integration in read_store_issues + show_issue_detail_with_options, doctor --verify-cache (-C) + cache status line, parity harness (replay-vs-cache + 30-step randomized mutation test + bench-corpus probes)

[2026-10-07T02:51:09Z · sase-1h8.8] Measurements (sase-core debug build, bench corpus 6899 beads/2000 streams/44735 events at 1x; 8x via prefix-copy: 55192 beads/16000 streams): 1x replay 1574ms (cold page cache) / cold rebuild 273ms / warm token-only reads ~250-279ms / cache 15.9MB; 8x replay 13786ms / cold rebuild 2508ms / warm ~2.2-2.3s / cache 127MB; verify-cache matched at both scales, generation stays 1 across warm reads. Warm serve still scales with total issues (full-snapshot deserialize) -- indexed point reads are read-model-queries (sase-1h8.12); the token path itself is 3 stats at any scale. Pre-existing rustfmt drift in 2 fingerprint files (clean-tree cargo fmt --check red) folded in so the gate passes.

## Dependencies

- **Depends on:** [sase-1h8.1](sase-1h8.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.11](sase-1h8.11.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.4](sase-1h8.4.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.9](sase-1h8.9.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.8.md) | [sase-1h8.8](sase-1h8.8.md) | 0 |
